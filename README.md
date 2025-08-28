# Upgradeable Beacon Proxy

## Deploy

```bash
cargo stylus deploy \
  -e=$RPC_URL \
  --private-key=$PRIV_KEY \
  --wasm-file=$WASM_FILE \
  --no-verify \
  --deployer-address=$DEPLOYER_ADDRESS \
  --constructor-signature 'constructor(address,address)' \
  --constructor-args <IMPLEMENTATION_ADDRESS> <OWNER>
```

## Get Implementation

```bash
cast call <CONTRACT_ADDRESS> "implementation()(address)" --rpc-url $RPC_URL
```

## Upgrade To

```bash
cast send <CONTRACT_ADDRESS> "upgradeTo(address)" <NEW_IMPLEMENTATION_ADDRESS>  --private-key $PRIV_KEY --rpc-url $RPC_URL
```
