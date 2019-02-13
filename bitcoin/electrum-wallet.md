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

