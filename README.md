# Cardano HW cli tool
Cardano HW CLI tool for signing transaction

# Installation
Check:
- releases https://github.com/vacuumlabs/cardano-hw-cli/releases
- installation instructions https://github.com/vacuumlabs/cardano-hw-cli/blob/develop/docs/installation.md

# Usage
For running commands with ledger, you might need to use `sudo`

## Generate public verification key and hardware wallet signing file
```
cardano-hw-cli shelley address key-gen
--path PATH                     Derivation path to the key we want to sign with.
--verification-key-file FILE    Output filepath of the verification key.
--hw-signing-file FILE          Output filepath of the hardware wallet signing file.
```

## Generate public verification key
```
cardano-hw-cli shelley key verification-key
--hw-signing-file FILE          Input filepath of the hardware wallet signing file.
--verification-key-file FILE    Output filepath of the verification key.
```

## Sign transaction
```
cardano-hw-cli shelley transaction sign
--tx-body-file FILE                    Input filepath of the TxBody.
--hw-signing-file FILE                 Input filepath of the hardware wallet signing file (one or more).
--change-output-key-file FILE          Input filepath of the hardware wallet signing file.
--mainnet | --testnet-magic NATURAL    Use the mainnet magic id or specify testnet magic id.
--out-file FILE                        Output filepath of the Tx.
```

## Witness transaction
```
cardano-hw-cli shelley transaction witness
--tx-body-file FILE                    Input filepath of the TxBody.
--hw-signing-file FILE                 Input filepath of the hardware wallet signing file.
--change-output-key-file File          Input filepath of the hardware wallet signing file.
--mainnet | --testnet-magic NATURAL    Use the mainnet magic id or specify testnet magic id.
--out-file FILE                        Output filepath of the Tx.
```

# Show address on device
```
cardano-hw-cli shelley address show 
  --payment-path PAYMENTPATH    Payment derivation path.
  --staking-path STAKINGPATH    Stake derivation path.
  --address-file ADDRESS        Input filepath of the address.
```

## Check app version
```
cardano-hw-cli version
```

## Check device version
```
cardano-hw-cli device version
```

## Examples
- https://github.com/vacuumlabs/cardano-hw-cli/blob/develop/docs/delegation-example.md
- https://github.com/vacuumlabs/cardano-hw-cli/blob/develop/docs/transaction-example.md

# Running from source
Install node version v12.16.2
```
nvm i v12.16.2
```

Install yarn:
```
npm install -g yarn
```

Install dependencies:
```
yarn install
```

Run unit test
```
yarn test-unit
```

Run application with
```
yarn dev ...
```

# Building from source
Install node version v12.16.2
```
nvm i v12.16.2
```

Install yarn:
```
npm install -g yarn
```

To build all artifacts for each OS run:
```
yarn build
```

To target specific artifact, run one of following commands:
```
yarn build-linux-deb
yarn build-linux-tar
yarn build-windows
yarn build-macos
```
