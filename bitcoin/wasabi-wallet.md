---
description: a privacy-centric Bitcoin wallet
---

# Wasabi Wallet



{% embed url="https://www.wasabiwallet.io/" %}

{% embed url="https://www.reddit.com/r/WasabiWallet/" %}

{% embed url="https://en.bitcoin.it/wiki/Wasabi\_Wallet" %}

### Wasabi CoinJoin

CoinJoin is a technique for improving the fungibility of bitcoins and the privacy of bitcoin transactions.

CoinJoin works by providing a trustless venue for many users to provide inputs and outputs to a bitcoin transaction; if the outputs are all of the same size, it's not possible to link a particular input—which may be tied to personally identifiable information, like a centralized exchange account or a string of other transactions—to a particular output.  The outputs from a CoinJoin can be spent without worrying that participants in your previous bitcoin transactions can see your future transactions \(and vice-versa!\).  This makes bitcoin more cash-like: your hairdresser today can't see where you bought a taco last night.

Wasabi provides a built-in CoinJoin service.  The service allows you to choose the size of the "anonymity set" that your output is part of—the number of equal-sized outputs that are indistinguishable from your output.  You pay the regular bitcoin transaction fees plus a CoinJoin market fee of 0.003% _per anonymity set_.  This means that if you want your output to be indistinguishable from 100 other outputs, you will pay a fee of 100 x 0.003% = 0.3%.  This fee isn't something to feel bad about—you're increasing the fungibility of bitcoin, increasing your own privacy and the privacy of others, and providing funds to developers that are building a valuable tool.



