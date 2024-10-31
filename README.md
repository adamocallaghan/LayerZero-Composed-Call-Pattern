## LayerZero Composed Call Pattern

**An example repo on how to implement LayerZero composed (A-B1-B2) calls, with deployment and wire-up scripts.**

Contains:

- **script**:
  - DeployToArbitrum.s.sol: a script for deploying both the Token and Vault contracts to Arbitrum Sepolia testnet
  - DeployToBase.s.sol: a script for deploying both the Token and Vault contracts to Base Sepolia testnet
  - SetPeers.s.sol: a script for "wiring up" (aka "setting peers") on our contracts
- **src**:
  - Token.sol: our OFT token
  - Vault.sol: our OApp contract
- **test**:
  - OptionsBuilder.t.sol: the LayerZero OptionsBuilder used in a test file to easily see our options bytes arrays

## Usage

### Download

Clone the repo to your local machine, and run...

```shell
$ forge install
```

### .env

Use .example.env to create a .env file...

- add in your own RPC URLs
- add in your block explorer API keys
- add in your Deployer wallet private and public keys

If you are using Base Sepolia and Arbitrum Sepolia then the LayerZero endpoints and IDs are already correct.

### Makefile

The Makefile commands are all currently based upon you having your "deployer" wallet set in foundry.
You can do this by running...

```shell
$ cast wallet import deployer --interactive
```

...and pasting in your private key
