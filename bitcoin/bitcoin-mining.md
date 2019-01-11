---
description: how to mine on the Bitcoin testnet
---

# Bitcoin Mining

### Practical Considerations

Bitcoin coinbase transactions must mature for 100 blocks before they can be spent.  This prevents the creation of chains of transactions that would be invalidated if a deep block reorganization occurs, orphaning blocks and removing their coinbase transactions from the ledger history.

SoChain estimates the realtime mining hashpower based on the block rate and difficulty:

* [https://chain.so/testnet/btc](https://chain.so/testnet/btc)
* [https://en.bitcoin.it/wiki/Difficulty](https://en.bitcoin.it/wiki/Difficulty)
* [https://bitcoinwisdom.com/bitcoin/difficulty](https://bitcoinwisdom.com/bitcoin/difficulty)



### Software

#### p2pool

* [https://en.bitcoin.it/wiki/P2Pool](https://en.bitcoin.it/wiki/P2Pool)
* [https://en.bitcoinwiki.org/wiki/P2Pool](https://en.bitcoinwiki.org/wiki/P2Pool)
* [http://p2pool.org/community/](http://p2pool.org/community/)
* [https://github.com/p2pool/p2pool](https://github.com/p2pool/p2pool)
* [https://github.com/jtoomim/p2pool/tree/1mb\_segwit](https://github.com/jtoomim/p2pool/tree/1mb_segwit)
  * [https://www.reddit.com/r/Bitcoin/comments/6uweb7/p2pool\_upgrade\_for\_segwit\_compatibility/?st=jqpopahu&sh=7dc7967b](https://www.reddit.com/r/Bitcoin/comments/6uweb7/p2pool_upgrade_for_segwit_compatibility/?st=jqpopahu&sh=7dc7967b)

When running p2pool locally, you can access the dashboard at the port you indicated with `-w`.

#### bitcoind

* [https://en.bitcoin.it/wiki/Running\_Bitcoin\#Sample\_Bitcoin.conf](https://en.bitcoin.it/wiki/Running_Bitcoin#Sample_Bitcoin.conf)
* [https://bitcoin.stackexchange.com/questions/77607/cant-specify-rpcport-for-testnet](https://bitcoin.stackexchange.com/questions/77607/cant-specify-rpcport-for-testnet)

#### cpuminer

* [https://rehmann.co/blog/cpuminer-help/](https://rehmann.co/blog/cpuminer-help/)
* [https://wiki.poiuty.com/index.php?title=Vertcoin\_cpuminer](https://wiki.poiuty.com/index.php?title=Vertcoin_cpuminer)
* [https://www.cryptocurrencyfreak.com/2017/08/06/vertcoin-mining-cpuminer-multi-centos-7/](https://www.cryptocurrencyfreak.com/2017/08/06/vertcoin-mining-cpuminer-multi-centos-7/)
* [https://www.cryptocurrencyfreak.com/2017/08/07/monero-mining-cpuminer-multi-centos-7/](https://www.cryptocurrencyfreak.com/2017/08/07/monero-mining-cpuminer-multi-centos-7/)

#### bmminer

* [https://www.reddit.com/r/Bitcoin/comments/7lkn9y/how\_to\_manually\_set\_the\_fan\_speed\_of\_your\_bitmain/](https://www.reddit.com/r/Bitcoin/comments/7lkn9y/how_to_manually_set_the_fan_speed_of_your_bitmain/)
* [https://github.com/dfoderick/Mining/blob/master/Antminer/bmminer.conf](https://github.com/dfoderick/Mining/blob/master/Antminer/bmminer.conf)
* [https://bitcointalk.org/index.php?topic=2799605.0](https://bitcointalk.org/index.php?topic=2799605.0)

### Errors

* [https://github.com/dashpay/p2pool-dash/issues/29](https://github.com/dashpay/p2pool-dash/issues/29)
* [https://litecointalk.io/t/setting-up-p2pool-on-mac/8206](https://litecointalk.io/t/setting-up-p2pool-on-mac/8206)
* [https://www.reddit.com/r/VertcoinMining/comments/767be5/help\_with\_p2pool\_setup/](https://www.reddit.com/r/VertcoinMining/comments/767be5/help_with_p2pool_setup/?st=jqpn3nf9&sh=9913666a)

### Examples

* [https://medium.com/@lopp/how-to-solo-mine-on-bitcoin-s-testnet-6073c917b495](https://medium.com/@lopp/how-to-solo-mine-on-bitcoin-s-testnet-6073c917b495)
* [https://www.dash.org/forum/threads/hyper-efficient-pool-lets-test-it-out.40515/](https://www.dash.org/forum/threads/hyper-efficient-pool-lets-test-it-out.40515/)
* [http://www.joshvamos.com/mining-bitcoins-with-p2pool/](http://www.joshvamos.com/mining-bitcoins-with-p2pool/)
* [https://www.reddit.com/r/vertcoin/comments/7591qz/p2pool\_test/](https://www.reddit.com/r/vertcoin/comments/7591qz/p2pool_test/?st=jqpmahu7&sh=5d933955)



