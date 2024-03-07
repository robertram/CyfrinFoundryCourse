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


# Tests

## Console log inside tests

```shell
forge test -vv
```

## Test with testnet

```shell
forge test -vv  --fork-url $SEPOLIA_RPC_URL
```

## Run only one test

```shell
forge test --match-test testPriceFeedVersionIsAccurate
```

// What can we do to work with addresses outside our system?
// 1. Unit
//    - Testing a specific part of our code
// 2. Integration
//    - Testing how our code works with other parts of our code
// 3. Forked
//    - Testing our code on a simulated real environment
// 4. Staging
//    - Testing our code in a real environment that is not prod


## Test using a real testnet

```shell
forge test --match-test testPriceFeedVersionIsAccurate -vvv --fork-url $SEPOLIA_RPC_URL
```

## See tests coverage

```shell
forge coverage -vvv --fork-url $SEPOLIA_RPC_URL
```
