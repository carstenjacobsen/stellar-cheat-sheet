# Storage
Smart contracts can persist data in the Stellar ledger using the storage interface. There are three types of storage available on the Stellar network: `persistent`, `temporary` and `instance`. The examples shows how to set and get a counter value, but any type of data can be used.

## Persistent Storage
This storage type is used for storing data on the network over an indefinitely long time period.

#### Set Value
```rust
const COUNTER: Symbol = symbol_short!("COUNTER");
let count: u32 = 1;

env.storage().persistent().set(&COUNTER, &count);
```

#### Get Value
```rust
const COUNTER: Symbol = symbol_short!("COUNTER");

let mut val: u32 = env.storage().persistent().get(&COUNTER).unwrap_or(0);
```


