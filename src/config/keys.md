# Config keys
The following section provide more details on configuration options.

## Top level
Top-level general config options. These are defined without any sub-section.

| Key     | Type | Default | Values | Description |
|---------|------|---------|--------|-------------|
| `network` | string | `"Mainnet"` | `"Mainnet"`, `"Testnet"`, `"Stagenet"` | The network to run on.

### `[tracing.stdout]`
Logging configuration.

| Key     | Type | Default | Values | Description |
|---------|------|---------|--------|-------------|
| `level` | string | `"info"` | `"error"`, `"warn"`, `"info"`, `"debug"`, `"trace"` | The minimum level for log events to be displayed.

### `[p2p.clear_net]`
P2P configuration for clear-net.

| Key     | Type | Default | Values | Description |
|---------|------|---------|--------|-------------|
| `outbound_connections` | unsigned integer | `64` | `0` to `MAX` | The number of outbound connections to create and maintain.
| `extra_outbound_connections` | unsigned integer | `8` | `0` to `MAX` | The number of extra connections to create when under load from the rest of Cuprate, i.e. when syncing.
| `max_inbound_connections` | unsigned integer | `128` | `0` to `MAX` | The maximum number of incoming to allow.
| `gray_peers_percent` | decimal number | `0.7` | `0.0` to `1.0` | The percent of outbound connections that should be to nodes we have not connected to before.
| `p2p_port` | Port (unsigned integer) | `0` | `0` to `65535` | The port to accept connections on, if left `0` no connections will be accepted.
| `listen_on` | IPv4 address (string) | `"0.0.0.0"` | | The IP address to listen to connections on.

### `[p2p.clear_net.address_book_config]`
P2P configuration for the clear-net address book.

| Key     | Type | Default | Values | Description |
|---------|------|---------|--------|-------------|
| `max_white_list_length` | unsigned integer | `1_000` | `0` to `MAX` | The size of the white peer list, which contains peers we have made a connection to before.
| `max_gray_list_length` | unsigned integer | `5_000` | `0` to `MAX` | The size of the gray peer list, which contains peers we have not made a connection to before.
| `peer_save_period` | `{ seconds, nanoseconds }` | `{ secs = 90, nanos = 0 }` | `0` to `MAX` | The amount of time between address book saves.

### `[p2p.block_downloader]`
Block downloader configuration.

| Key     | Type | Default | Values | Description |
|---------|------|---------|--------|-------------|
| `buffer_size` | unsigned integer | `50_000_000` | `0` to `MAX` | The size of the buffer of sequential blocks waiting to be verified and added to the chain in bytes.
| `in_progress_queue_size` | unsigned integer | `50_000_000` | `0` to `MAX` | The size of the queue of blocks which are waiting for a parent block to be downloaded in bytes.
| `target_batch_size` | unsigned integer | `5_000_000` | `0` to `100_000_000` | The target size of a batch of blocks in bytes.
| `check_client_pool_interval` | `{ seconds, nanoseconds }` | `{ secs = 30, nanos = 0 }` | `0` to `MAX` | The amount of time between checking the pool of connected peers for free peers to download blocks.

### `[storage]`
Storage configuration.

| Key     | Type | Default | Values | Description |
|---------|------|---------|--------|-------------|
| `reader_threads` | string | `"OnePerThread"` | TODO | The amount of database reader threads to spawn.

### `[storage.txpool]`
Transaction pool configuration.

| Key     | Type | Default | Values | Description |
|---------|------|---------|--------|-------------|
| `sync_mode` | string | `"Async"` | TODO | The database sync mode for the transaction pool.
| `max_txpool_byte_size` | unsigned integer | `100_000_000` | TODO | The maximum size of all the transaction in the pool in bytes.

### `[storage.blockchain]`
Blockchain configuration.

| Key     | Type | Default | Values | Description |
|---------|------|---------|--------|-------------|
| `sync_mode` | string | `"Async"` | TODO | The database sync mode for the blockchain.