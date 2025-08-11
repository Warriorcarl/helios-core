# Helios-Core CLI Documentation

This document provides a detailed overview of all `heliades` commands, subcommands, arguments, and their functions.

---

## Usage
```
heliades [command] [subcommand] [flags]
```

## Main Commands & Subcommands

### add-genesis-account
Add a genesis account to `genesis.json`.
- **Usage:** `heliades add-genesis-account ADDRESS_OR_KEY_NAME COIN... [flags]`
- **Flags:** `--clawback`, `--funder`, `--grpc-addr`, `--height`, `--lockup`, `--vesting`, `--vesting-start-time`, etc.
- **Function:** Adds an account with initial coins and optional vesting/clawback parameters.

### application-db
Apply a method to the application database.
- **Usage:** `heliades application-db [method] [flags]`
- **Methods:** `list`, `load-version`, `info`, `trace`
- **Flags:** `--app-db-backend`, `--height`, etc.

### backups
Backup and restore application state.
- **Subcommands:**
  - `dump`: Create a backup at the current height
  - `restore`: Restore a snapshot

### block
Get a specific block from the database.
- **Usage:** `heliades block [flags]`
- **Flags:** `--height`

### blockstore
Interact with CometBFT blockstore.
- **Subcommands:** `delete-latest-block`, `get`, `info`, `list`, `rollback`

### collect-gentxs
Collect genesis transactions and output a `genesis.json` file.
- **Flags:** `--gentx-dir`, `--home`

### config
Manage application configuration.
- **Subcommands:** `diff`, `get`, `home`, `migrate`, `set`, `view`

### debug
Debugging tools for the application.
- **Subcommands:** `addr`, `legacy-eip712`, `pubkey`, `raw-bytes`

### export
Export state to JSON.
- **Flags:** `--for-zero-height`, `--height`, `--jail-allowed-addrs`, `--modules-to-export`, `--output-document`

### gentx
Generate a genesis transaction for validator creation.
- **Usage:** `heliades gentx [key_name] [amount] [flags]`
- **Flags:** `--commission-rate`, `--moniker`, `--identity`, `--website`, etc.

### index-eth-tx
Index historical Ethereum transactions.
- **Usage:** `heliades index-eth-tx [backward|forward] [flags]`

### init
Initialize validator and node configuration files.
- **Usage:** `heliades init [moniker] [flags]`
- **Flags:** `--chain-id`, `--default-denom`, `--initial-height`, `--overwrite`, `--recover`

### keys
Keyring management commands.
- **Subcommands:** `add`, `clear`, `delete`, `export`, `import`, `list`, `list-key-types`, `migrate`, `mnemonic`, `parse`, `rename`, `show`, `unsafe-export-eth-key`, `unsafe-import-eth-key`

### migrate
Migrate genesis file to a target version.
- **Usage:** `heliades migrate TARGET_VERSION GENESIS_FILE [flags]`
- **Flags:** `--chain-id`, `--genesis-time`

### prune
Prune app history states.
- **Usage:** `heliades prune [pruning-method] [flags]`
- **Flags:** `--app-db-backend`, `--pruning-interval`, `--pruning-keep-recent`

### query
Query blockchain data and modules.
- **Subcommands:** `auth`, `authz`, `bank`, `block`, `block-results`, `chronos`, `comet-validator-set`, `consensus`, `distribution`, `epochs`, `erc20`, `evidence`, `evm`, `feegrant`, `feemarket`, `gov`, `hyperion`, `ibc`, `ibc-fee`, `ibc-transfer`, `interchain-accounts`, `logos`, `mint`, `packetforward`, `params`, `ratelimit`, `revenue`, `slashing`, `staking`, `tokenfactory`, `tx`, `txs`, `upgrade`, `wait-tx`

### rollback
Rollback application and CometBFT state by one height.
- **Flags:** `--delete-latest-state`, `--hard`, `--height`

### rosetta
Spin up a Rosetta server for blockchain integration.
- **Flags:** `--addr`, `--blockchain`, `--denom-to-suggest`, `--enable-fee-suggestion`, `--gas-to-suggest`, `--grpc`, `--grpc-types-server`, `--network`, `--offline`, `--plugin`, `--prices-to-suggest`, `--retries`, `--tendermint`

### snapshots
Manage local snapshots.
- **Subcommands:** `delete`, `dump`, `export`, `list`, `load`, `restore`

### start
Run the full node application.
- **Flags:** Many options for ABCI, API, backup, consensus, database, EVM, gRPC, halt, metrics, P2P, pruning, RPC, state-sync, TLS, transport, upgrades, wasm, etc.

### statedb
Interact with CometBFT state database.
- **Subcommands:** `delete-latest`, `get`, `info`, `list`, `rollback`

### status
Query remote node for status.
- **Flags:** `--node`, `--output`

### tendermint
Tendermint subcommands.
- **Subcommands:** `bootstrap-state`, `reset-state`, `show-address`, `show-node-id`, `show-validator`, `unsafe-reset-all`, `version`

### testnet
Start or configure local testnets.
- **Subcommands:** `init-files`, `start`

### tx
Transaction subcommands.
- **Subcommands:** `auth`, `authz`, `bank`, `broadcast`, `chronos`, `consensus`, `crisis`, `decode`, `distribution`, `encode`, `erc20`, `evidence`, `evm`, `feegrant`, `feemarket`, `gov`, `hyperion`, `ibc`, `ibc-fee`, `ibc-transfer`, `interchain-accounts`, `mint`, `multi-sign`, `multisign-batch`, `packetfowardmiddleware`, `ratelimit`, `revenue`, `sign`, `sign-batch`, `simulate`, `slashing`, `staking`, `tokenfactory`, `upgrade`, `validate-signatures`, `vesting`, `logos`

### validate
Validate the genesis file.

### version
Print the application binary version information.

---

## Global Flags
- `--broadcast-mode` Transaction broadcasting mode (`sync|async`)
- `--chain-id` Specify Chain ID for sending Tx
- `--fees` Fees to pay along with transaction
- `--from` Name or address of private key with which to sign
- `--gas-adjustment` Adjustment factor for gas estimation
- `--gas-prices` Gas prices for transaction fee
- `--home` Directory for config and data
- `--keyring-backend` Keyring backend (`os|file|test|local`)
- `--log_format` Logging format (`json|plain`)
- `--log_level` Logging level (`trace|debug|info|warn|error|fatal|panic|disabled`)
- `--log_no_color` Disable colored logs
- `--node` Tendermint RPC interface address
- `--trace` Print full stack trace on errors

---

For more details on each subcommand, run:
```
heliades [command] [subcommand] --help
```

---

This documentation covers all available commands and options for the Helios-Core CLI as of v1.0.0.
