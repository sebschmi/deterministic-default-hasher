# Deterministic default hasher

Annoyed by your rust hashtables behaving differently each execution, and making reproducing bugs a matter of luck?
Worry no more, simply use the deterministic default hasher, which is nothing else than a special constructor for the default hasher that always chooses the same seed, instead of using a random one.

## Example

```rust
use deterministic_default_hasher::DeterministicDefaultHasher;

let map = HashMap::<String, usize, DeterministicDefaultHasher>::new();
```

The third argument defaults to `DefaultHasher`.
Using `DeterministicDefaultHasher` instead makes the hash map deterministic.