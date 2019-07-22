# Electrum Wallet

I recently built this version of Electrum locally to manage Bitcoin Testnet funds in a Ledger wallet.

{% embed url="https://github.com/spesmilo/electrum" %}

Electrum also ships a server, ElectrumX, that plugs into your blockchain node of choice so you don't have to trust anyone else:

{% embed url="https://github.com/spesmilo/electrumx" %}

## Ledger Hardware Wallet

Unlike the Ledger desktop app, Electrum supports p2wkh wallets in addition to the legacy np2wkh and p2pkh wallets.

To interface with the Ledger, you'll also need to install btchip-python:

{% embed url="https://github.com/LedgerHQ/btchip-python" %}

## Install ElectrumX

{% embed url="https://electrumx.readthedocs.io/en/latest/HOWTO.html\#prerequisites" %}

### Arch Linux

You will need to install some system-level dependencies for interacting with databases.

```text
export REPOS=/path/to/your/git/repos
git clone https://aur.archlinux.org/rocksdb.git $REPOS/rocksdb
cd $REPOS/rocksdb
makepkg -si
sudo pacman -S leveldb

git clone git@github.com:/kyuupichan/electrumx
cd $REPOS/electrumx
pipenv --python 3.7
pipenv install python-rocksdb
pipenv install plyvel
pipenv install
pipenv shell
./electrumx_server
```

{% embed url="https://www.archlinux.org/packages/extra/x86\_64/leveldb/" %}

{% embed url="https://plyvel.readthedocs.io/en/latest/installation.html" %}

{% embed url="https://aur.archlinux.org/packages/rocksdb/" %}

{% embed url="https://github.com/twmht/python-rocksdb" %}

## Running ElectrumX

The standard technique for configuring ElectrumX involves creating lots and lots of environmental variables:

{% embed url="https://electrumx.readthedocs.io/en/latest/environment.html" %}

For instance, to restrict memory usage to approximately 500MB on a resource-constrained platform like a Raspberry Pi or a HardKernel Odroid:

`DB_DIRECTORY='/mnt/data/electrum-btc' DAEMON_URL=rpcuser:rpcpass@127.0.0.1 COIN=BitcoinSegwit NET=mainnet DB_ENGINE=rocksdb CACHE_MB=500 ./electrumx_server`

where rpcuser and rpcpass are set in your `bitcoind` file.

### Electrum Queries

By default, ElectrumX does not listen for queries on any port or interface; you must configure this at runtime using the `SERVICES` environmental variable, for instance \`SERVICES=[tcp://localhost:50001](tcp://localhost:50001)\`.

ElectrumX provides a raw TCP socket for queries.  You can use a tool like `netcat` to sling these queries.  Here are some example queries:

```text
echo '{"id": 1, "method": "blockchain.block.header", "params": ["1"]}' | nc localhost 50001
echo '{"id": 1, "method": "mempool.get_fee_histogram", "params": []}' | nc localhost 50001
echo '{"id": 1, "method": "blockchain.scripthash.get_history", "params": ["9c0b6d7a6f8e74f16ed5e1adae8ee70e88a7e77c8a9bcc063b44c6f43e5f7fb2"]}' | nc localhost 50001
echo '{"id": 1, "method": "blockchain.scripthash.get_balance", "params": ["0fb72c30d33d609f6ead88fe6f76fdfc0bc92c48e5132a0a385a3c2fba6a030a"]}' | nc localhost 50001
```

`blockchain.scripthash` queries take scripthashes—the sha256 hash of the output script—as a parameter.  Bitcoin follows strange conventions for hashing and byte ordering, but you can use these scripts to convert an output script into a scripthash that will work for you.

For instance, here's the output script of the coinbase transaction from [the fifth Bitcoin block](https://blockstream.info/block-height/5):

`410456579536d150fbce94ee62b47db2ca43af0a730a0467ba55c79e2a7ec9ce4ad297e35cdbb8e42a4643a60eef7c9abee2f5822f86b1da242d9c2301c431facfd8ac`

To generate the scripthash in a bash terminal:

```text
$ echo -n 410456579536d150fbce94ee62b47db2ca43af0a730a0467ba55c79e2a7ec9ce4ad297e35cdbb8e42a4643a60eef7c9abee2f5822f86b1da242d9c2301c431facfd8ac | xxd -r -p | sha256sum -b | cut -d' ' -f1 | tac -r -s ..
0fb72c30d33d609f6ead88fe6f76fdfc0bc92c48e5132a0a385a3c2fba6a030a
```

Use this script to query the balance of this output:

```text
echo '{"id": 1, "method": "blockchain.scripthash.get_balance", "params": ["0fb72c30d33d609f6ead88fe6f76fdfc0bc92c48e5132a0a385a3c2fba6a030a"]}' | nc localhost 50001
```

You can also use the bitcoinjs-lib NodeJS library to convert an address to an output script and hash it appropriately to generate a scripthash that will work for Electrum queries:

```text
const bitcoin = require('bitcoinjs-lib')
address='38z1Y5NrzcRnEady3MppbCyG9s7mwcgHmB'
let script = bitcoin.address.toOutputScript(address)
let hash = bitcoin.crypto.sha256(script)
let reversedHash = new Buffer(hash.reverse())
console.log(address, ' maps to ', reversedHash.toString('hex'))
38z1Y5NrzcRnEady3MppbCyG9s7mwcgHmB  maps to  9c0b6d7a6f8e74f16ed5e1adae8ee70e88a7e77c8a9bcc063b44c6f43e5f7fb2
```

