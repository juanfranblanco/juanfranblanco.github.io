---
layout: post
title: Setup your own testnet in Ethereum
date: '2015-09-09 12:37:27'
---

This post will cover the steps to create your own testnet in Ethereum using Geth. From creating your own genesis to start mining.

* Install the [latest version of Geth from Github](https://github.com/ethereum/go-ethereum/releases)

* Create a new genesis file and save it next to geth as **dev_genesis.json**

<pre><code class=language-javascript>
{
    "nonce": "0x0000000000000042",
    "difficulty": "0x40000",
    "alloc": {
            "b285c812311ecad1111bc859a3ccb538f5531766": {
            "balance": "10000000000000000"
        }
    },
    "mixhash": "0x0000000000000000000000000000000000000000000000000000000000000000",
    "coinbase": "0x0000000000000000000000000000000000000000",
    "timestamp": "0x00",
    "parentHash": "0x0000000000000000000000000000000000000000000000000000000000000000",
    "extraData": "0x",
    "gasLimit": "0x4c4b40"
}
</code></pre>

The genesis has assigned **b285c812311ecad1111bc859a3ccb538f5531766** 1 Ethere

* Open geth using this command

```
> geth --rpc --networkid=39318 --maxpeers=0 --datadir=devChain --genesis dev_genesis.json console
```

Using this command geth will be opened with no peer connections, using a different chain and genesis.


* Create a new account

```
> personal.newAccount("passphrase")
```


* Allocate funds to your account by modifying the genesis

You can allocate the account some funds by modifying the genesis.
Copy the account address from the previous step, exit (type exit) and modify the genesis allocation.

<pre><code class=language-javascript>
{
    "nonce": "0x0000000000000042",
    "difficulty": "0x40000",
    "alloc": {
            "PUT-HERE-YOUR-NEW-ADDRESS": {
            "balance": "10000000000000000"
        }
    },
    "mixhash": "0x0000000000000000000000000000000000000000000000000000000000000000",
    "coinbase": "0x0000000000000000000000000000000000000000",
    "timestamp": "0x00",
    "parentHash": "0x0000000000000000000000000000000000000000000000000000000000000000",
    "extraData": "0x",
    "gasLimit": "0x4c4b40"
}
</code></pre>

* Start mining. 

To start mining, just type
```
> miner.start()
```
this will generate the DAG and start mining.

* Checking your balance
```
balance = web3.fromWei(eth.getBalance(eth.accounts[0]), "ether");
```

* Getting latest releases (solc, eth, mix):
https://github.com/ethereum/webthree-umbrella/releases