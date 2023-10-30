## Install foundry

https://book.getfoundry.sh/getting-started/installation

## Install dependencies

```
forge install
```

## Load env

```
source .env
```

## Deploy

```
forge script script/DeployPermit2.s.sol:DeployPermit2 \
 --chain-id $CHAIN_ID --rpc-url $RPC_URL \
 --etherscan-api-key $ETHERSCAN_API_KEY --verifier-url $VERIFIER_URL \
 --private-key $PRIVATE_KEY --broadcast --verify -vvvv
```

## Deploy ONUS (Manual verify)

```
forge script script/DeployPermit2.s.sol:DeployPermit2 \
 --chain-id $CHAIN_ID --rpc-url $RPC_URL \
 --private-key $PRIVATE_KEY --broadcast -vvvv --legacy
```

## Verify

```
forge verify-contract \
 -c $CHAIN_ID \
 --num-of-optimizations 1000000 \
 --watch \
 0x134ad5aa7114ed1742860e1a5555fe60f6ac678f \
 src/Permit2.sol:Permit2
```
