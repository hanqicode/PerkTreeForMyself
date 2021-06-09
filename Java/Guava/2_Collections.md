# Collections
[User Guide](https://github.com/google/guava/wiki/ImmutableCollectionsExplained)

## ImmutableCollections

### Why?
Immutable objects have many advantages, including:
- Safe for use by untrusted libraries.
- Thread-safe: can be used by many threads with no risk of race conditions.
- Doesn't need to support mutation, and can make time and space savings with that assumption. All immutable collection implementations are more memory-efficient than their mutable siblings.
- Can be used as a constant, with the expectation that it will remain fixed.

It is better than JDK `Collections.unmodifiableXXX`. See [explanation](https://github.com/google/guava/wiki/ImmutableCollectionsExplained).

### How?
- `ImmutableSet.copyOf(set)`;
- `ImmutableSet.of("a", "b", "c")`;
- `Builder`

## Collection Utilities
// TODO: https://github.com/google/guava/wiki/CollectionUtilitiesExplained
