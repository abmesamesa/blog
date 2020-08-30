A gentle introduction to Blockchain
===================================

Abrahán Mesa - Posted on January 10, 2019

At some point I became interested on the blockchain. Here there are some notes I took while learning.

Main sections covered in this article:

-   Why Blockchain
-   Blockchain as a data model
-   Installing Bitcoin software
-   Bitcoin core nets
-   Bitcoin debug console

Why Blockchain
--------------

These are a few reasons:

1.  It is reinventing the Internet.
2.  It is building the digital economy.
3.  It is challenging.
4.  The demand for open positions gigantic.

Some industries could drastically change:

1.  Personal identification.
2.  Medicine: patient information.
3.  Finance: send money across the world.
4.  Supply Chain.
5.  Government.

It brings us new ways of sharing data more secure, cheaper and transparent without large companies storing our data.

The blockchain is a shared database that contains a list of transactions made by the users where the database belongs to the network.

Bitcoin as example

Open to anyone, it can establish the trust needed to the transaction.

We often give personal information to companies in exchange of the services they provide. We can easily lose control of our data which is in one single location, "easily" hackable. The blockchain data is shared by people in the network, it is encrypted and it is nearly impossible to hack.

Today knowing all the data about a single car can be extremely messy. Using the blockchain we could share the details of the car from the very beginning. In the blockchain:

1.  The information is anonymous very often.
2.  The information belongs to its proprietaries, the participants of the chain.
3.  The information is stored securely, encrypted.
4.  The transactions history is trusty and precise.
5.  A group of transactions big enough form a block which is added to the chain. Each block contains a hash which depends on the previous block in a way that makes impossible to change any of it. The hash identifies the data within the block.

Potential flaws on financial transactions today

1.  Many steps make the whole process slow.
2.  Many transactions need to be secured.
3.  Different protocols need to be defined (interfaces between people and banks, between banks...).
4.  The whole process depends on a single node, the bank.
5.  No easy way to see if transactions have been tampered with.
6.  Transaction time is dependent on the banks to validate the transactions.

If we create a shared ledger we do not need to trust a single bank that would or would not give as personal information. On the other hand, with the blockchain we will not have intermediaries of financial services that could charge fees on each transaction (like Paypal), each time they communicate to banks.

Bitcoin

Bitcoin is an implementation of the blockchain. A digital currency that facilitates transactions. [An study of Heber and Stermetta](https://www.anf.es/pdf/Haber_Stornetta.pdf) already defined the idea of a chain of timestamped blocks. After that a very [famous paper](https://bitcoin.org/bitcoin.pdf) of Satoshi Nakamoto defined the Bitcoin like a peer to peer electronic cash system. Here is an extract:

> A purely peer-to-peer version of electronic cash would allow online payments to be sent directly from one party to another without going through a financial institution. Digital signatures provide part of the solution, but the main benefits are lost if a trusted third party is still required to prevent double-spending. We propose a solution to the double-spending problem using a peer-to-peer network. The network timestamps transactions by hashing them into an ongoing chain of hash-based proof-of-work, forming a record that cannot be changed without redoing the proof-of-work. The longest chain not only serves as proof of the sequence of events witnessed, but proof that it came from the largest pool of CPU power. As long as a majority of CPU power is controlled by nodes that are not cooperating to attack the network, they'll generate the longest chain and outpace attackers. The network itself requires minimal structure. Messages are broadcast on a best effort basis, and nodes can leave and rejoin the network at will, accepting the longest proof-of-work chain as proof of what happened while they were gone.
>
> *Satoshi Nakamoto*

Hashing

A digital fingerprint for information. A unique string of letters and numbers that represents a set of data. A function that generates hashes is SHA256, used by Bitcoin for example to be able to identify a block within the blockchain. Here an example written in javascript code:

```js
let sha256 = require('crypto-js/sha256');
const stringToBeHashed = "Blockchain Rock!";
const objectToBeHashed = {
    id: 1,
    body: "With Object Works too",
    time: new Date().getTime().toString().slice(0,-3)
};
function generateHash(obj) {
    return sha256(JSON.stringify(obj));
}
console.log(`SHA256 Hash: ${generateHash(stringToBeHashed)}`);
console.log(`SHA256 Hash: ${generateHash(objectToBeHashed)}`);
```

Blocks

They have a list of transactions to be added to the blockchain.

A block also has a header that contains:

1.  Previous blocks hash.
2.  Time: A solution to the [double-spending problem](https://en.wikipedia.org/wiki/Double-spending).
3.  Merkle root: A hash representing every transaction in the block.
4.  Nonce: Arbitrary number that can only be used once. All the blocks of data combined with the hash value have to produce a hash meeting some conditions (pow). The computer has to guess the nonce in order to generate a block. This conditions are a number of zeros on the left side of the hash (more zeros, more difficult to calculate). Another condition is the maximum size of the block, determined by the developer.

Blockchain

1.  It is just a part of the blockchain framework (where the information is stored).
2.  The information is permanent and it can not be updated. The data is immutable.
3.  The information is divided in blocks that are related using hash values.
4.  Each block has a number associated which refers to the position of the block in the chain.
5.  Any change in the block triggers a change in the hash value and therefor a change in the rest of the blocks.
6.  The first block in a chain is called "Genesis block".

Distributed Peer to peer network

The blockchain is based on a distributed peer to peer network. The users (nodes) can send information between them directly. The information belongs to the members of the network. There is not a central node. Everyone in the network has access to the information equally Vs network centralized / decentralized (multiple centers).

Memory Pool / Mempool

A place for transaction to wait to be included in the blockchain (backlog of information). It is also a waiting place of unconfirmed transactions. (The ram memory of the nodes).

The miners have to validate the transactions before to be added, so it exists a queue of untreated transactions.

There are some reasons for a transaction to quit the queue:

1.  The transaction is expired.
2.  The maximum size of the mempool is reached and a new transaction with higher fee (a tip for the miner) arrives, so the transaction with lower fee quits the mempool.
3.  The transaction is included in a bloc.
4.  The transaction has conflicts with another transaction in the block.

Consensus

What transactions are valid? How the network reaches agreement?

See the [Bizantine general's problem](https://en.wikipedia.org/wiki/Two_Generals%27_Problem).

The blockchain needs to establish trust between nodes when it is impossible to communicate easily. The whitepaper of the bitcoin gives a solution to this problem: Proof of work (a way of reach consensus without central authority) but there are a few of them.

*Proof of work*

Whoever puts in the most work to contribute to the system is the most trustworthy. The work of a node demands a lot of resources but it is easy to validate the work by other nodes. Finding a hash with more leading zeros is a hash more specific and much more time is needed to get it. The miners search the nonce to generate the hash. The number of zeros on the left is known as the "block difficulty". The difficulty can be changed if the blocks are being built too quickly o too slowly. The idea is to need 10 minutes (a balance between speed and security). If the blocks are generated too quickly, hackers could find ways to validate false transactions. If the blocks are generated too slowly there would be too many transactions waiting in the mempool.

There are two main concerns with this algorithm:

1.  Energy consumption high.
2.  The monopoly of trustworthy miners could lead to the centralization (pools sharing resources and gains centralized the network).

Bitcoin uses proof of work.

*Proof of stake*

It focuses on giving votes to members, depending on how much stake they have in the success of the chain.

There are not miners in this algorithm. All the coins exist at the beginning, there are only "validators". The validators bet theirs coins to be able to validate a block and to get more according to the bet. If the block is not validated the validator lost the money. The validator having more coins has a great probability of getting the next block to validate.

Some advantages are the security, a reduced risk of centralization and energy efficiency.

An important issue is:

1.  Nothing at stake: Validators bet several blocks at a time in a way that they never lost and they are always at the top of the validators list aiming to modify the transactions.

A solution:

1.  Slasher: Validators who place bets in several blocks at the same time are penalized.
2.  Punisher: It penalizes validators adding blocks on forks.

It is used by Casper, Dash or Lisk.

*Delegate Bizantine fault tolerance DBFT*

It assigns roles to the nodes to help coordinate consensus. There are not miners, there are specialized nodes (regular nodes and consensus nodes). A consensus node is chosen randomly from the pool of consensus nodes (speaker), the speaker creates a new block and proposes it to the rest of the consensus nodes (delegates voted for the rest of the nodes) who must approve it, otherwise a new speaker is chosen and the process starts again.

Advantages:

1.  There is not a need to solve cryptographic problems.
2.  It is resistant to forking because there is only one block being added at a given moment.

Issues:

Dishonest speaker: It depends on honest delegates to validate or not, it depends on the delegate to vote honest speakers and it depends on the users to vote honest delegates.

Dishonest delegate: If there are several dishonest delegates they could technically validate a block that is not valid. If most of the delegates is honest the block will be refused and a new speaker will be chose.

This method is used by Neo.

Blockchain transaction

*Identity*

1.  Only someone who owns the money has access to spend it.
2.  The transactions cannot be traced.
3.  It should be possible to share the identity so others can make transactions with me.

We get that using a wallet:

1.  Private key: it allows spend your money from your wallet.
2.  Public key: publicly sharable key allows people to send you money.
3.  Wallet Address identification unique you can share with others and allows you to make transactions.

The public key is generated from the private key. For instance Bitcoin uses the algorithm [ECDSA](https://en.wikipedia.org/wiki/Elliptic_Curve_Digital_Signature_Algorithm) to generate public keys, which is extremely difficult to hack nowadays.

The wallet address allows the transactions not to be traced. Bitcoin uses two algorithm to get the wallet address:

> public key -> sha256 -> 256 bits number -> ripemd160 -> 160 bit number (Wallet address)

Then we take the number and make it more readable:

> base58check -> base58 number.

*Wallet types*

Deterministic

-   Sequential: derived sequentially from a single seed, it can be traced back to that seed. Private key is sha256(seed + n), n are 128 random bits. With the seed the private keys can be regenerated.
-   Hierarchical: Derived in a tree structure. Private key is sha256(address(publickKey(seed)+n)). It allows us to have a lot of keys, for example for a company with many departments.

Non deterministic

-   Randomly generated private keys with numbers between 1 and 2^256. For privacy is better to generate a new key for each transaction and back up to the wallet, so no one can track links between the addresses.

*Private keys*

A 256 bit random number between 1 and 2^256 which can be represented using different formats like Hex, WIF wallet import format (base58check) or Wiff compressed. To be generated and obtain unique keys a random non repeatable method is needed so a source of entropy is also needed. There is several ways to generate keys, like using some software like [Electrum](https://electrum.org/#home).

*Sign a transaction*

It establishes a proof of ownership for each transaction on the blockchain. Before a transaction is submitted to the network a signature is needed to establish the ownership of the money (Bitcoin example). The signature is made using a wallet address (bank account number like) which is linked to a private key. The transaction is sent as a UTXO (Unspent transaction output). Each transaction input will need to be converted into a transaction output that contains the proof of ownership using the private key. To create a transaction output you need to have the sum of the input transactions which are equal to or greater than the value you are sending. So sometimes we want the change back, which is possible.

*Lifecycle*

1.  A wants to send 1 bitcoin to B.
2.  A gets the wallet address of B.
3.  A creates a new transaction of 1 bitcoin plus optionally, transaction fees for miners.
4.  A verifies his information and sends the transaction.
5.  The wallet starts the transaction sign algorithm which signs his transaction using his private key.
6.  The transaction is broadcasted to the memory pool in the network (the public key, the signature and the message).
7.  The receiving node then checks using the verification algorithm that the message has been signed by the sender.
    -   Authentication (message sent by a known sender).
    -   Integrity (message not altered).
    -   Non-repudiation (The sender cannot deny sending the message).
8.  The transaction is eventually accepted by miners, including it in a block and creating a hash value for the block.
9.  The block is added to the blockchain.
10. The transaction is accepted as a valid transaction in the blockchain.
11. B gets the money.

Blockchain as a data model
--------------------------

Blockchain dataset vs traditional databases

Traditional databases:

1.  Have a centralized network.
2.  It can create, read, update and delete.
3.  They are mutable (data can be updated after being added).
4.  Authorization is centralized and transparency is low.

Blockchains:

1.  Distributed (control given to nodes, need consensus).
2.  It can read, append and validate (accurate historical record and faster read and write).
3.  They are immutable (permanent historical record but high storage space).
4.  Authorization is distributed (more secured).
5.  Transparency is generally high (everyone has access but no permission control).

Do I need a blockchain. Some useful questions to be responded.

1.  Do I need a database?
2.  Does it require share write access (users will need access to add or write to the database)?
3.  Will I need to create the trust between users?
4.  Can I operate without trusted 3rd parties?
5.  Can I operate without control over permissions?

Blockchain types

Who is allowed to participate in the network, execute the consensus protocol and maintain the shared ledger?

*Public*

Everything is open, everyone has access and can verified.

*Private*

The functionality of a blockchain but with access control.

*Hybrid*

Some transactions are public and others are private.

Private and Hybrid are a recentralization of the information.

Questions before choosing one:

1.  Will transactions be public? -> if yes, public
2.  Will other companies need access to your data? -> if no, private
3.  Should some information be public while other information is restricted? -> if yes, Hybrid

Blockchain network

Blockchain uses a peer to peer (P2P) network vs Client-Server used by traditional applications.

*Client-Server* brakes up tasks between providers and requesters. The server is a centralized resource that contains the information users want to access. The client make requests. Web servers or file servers are exemples. Data is controlled in centralized servers. It gives fully control over permissions. Overall considered more stable because a central owner can add or remove computation and storage to meet the demands of the client. A failover system is built in into the this model.

*P2P* is a network of computers that share access to files with each other. So every node is the server and the client. Is generally considered less stable, especially when is getting started. The network itself is not contributing to the security but the cryptography.

Block structure

-   Block Header: Metadata about the block like the hash value.
-   Block Transactions: all the block transactions information. You can explore block content using sites like [blockexplorer.com](https://blockexplorer.com)\
    The first transaction in the list (the oldest) is called "Coinbase". The interface renders the data in a pretty way, but as programmers will use data programmatically, in json format for instance.

*Exploring a block of bitcoin data.*

-   Blockexplorer.js is a library allowing us to get a block by hash (or raw block, get the block hash by height and many other things.

An example of code getting a block from an index:

```js
const be = require('blockexplorer');
function getBlock(index) {
    let hash = be.blockIndex(index);
    hash.then(function(value){
        return JSON.parse(value).blockHash;
    }).then(function(value){
        return be.block(value);
    }).then(function(block){
        console.log(JSON.parse(block))
    });
}
```

Installing Bitcoin software
---------------------------

The whole process is explained [here](https://bitcoin.org/en/full-node#initial-block-downloadibd).

This is a bitcoin wallet that fully validates transactions and blocks.

By downloading bitcoin core I become a bitcoin node (this is not the same as miner). A client that is downloading the blockchain and validating using the local computer.

I used this [link](https://bitcoin.org/en/download).

This is a very heavy installation, currently the bitcoin blockchain is ~200GB and it continues to grow every month. You can use pruning to reduce the space required by creating a file "bitcoin.conf" in the blockchain data folder with this content:

```js
prune=550
```

You can find default locations fo the blockchain data folder [here](https://en.bitcoin.it/wiki/Data_directory#Linux). In my case as I am running linux is:

```js
~/.bitcoin
```

Another solution to save disk space might be to use another network as testnet or regnet.

Some people install the blockchain on an external hard drive to keep the machine HD clean.

After downloading it, I just need to untar the file:

```js
tar xvzf bitcoin-0.17.0.1-x86_64-linux-gnu.tar.gz
```

Install it:

```js
sudo install -m 0755 -o root -g root -t /usr/local/bin bitcoin-0.17.0/bin/*
```

And run the GUI by executing this:

```js
bitcoin_qt
```

I'll start downloading the blockchain from the very beginning. You can close the application and the sync will continue when you run the application again.

Within the config file ~/.bitcoin/bitcoin.conf you may add a configuration line in order to access a certain network (testnet or regnet). Mainnet is default, so you can comment the lines if you like to access to it.

```js
#~/.bitcoin/bitcoin.conf

#testnet=1
regtest=1
```

Bitcoin Mainnet: Primary Network where real live transactions take place.\
Bitcoin Testnet: Alternative Bitcoin blockchain that provides a test environment for applications.\
Bitcoin Regnet: Alternative test network for testing bitcoin applications locally.

Bitcoin core nets
-----------------

Bitcoin has two main functions:

1.  Bitcoin as a network. Create and validate transactions.
2.  Bitcoin as a software. Bitcoin core is an implementation of bitcoin that encompasses all of the software behind bitcoin.

To clear the confusion, Bitcoin Core was created to distinguish it from the Bitcoin network.

Features:

1.  Connect to the network.
2.  Validate the blockchain.
3.  Send and receive bitcoins.

We can access a test platform to learn how to use the core. And we use the Debug Console provided to interact with the data on the bitcoin blockchain.

Different environments are provided to test our software as developers:

1.  Mainnet
    -   Primary network where live transactions take place.
    -   Coins have real value.
    -   There are peers.
2.  Testnet
    -   Alternative blockchain that provides a test environment.
    -   Testnet coins have no real value.
    -   There are peers.
3.  Regnet
    -   Alternative test network for testing applications.
    -   It uses coins with no real value.
    -   There are not peers.

Mainnet vs Testnet

Purpose: Production / Testing\
Environment: Public / Public\
Peers: Entire network / Testers\
Size: ~200GB / ~14GB\
Block Creation: 10 minutes both cases\
Value: Full value / No value\
Public Key Prefix: 1 / m or n\
Block Difficulty: Full / Half of mainnet

Testnet vs Regnet

Purpose: Testing / Testing\
Environment: Public / Private\
Peers: Testers / None\
Size: ~14GB / ~0GB\
Block Creation: 10 minutes / Instantly\
Value: No value for both\
Public Key Prefix: m or n for both\
Block Difficulty: Half of mainnet / none

Bitcoin debug console
---------------------

In order to use bitcoin in the command line I previously needed to start this (otherwise I get an error):

```js
bitcoind
```

then I can play with:

```js
bitcoin-cli
```

This will give you some useful information:

```js
bitcoin-cli help
```

I configure my file bitcoin.conf to use the testnet. But some commands are only really usefull on the regnet.

Then I start using the commands available like this one:

```js
bitcoin-cli getbestblockhash

00000000000000ec0c4ca095989933fe49e4723a1933c2272f4171aa64693e96
```

Some interesting commands.

###### Explore the blockchain

```js
getblockchaininfo
getblockcount
verifychain
```

###### Hashing

```js
getblockhash height
```

It returns the hash of a block (height of the block -a sequential number- is required as an argument)

```js
getnetworkhashps
```

It returns an estimated network hashes per second based on specified number of recent blocks. It is useful for knowing when the network is running faster or slower.

```js
getbestblockhash
```

The hash of the last block synced.

###### Blocks

```js
getblock hash
```

You first need to get a hash of a block using *getblockhash*.

```js
getblockheader hash
```

It gives you the block without transactions.

```js
generate nblocks
```

It mines a number of blocks to an address in the wallet. It can be useful using the regnet. Remember to update the config file *bitcoin.conf* before.

```js
regtest=1
```

###### Wallets

```js
getwalletinfo
```

It provides information about the current wallet.

```js
listwallets
```

It creates a list of currently loaded wallets.

```js
walletpassphrasechange oldpass newpass
```

It updates the passphrase.

###### Mempool

```js
getmempoolinfo
```

It returns details on the active state of the transaction memory pool.

```js
getrawmempool
```

It returns a list of the transactions ids in the mempool.

```js
getmempoolentry
```

It returns mempool data for a given transaction.

###### Transactions

```js
getchaintxstats
```

It returns compute statistics about the total number and rate of transactions in the chain.

```js
getrawtransaction
```

It returns the transaction data in a computer friendly format.

```js
listtransactions
```

It returns a list of transactions for a given account.

###### Signature

```js
signrawtransaction
```

It signs inputs for a raw transaction which is formatted to be read by a computer. In version 18 will be removed so we will use *signrawtransactionwithkey* and *signrawtransactionwithwallet* instead.

```js
signmessage
```

It signs a message with the private key of an address.

###### Network

```js
getnetworkinfo
```

It gets a high level overview of the network state you are currently on.

```js
getpeerinfo
```

It returns data about each connected node.

```js
getconnectioncount
```

It returns the number of connections you have to other nodes (number of peers).

###### Mining

```js
getmininginfo
```

It returns an object with mining-related information, for example the block that is currently being mined.

```js
prioritisetransaction
```

It accepts the transaction into mined blocks at a higher or lower priority.

```js
getblocktemplate
```

It returns data needed to create a block.
