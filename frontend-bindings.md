# Frontend Bindings

The Stellar CLI can generate and produce a fully typed NPM package ready for integration into your frontend. This means you can invoke a smart contract, by adding the bindings package, and use its interface.

## Generate Bindings
Before we can create the bindings, we need to build and deploy the smart contract. When that's done, follow these three steps:

### Step 1
Run the Stellar CLI bindings command, using the contract address. Use the contract address returned by the deploy command.

```bash
stellar contract bindings typescript \
    --network testnet \
    --id <contract_address_from_deploy_step> \
    --output-dir ./packages/<project_name> \
    --overwrite
```

### Step 2
The binding package is now generated in the `packages/<project_name>` folder. Now we install and build it. 

```bash
cd packages/<project_name>
pnpm install
pnpm run build
cd ../..
```

### Step 3
The last step is to import the bindings package as a project dependency so we can use it in the frontend code.

```bash
pnpm add file:./packages/<project_name>
```

## Use Bindings
This example is a simplified version of a contract function call in the [Hello World sample dapp](https://developers.stellar.org/docs/build/smart-contracts/getting-started/hello-world-frontend)), but it serves well as an example of how the bindings can be implemented.

First the package is imported, and a client is instantiated, with the appropriate network settings, in this case testnet. The hello() contract function can now be invoked using the frontend binding client.

```javascript
---
import * as Client from '<project_name>';

const contract = new Client.Client({
   ...Client.networks.testnet,
   rpcUrl: 'https://soroban-testnet.stellar.org:443'
});

const { result } = await contract.hello({to: "Devs!"});
const greeting = result.join(" ");
---

<h1>{greeting}</h1>
```

## Links
- [Build a Hello World Frontend](https://developers.stellar.org/docs/build/smart-contracts/getting-started/hello-world-frontend)
