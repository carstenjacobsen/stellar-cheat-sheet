# Storage
Smart contracts can persist data in the Stellar ledger using the storage interface. There are three types of storage available on the Stellar network: `persistent`, `temporary` and `instance`.

## Persistent Storage
This storage type is used for storing data on the network over an indefinitely long time period.

#### Set Value
```rust
env.storage().persistent().set(&key, &value);
```

#### Get Value
```rust
let mut val: u32 = env.storage().persistent().get(&key).unwrap_or(0);
```


