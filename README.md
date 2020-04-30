# Ethereum Proof-of-Authority Testnet Example

Example proof-of-authority Ethereum testnet bootstrapped using Docker Compose.

## Services

Our testnet consists of 3 services:
- Single Geth node,
- Blockscout,
- Postgres

HTTP RPC is exposed on port 8178. This is the only port that isn't blocked by MyEtherWallets CSP header. WebSocket API is available at 8546. Once bootstrapped, you can navigate to [http://localhost:4000](http://localhost:4000) to access Blockscout explorer.

## Accounts

This testnet is using two accounts. **DON'T REUSE THESE KEYS ON ANY OTHER ETHEREUM NETWORK.**

### Buffer
An account which holds all the coins.

- **Address:** `0x411167FeFecAD12Da17F9063143706C39528aa28`
- **Private key:** `0x766df34218d5a715018d54789d6383798a1885088d525670802ed8cf152db5b4`

### Signer
Default signer on PoA network. The only account allowed to mine blocks.

- **Address:** `0x0c56352F05De44C9b5BA8bcF9BDEc7e654993339`
- **Private key:** `0x0d0b4c455973c883bb0fa584f0078178aa90c571a8f1d40f28d2339f4e757dde`

## Bootstrapping

Use Docker Compose to bootstrap the testnet.

```shell
$ docker-compose up -d
```

## Usage with MyEtherWallet.com

Add a custom network/node with these parameters. Explorer URLs are required and if you enter something that isn't a valid URL there, you'll most likely encounter the least helpful error message I've ever seen: `{}`.

- **URL:** `http://localhost`
- **Type:** CUS - CUSTOM
- **Port:** `8178`
- **Chain ID:** `5555`
- **Explorer TX URL:** `http://localhost:4000/tx/[[txHash]]`
- **Explorer Address URL:** `http://localhost:4000/address/[[address]]`

![MEW Config](/img/mew.png#max500 'MEW Config')
