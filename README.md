# TurtleCoin REPL

Simple fake TurtleCoin blockchain to learn/test against.

# Why?

We have API docs, they are an awesome resource, however nothing beats practical and concrete experience. Setting up everything needed to run commands against the TurtleCoin network is not that difficult, however then you need coins to take the next step to do transactions.
So just run a testnet, that's not that hard! True, however TurtleCoin doesn't currently maintain a `--testnet`. There are running [testnets](https://github.com/turtlecoin/testnet), however again involves setting up a bunch of stuff.

So this project aims to bring iterative development to the masses via an [ActionHero](https://www.actionherojs.com/) node.js based REPL.

# What

As mentioned above this is a tool built on the [ActionHero](https://www.actionherojs.com/) framework that is built on node.js. All it does it pretend to be a blockchain, it emits blocks that look like blocks, transactions that look like transactions.

It replicates the HTTP JSON APIs of TurtleCoind and walletd. It does it at a basic level, it is a simulator. A bunch of random values are generated at startup and from those values the blockchain hums along doing blockchain things. None of the crypto is implemented so anything that needs to solve crypto problems won't work with this. However all of the transaction and basic getting on block info is functional.

# How?

Simply install the package using NPM/Yarn and run it.

A workable config is included and mirrors the characteristics of the TurtleCoin network.
Check comments in the config file for details.

## Transactions

When there are addresses in the network they create transactions at random, the transactions go into a mempool just like they do on the real network. Addresses can be tagged for receiveing block rewards or not.

## Blocks

When started the engine hums a long generating blocks as per the config. The blocks when created will pull transactions out of the mempool and produce the block as per the config params. Block rewards are rewarded either to the addresses configured or to nowhere, the coin supply will still increase accuratley and be tracked though.

## Wallets / Addresses

The whole point of this REPL is really to address this part, this is the part where apps are made against. Having a tool that can be tested against and respond logically in step with the real items is what make turtlecoin-repl useful.
Addresses/Containers can be made at will and automatically as well as manually specified in the config.

# Websockets?

Yes, you also get websocket access to a bunch of the methods, becuase if you use [turtlecoin/walletd-ha](https://github.com/turtlecoin/walletd-ha) you get websockets. This is very useful for also learning websockets too.


# License

Copyright (c) 2018 Nicholas Orr

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
