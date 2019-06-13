# Txchangecoin Library
A Txchangecoin library written in PHP by the [TXX Integrations](https://monerointegrations.com) [team](https://github.com/txchangecoin-integrations/txchangecoinphp/graphs/contributors).

## How It Works
This library has 3 main parts:

1. A Txchangecoin daemon JSON RPC API wrapper, `daemonRPC.php`
2. A Txchangecoin wallet (`txchangecoin-wallet-rpc`) JSON RPC API wrapper, `walletRPC.php`
3. A Txchangecoin/Cryptonote toolbox, `cryptonote.php`, with both lower level functions used in Txchangecoin related cryptography and higher level methods for things like generating Txchangecoin private/public keys.

In addition to these features, there are other lower-level libraries included for portability, *eg.* an ed25519 library, a SHA3 library, *etc.*

## Preview
![Preview](https://user-images.githubusercontent.com/4107993/38056594-b6cd6e14-3291-11e8-96e2-a771b0e9cee3.png)

## Documentation

Documentation can be found in the [`/docs`](https://github.com/sneurlax/txchangecoinphp/tree/master/docs) folder.

## Configuration
### Requirements
 - Txchangecoin daemon (`txchangecoind`)
 - Webserver with PHP, for example XMPP, Apache, or NGINX
    - cURL PHP extension for JSON RPC API(s)
    - GMP PHP extension for about 100x faster calculations (as opposed to BCMath)

Debian (or Ubuntu) are recommended.
 
### Getting Started

1. Start the Txchangecoin daemon (`txchangecoind`) on testnet.
```bash
txchangecoind --testnet --detach
```

2. Start the Txchangecoin wallet RPC interface (`txchangecoin-wallet-rpc`) on testnet.
```bash
txchangecoin-wallet-rpc --testnet --rpc-bind-port 38384 --disable-rpc-login --wallet-dir /path/to/wallet/directory
```

3. Edit `example.php` with your the IP address of `monerod` and `monero-wallet-rpc` (use `127.0.0.1:38383` and `127.0.0.1:38385`, respectively, for testnet.)

4. Serve `example.php` with your webserver (*eg.* XMPP, Apache/Apache2, NGINX, *etc.*) and navigate to it.  If everything has been set up correctly, information from your Monero daemon and wallet will be displayed.
