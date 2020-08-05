# BitcoinVaultJS (btcvjs-lib)

A javascript Bitcoin Vault library for node.js and browsers. Written in TypeScript, but committing the JS files to verify.

Released under the terms of the [MIT LICENSE](LICENSE).

## Documentation
Presently,  we do not have any formal documentation other than our [examples](#examples).

Typically we support the [Node Maintenance LTS version](https://github.com/nodejs/Release).
If in doubt, see the [.travis.yml](.travis.yml) for what versions are used by our continuous integration tests.

### Browser
The recommended method of using `btcvjs-lib` in your browser is through [Browserify](https://github.com/substack/node-browserify).
If you're familiar with how to use browserify, ignore this and carry on, otherwise, it is recommended to read the tutorial at https://browserify.org/.

**NOTE**: We use Node Maintenance LTS features, if you need strict ES5, use [`--transform babelify`](https://github.com/babel/babelify) in conjunction with your `browserify` step (using an [`es2015`](https://babeljs.io/docs/plugins/preset-es2015/) preset).

**WARNING**: iOS devices have [problems](https://github.com/feross/buffer/issues/136), use atleast [buffer@5.0.5](https://github.com/feross/buffer/pull/155) or greater,  and enforce the test suites (for `Buffer`, and any other dependency) pass before use.

### Typescript or VSCode users
Type declarations for Typescript are included in this library. Normal installation should include all the needed type information.

## Examples
The below examples are implemented as integration tests, they should be very easy to understand.
Otherwise, pull requests are appreciated.
Some examples interact (via HTTPS) with a 3rd Party Blockchain Provider (3PBP).

- [Generate a random address](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/addresses.spec.ts)
- [Import an address via WIF](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/addresses.spec.ts)
- [Generate a 2-of-3 P2SH multisig address](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/addresses.spec.ts)
- [Generate a SegWit address](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/addresses.spec.ts)
- [Generate a SegWit P2SH address](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/addresses.spec.ts)
- [Generate a SegWit 3-of-4 multisig address](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/addresses.spec.ts)
- [Generate a SegWit 2-of-2 P2SH multisig address](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/addresses.spec.ts)
- [Support the retrieval of transactions for an address (3rd party blockchain)](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/addresses.spec.ts)
- [Generate a Testnet address](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/addresses.spec.ts)
- [Generate a Litecoin address](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/addresses.spec.ts)
- [Create a 1-to-1 Transaction](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/transactions.spec.ts)
- [Create (and broadcast via 3PBP) a typical Transaction](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/transactions.spec.ts)
- [Create (and broadcast via 3PBP) a Transaction with an OP\_RETURN output](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/transactions.spec.ts)
- [Create (and broadcast via 3PBP) a Transaction with a 2-of-4 P2SH(multisig) input](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/transactions.spec.ts)
- [Create (and broadcast via 3PBP) a Transaction with a SegWit P2SH(P2WPKH) input](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/transactions.spec.ts)
- [Create (and broadcast via 3PBP) a Transaction with a SegWit P2WPKH input](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/transactions.spec.ts)
- [Create (and broadcast via 3PBP) a Transaction with a SegWit P2PK input](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/transactions.spec.ts)
- [Create (and broadcast via 3PBP) a Transaction with a SegWit 3-of-4 P2SH(P2WSH(multisig)) input](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/transactions.spec.ts)
- [Create (and broadcast via 3PBP) a Transaction and sign with an HDSigner interface (bip32)](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/transactions.spec.ts)
- [Import a BIP32 testnet xpriv and export to WIF](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/bip32.spec.ts)
- [Export a BIP32 xpriv, then import it](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/bip32.spec.ts)
- [Export a BIP32 xpub](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/bip32.spec.ts)
- [Create a BIP32, bitcoin, account 0, external address](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/bip32.spec.ts)
- [Create a BIP44, bitcoin, account 0, external address](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/bip32.spec.ts)
- [Create a BIP49, bitcoin testnet, account 0, external address](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/bip32.spec.ts)
- [Use BIP39 to generate BIP32 addresses](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/bip32.spec.ts)
- [Create (and broadcast via 3PBP) a Transaction where Alice can redeem the output after the expiry (in the past)](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/cltv.spec.ts)
- [Create (and broadcast via 3PBP) a Transaction where Alice can redeem the output after the expiry (in the future)](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/cltv.spec.ts)
- [Create (and broadcast via 3PBP) a Transaction where Alice and Bob can redeem the output at any time](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/cltv.spec.ts)
- [Create (but fail to broadcast via 3PBP) a Transaction where Alice attempts to redeem before the expiry](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/cltv.spec.ts)
- [Create (and broadcast via 3PBP) a Transaction where Alice can redeem the output after the expiry (in the future) (simple CHECKSEQUENCEVERIFY)](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/csv.spec.ts)
- [Create (but fail to broadcast via 3PBP) a Transaction where Alice attempts to redeem before the expiry (simple CHECKSEQUENCEVERIFY)](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/csv.spec.ts)
- [Create (and broadcast via 3PBP) a Transaction where Bob and Charles can send (complex CHECKSEQUENCEVERIFY)](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/csv.spec.ts)
- [Create (and broadcast via 3PBP) a Transaction where Alice (mediator) and Bob can send after 2 blocks (complex CHECKSEQUENCEVERIFY)](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/csv.spec.ts)
- [Create (and broadcast via 3PBP) a Transaction where Alice (mediator) can send after 5 blocks (complex CHECKSEQUENCEVERIFY)](https://github.com/bitcoinvault/btcvjs-lib/blob/master/test/integration/csv.spec.ts)

## Contributing
See [CONTRIBUTING.md](CONTRIBUTING.md).


### Running the test suite

``` bash
npm test
npm run-script coverage
```

## Complementing Libraries
- [BIP21](https://github.com/bitcoinjs/bip21) - A BIP21 compatible URL encoding library
- [BIP38](https://github.com/bitcoinjs/bip38) - Passphrase-protected private keys
- [BIP39](https://github.com/bitcoinjs/bip39) - Mnemonic generation for deterministic keys
- [BIP32-Utils](https://github.com/bitcoinjs/bip32-utils) - A set of utilities for working with BIP32
- [BIP66](https://github.com/bitcoinjs/bip66) - Strict DER signature decoding
- [BIP68](https://github.com/bitcoinjs/bip68) - Relative lock-time encoding library
- [BIP69](https://github.com/bitcoinjs/bip69) - Lexicographical Indexing of Transaction Inputs and Outputs
- [Base58](https://github.com/cryptocoinjs/bs58) - Base58 encoding/decoding
- [Base58 Check](https://github.com/bitcoinjs/bs58check) - Base58 check encoding/decoding
- [Bech32](https://github.com/bitcoinjs/bech32) - A BIP173 compliant Bech32 encoding library
- [coinselect](https://github.com/bitcoinjs/coinselect) - A fee-optimizing, transaction input selection module for btcvjs-lib.
- [merkle-lib](https://github.com/bitcoinjs/merkle-lib) - A performance conscious library for merkle root and tree calculations.
- [minimaldata](https://github.com/bitcoinjs/minimaldata) - A module to check bitcoin policy: SCRIPT_VERIFY_MINIMALDATA


## Alternatives
- [BCoin](https://github.com/indutny/bcoin)
- [Bitcore](https://github.com/bitpay/bitcore)
- [Cryptocoin](https://github.com/cryptocoinjs/cryptocoin)


## LICENSE [MIT](LICENSE)
