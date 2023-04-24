# Pegasys V2 Periphery

[![Tests](https://github.com/pegasys-fi/v2-phperiphery/workflows/Tests/badge.svg)](https://github.com/pegasys-fi/v2-phperiphery/actions?query=workflow%3ATests)
[![Lint](https://github.com/pegasys-fi/v2-phperiphery/workflows/Lint/badge.svg)](https://github.com/pegasys-fi/v2-phperiphery/actions?query=workflow%3ALint)

This repository contains the periphery smart contracts for the Pegasys V2 Protocol.
For the lower level core contracts, see the [v2-core](https://github.com/pegasys-fi/v2-core)
repository.


## Local deployment

In order to deploy this code to a local testnet, you should install the npm package
`@pollum-io/v2-periphery`
and import bytecode imported from artifacts located at
`@pollum-io/v2-periphery/artifacts/contracts/*/*.json`.
For example:

```typescript
import {
  abi as SWAP_ROUTER_ABI,
  bytecode as SWAP_ROUTER_BYTECODE,
} from '@pollum-io/v2-periphery/artifacts/contracts/SwapRouter.sol/SwapRouter.json'

// deploy the bytecode
```
This will ensure that you are testing against the same bytecode that is deployed to
mainnet and public testnets, and all Pegasys code will correctly interoperate with
your local deployment.

## Using solidity interfaces

The Pegasys V2 periphery interfaces are available for import into solidity smart contracts
via the npm artifact `@pollum-io/v2-periphery`, e.g.:

```solidity
import '@pollum-io/v2-periphery/contracts/interfaces/ISwapRouter.sol';

contract MyContract {
  ISwapRouter router;

  function doSomethingWithSwapRouter() {
    // router.exactInput(...);
  }
}

```
