# Config file
The following is the default configuration used by `cuprated`.

```toml
# `cuprated` configuration file.
#
# See also:
# - <https://user.cuprate.org/config.html>
# - <https://github.com/Cuprate/cuprate/tree/main/binaries/cuprated/Cuprated.toml>

network = "Mainnet"

[tracing.stdout]
level = "info"

[p2p.clear_net]
outbound_connections = 64
extra_outbound_connections = 8
max_inbound_connections = 128
gray_peers_percent = 0.7
p2p_port = 0
listen_on = "0.0.0.0"

[p2p.clear_net.address_book_config]
max_white_list_length = 1_000
max_gray_list_length = 5_000
peer_save_period = { secs = 90, nanos = 0 }

[p2p.block_downloader]
buffer_size = 50_000_000
in_progress_queue_size = 50_000_000
target_batch_size = 5_000_000
check_client_pool_interval = { secs = 30, nanos = 0 }

[storage]
reader_threads = "OnePerThread"

[storage.txpool]
sync_mode = "Async"
max_txpool_byte_size = 100_000_000

[storage.blockchain]
sync_mode = "Async"
```

## Location
TODO

## Command-line overrides
TODO

## Config-relative paths
TODO
