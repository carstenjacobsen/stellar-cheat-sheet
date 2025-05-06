# Deploy to Mainnet

The steps to deploy to `mainnet` is similar to deploying to `testnet` described in [Build, Deploy & Invoke](build-deploy-invoke.md) - with a couple of extra steps.

## Create Mainnet User Account
First step is to create a user for mainnet

```bash
stellar keys generate --network mainnet bob
```

## Fund User Account
Because there are fees associated with running a smart contract on mainnet, we need to fund the user account so we can pay for fees.

The user account can be funded from an exchange like Coinbase. To fund the account, we need to get the public address:

```bash
stellar keys public-key bob
```

Copy the public key/address and send some XLM to it from e.g. Coinbase. Deploying a smart contract will cost less than 1 XLM in fees, so we don't need to send a lot of XLM to the account, 5 XLM will go far. The user accounts balance can be checked with [Stellar.Expert](https://stellar.expert/).

## Build
Now we are ready to start deploying, and start by building the code. Run this command from your project root:

```bash
stellar contract build
```

## Deploy
Now deploy the smart contract to the Stellar blockchain. The smart contract can be deployed to `testnet`, `mainnet` or `futurenet`. For development and testing, `testnet` is typically used:

```bash
stellar contract deploy \
  --wasm target/wasm32-unknown-unknown/release/<project_name>.wasm \
  --source bob \
  --network mainnet
```

## Extend Contract TTL
The smart contract data ledger entry's TTL (Time To Live) can be extended like this:

```bash
stellar contract extend \
  --id CBU7AECY5NCMRYDKSMEN737BYIUBNPMFQTL7YTH436VVHXPHCU4CYA5E \
  --durability persistent \
  --ledgers-to-extend 120000 \
  --source bob \
  --network mainnet
```

Read more about the command here: [stellar contract extend](https://developers.stellar.org/docs/tools/cli/stellar-cli#stellar-contract-extend)
