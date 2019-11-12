# Leveraging Redis

We will see how we can leverage Redis's data structures, speed, and flexibility to resolve system limitations and problems.

## Using Redis as a Key/Value Store

### Storing application usage counters

Imagine we run a webpage and want to track profile/page visit data. We may have some ideas in mind:
- We could emit metrics. But this still not a direct number at a glance.
- We could just increase counter in our database. But will have trouble when traffic is high enough.

We need something much faster to update and to query. So here we use Redis for this instead.

---
**Naming Convention**

There is no actual convention for organizing keys, but a lot of people like to build keys out of keywords separated by colons.
Like: `visits:orderPage:totals`.

---

