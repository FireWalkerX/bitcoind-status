# bitcoind-status

This is a small PHP application designed to display status and information from the Bitcoin node daemon.

## Requirements

To run the application, you will need:

  * A Bitcoin node!
  * A web-server with PHP installed.
  * The PHP `curl` module - this is used to make RPC calls to the Bitcoin daemon.

## Getting Started

To get started, all you need to do is copy/rename `php/config.sample.php` to `php/config.php` and configure your node's RPC credentials. The application will connect to your node via RPC and report statistics.

## Advanced Options

The `config.php` file also contains lots of options to control how the application behaves:

  * `debug` (Boolean, default: FALSE) - Enables debug mode. This prints the full `$data` array into the page's HTML output inside a comment.
  * `rpc_user`(String, default: `rpcuser`) - Username for RPC calls.
  * `rpc_pass` (String, default: `rpcpass`) - Password for RPC calls.
  * `rpc_host` (String, default: `localhost`) - Which RPC host to connect to.
  * `rpc_port` (String, default: `8332`) - Port to use for the RPC connection.
  * `rpc_ssl` (Boolean, default: `FALSE`) - Should we use SSL for the RPC connection?
  * `rpc_ssl_ca` (String, default: `NULL`) - The SSL CA chain file.
  * `cache_file` (String, default: `/tmp/bitcoind-status.cache`) - File location to write to for cache.
  * `max_cache_time` (Int, default: 300`) - Expiry time for cache.
  * `nocache_whitelist` (Array, default: `array('127.0.0.1')`) - The IP addresses that are allowed to bypass or clear cache.
  * `admin_email` (String, default: `admin@domain.net`) - Email address to display on error
  * `display_donation_text` (Boolean, default: `TRUE`) - Display text to encourage donations.
  * `donation_address` (String, default: `not_set`) - Bitcoin address to use for donations to support the node.
  * `donation_amount` (String, default: `0.001`) - Donation amount - not currently implemented.
  * `use_bitcoind_ip` (Boolean, default: `FALSE`) - Use the Bitcoin daemon to get the public IP, instead of `$_SERVER`
  * `intro_text` (String, default: `not_set`) - Introductory text to display above the node statistics.
  * `display_peer_info` (Boolean, default: `FALSE`) - Switch to enable displaying connected peers.
  * `display_free_disk_space` (Boolean, default: `FALSE`) - Switch to enable displaying free disk space.
  * `display_ip_location` (Boolean, default: `FALSE`) - Switch to enable displaying your IP location.
  * `display_testnet` (Boolean, default: `TRUE`) - Switch to enable displaying if the node is running on testnet.
  * `display_version` (Boolean, default: `FALSE`) - Switch to enable displaying the nodes version.
  * `use_cache` (Boolean, default: `TRUE`) - Switch to enable the cache feature.

### Important Note

  *  **Do not** disable cache unless you either have an alternative mechanism or your node is protected from potential DDoS attacks.

## Development & Licensing

* Copyright (C) 2015 [Craig Watson](http://www.cwatson.org)
* Distributed under the terms of the [Apache License v2.0](http://www.apache.org/licenses/LICENSE-2.0) - see [LICENSE file](https://github.com/craigwatson/bitcoind-status/blob/master/LICENSE) for details.
* [EasyBitcoin-PHP library](https://github.com/aceat64/EasyBitcoin-PHP) is reproduced under the terms of the [MIT licence](http://opensource.org/licenses/MIT) and is used from commit [670414e](https://github.com/aceat64/EasyBitcoin-PHP/tree/670414e1b733e11bb7bdf4fcb17169853301716b).
* Further contributions and testing reports are extremely welcome - please submit a pull request or issue on [GitHub](https://github.com/craigwatson/bitcoind-status)
