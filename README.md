## Cyfrin Foundry Course

**Foundry is a blazing fast, portable and modular toolkit for Ethereum application development written in Rust.**

Foundry consists of:

-   **Forge**: Ethereum testing framework (like Truffle, Hardhat and DappTools).
-   **Cast**: Swiss army knife for interacting with EVM smart contracts, sending transactions and getting chain data.
-   **Anvil**: Local Ethereum node, akin to Ganache, Hardhat Network.
-   **Chisel**: Fast, utilitarian, and verbose solidity REPL.

## Documentation

https://book.getfoundry.sh/

## Usage

### Build

```shell
$ forge build
```

### Test

```shell
$ forge test
```

### Format

```shell
$ forge fmt
```

### Gas Snapshots

```shell
$ forge snapshot
```

### Anvil

```shell
$ anvil
```

### Deploy

```shell
$ forge script script/Counter.s.sol:CounterScript --rpc-url <your_rpc_url> --private-key <your_private_key>
```

### Cast

```shell
$ cast <subcommand>
```

### Help

```shell
$ forge --help
$ anvil --help
$ cast --help
```

# Convert hex to decimal 

cast --to-base [number] dec 

# Save Env variables 
Modify env 
Run source .env
echo $RPC_URL

# Run Anvil local blockchain

```shell
anvil
```

# Anvil Rpc deploy smart contract

## Adding rpc and hidden private key

```shell
forge create SimpleStorage --rpc-url http://127.0.0.1:8545 --interactive
```

## Adding rpc and private key

```shell
forge create SimpleStorage --rpc-url http://127.0.0.1:8545 --private-key 0xasdasd
```

## Deploy to Anvil by default and hidden private key

```shell
forge create SimpleStorage --interactive
```

# Deploy Smart Contract with scripts

```shell
forge script script/DeploySimpleStorage.s.sol --rpc-url http://127.0.0.1:8545 --broadcast --private-key [private-key]
```

Using the .env variables

```shell
forge script script/DeploySimpleStorage.s.sol --rpc-url $RPC_URL --broadcast --private-key $PRIVATE_KEY
```

*NOTE*: Having the .env file is cool in development but for production, use --interactive for the private key

# Interact with smart contract

Interact with contracts that already have been deployed

```shell
Cast
```

## Send transaction
```shell
cast send 0xe7f1725E7734CE288F8367e1Bb143E90bb3F0512 "store(uint256)" 123 --rpc-url $RPC_URL --private-key $PRIVATE_KEY
```

## Read function
```shell
cast call 0xe7f1725E7734CE288F8367e1Bb143E90bb3F0512 "retrieve()" 
```

# Thirdweb deploy

```shell
npx thirdweb deploy
```

# Format Code

```shell
forge fmt
```