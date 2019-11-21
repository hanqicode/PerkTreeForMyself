# Use Redis as a Key/Value Store

We will see how we can leverage Redis's data structures, speed, and flexibility to resolve system limitations and problems.

## Storing application usage counters

Imagine we run a webpage and want to track profile/page visit data. We may have some ideas in mind:
- We could emit metrics. But this still not a direct number at a glance.
- We could just increase counter in our database. But will have trouble when traffic is high enough.

We need something much faster to update and to query. So here we use Redis for this instead.

---
**Naming Convention**

There is no actual convention for organizing keys, but a lot of people like to build keys out of keywords separated by colons.
Like: `visits:orderPage:totals`.

---

## Storing object data in hashes
If we have a Java object like:
```java
@Getter
class User {
    private String name;
    private int age;
}
```

Then, its usage likes:
```bash
redis> hset user:qqihan name "qqihan"
redis > hset user:qqihan age 23
```

To set values:
```bash
redis> hset users:jdoe name "John Doe" 
(integer) 1
redis> hset users:jdoe email "jdoe@test.com" 
(integer) 1
redis> hset users:jdoe phone "+1555313940" 
(integer) 1
redis> hincrby users:jdoe visits 1 
(integer) 1
```

To get values:
```bash
redis> hget users:jdoe email 
"jdoe@test.com"
redis> hgetall users:jdoe
1) "name"
2) "John Doe"
3) "email"
4) "jdoe@test.com" 5) "phone"
6) "+1555313940" 7) "visits"
8) "1"
```

## Storing user "Circles" using sets
Sets are a natural fit for circles, because sets represent collections of data, and have native functionality to do interesting things like intersec- tions and unions.

```bash
redis> sadd circle:jdoe:family users:anna 
(integer) 1
redis> sadd circle:jdoe:family users:richard
(integer) 1
redis> sadd circle:jdoe:soccer users:anna
(integer) 1
```

```bash
redis> sinter circle:jdoe:family circle:jdoe:soccer
1) "users:anna"
redis> sunion circle:jdoe:family circle:jdoe:soccer
1) "users:anna"
2) "users:richard"
```
