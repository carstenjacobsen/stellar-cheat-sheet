# Storage
Smart contracts can persist data in the Stellar ledger using the storage interface. There are three types of storage available on the Stellar network: `persistent`, `instance` and `temporary`. The examples shows how to set and get a counter value, but any type of data can be used.

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


## Instance Storage
Instance storage is a small, limited-size map attached to the contract instance. It is physically stored in the same ledger entry as the contract itself and shares TTL with it.

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


## Temporary Storage
As the name implies, temporary storage stores data only for a certain time period, and then discards it automatically when TTL expires. **Temporary entries are gone forever when their TTL expires**.

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


## Links
- [Storage How-To Documentation](https://developers.stellar.org/docs/build/guides/storage/choosing-the-right-storage)
- [Storage Example Contract](https://developers.stellar.org/docs/build/smart-contracts/example-contracts/storage)
