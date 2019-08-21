# Cache General
Guava/Cache Github: https://github.com/google/guava/wiki/CachesExplained

Guava Java API doc: https://guava.dev/releases/23.0/api/docs/

## Two Interfaces
1. `Cache<K, V>`
It is NOT necessary to provide loader when building the cache.
2. `LoadingCache<K, V>`
It is necessary to provide loader when building the cache.

## Examples
1. Cache<K, V>
```java
@Test
public void whenCacheMiss_thenValueIsMissed() {
    // build
    Cache<String, String> cache = CacheBuilder.newBuilder().build();

    // operate
    String actual_before = cache.getIfPresent("hello");
    cache.put("hello", "test");
    String actual_after = cache.getIfPresent("hello");

    // check
    Assertions.assertNull(actual_before);
    Assertions.assertEquals("test", actual_after);
}
```

2. LoadingCache<K, V>
```java
@Test
public void whenCacheMiss_thenValueIsComputed() throws Exception {
    // build
    CacheLoader<String, String> loader = new CacheLoader<>() {
        @Override
        public String load(String key) {
            return key.toUpperCase();
        }
    };

    LoadingCache<String, String> cache = CacheBuilder.newBuilder()
            .expireAfterAccess(20, TimeUnit.MILLISECONDS)
            .build(loader);

    // operate
    String actual_before = cache.get("hello");
    cache.put("hello", "test");
    String actual_after_put = cache.get("hello");

    Thread.sleep(1000L);
    String actual_after_sleep = cache.get("hello");

    // check
    Assertions.assertEquals("HELLO", actual_before);
    Assertions.assertEquals("test", actual_after_put);
    Assertions.assertEquals("HELLO", actual_after_sleep);
}
```

## Eviction
It has several ways for eviction, so need to read the doc to find proper one based on our requirements.
- Size-based Eviction
- Timed Eviction
