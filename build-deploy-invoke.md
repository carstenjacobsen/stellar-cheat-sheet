# Build, Deploy & Invoke

The lifecycle of a smart contract can be described as these four steps: Write Code, Compile/Build, Deploy and Invoke. Let's say you have some code, and now it's time to get it on the network.

## Build
First step is to build the code, run this command from your project root:

```bash
stellar contract build
```

## Deploy
Now deploy the smart contract to the Stellar blockchain. The smart contract can be deployed to `testnet`, `mainnet` or `futurenet`. For development and testing, `testnet` is typically used:

```bash
stellar contract deploy \
  --wasm target/wasm32-unknown-unknown/release/hello_world.wasm \
  --source alice \
  --network testnet \
  --alias hello_world
```


