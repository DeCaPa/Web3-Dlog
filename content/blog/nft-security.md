+++
title = "Is Your NFT Collectable Secure and Legitimate?"
description = "The Treat Landscape for an NFT is a Minefield."
author = "MaTTeo DeCaPa"
date = "2021-06-28"
tags = ["web3", "nft", "security"]
categories = ["web3"]
[[images]]
  src = "img/appsec/nft.png"
  alt = "nft"
+++

# What is an NFT?

NFT stands for NonFungible Token.  Think of it is a digital record which has been minted (created) on a blockchain.  Meaning, the file representing "something" that has been recorded on a blockchain. It is very unlikely the NFT itself is stored on a blockchain, rather the transaction details and a reference to the actual NFT location are stored on the blockchain.

There are many potential "gotcha's" associated with NFT's.  This post looks at the NFT landscape.  It is intended to help educate the NFT minter, the collector who purchases directly from the minter, and potential buyers later. Before you decide to swim with the sharks consider the following questions in 3 sections

- **Is It Legitimate?**
- **Can My NFT Disappear?**
- **Ownership**

## Is It Legitimate?

This section covers a few of the ways an NFT might not be the original, may not be legitimate, or fail to have proof that it is the real thing.

### How do I know?

In short, you do not.  At least not without additional proof, that is.  As with real non-digital collectables, the collectable and its provenance could be faked.  The blockchain alone, merely provides an immutable record of the transaction(s), not the legitimacy of the NFT being purchased.  If the NFT has been bought and resold multiple times, it should still be traceable back to the original minter, and you can independently verify the individual/company is the actual entity that originally created it.

Buying thru reputable exchanges, or from a known and verified buyer, limits the risk.  Additionally, reputable exchanges should also have seller rating capabilities.  But even like eBay, and other reputation-based systems, there are ways to deceive and mislead.

### Can someone replicate my NFT?

In short, yes, they could.  In the real world, there are all kinds of faked products, art, and collectables.  In the virtual world of NFT's the same can happen.  The blockchain transaction cannot prove the NFT is real, it only records an unchangeable record of the transaction.  It is not intended to know if the NFT is real or fake.

### Can there be multiple copies of the same NFT?

In short, yes there could be.  Minting is the act of creating an NFT transaction recorded on a blockchain.  With so many exchanges selling NFT's these days, nothing stops an individual from minting the same NFT across multiple blockchains.  

The risk could be mitigated by knowing in advance which blockchain or Dapp the Minter *always* uses.  However, any seller or a criminal could mint a slightly modified NFT on the same or any blockchain.  A common storage location for NFT's is on IPFS. which uses a unique hashing algorithm (more below).  A slightly modified NFT would result in a different hash, making one believe it is original and authentic, when it is only a copy. Now which one is the original?

### Can someone else mint the same NFT?

In short, yes someone could.  Since a blockchain transaction is a public record of the transaction.  A thief has all the information about the transaction available to them to set up a fake or misleading identity and list the NFT for sale again.

## Can my NFT disappear?

In short, yes it could.  It will only stick around for as long as it is stored and supported.  This section discusses some of the potential issues around NFT storage.

Blockchain technology and Web3 in general is in its infancy.  If the developers behind the particular blockchain that recorded your NFT decide to stop supporting the project, the entities processing transactions could potentially cease as well, meaning the database could go away, leaving no record of ownership.

Another scenario would be if the storage location of the NFT was deleted, or in some other manner ceased to exist.  IPFS (InterPlanetary File System) aims to make the file stick around forever in a Web3 sort of way.  While IPFS is also in its infancy, the file (or any file for that matter) is likely to be hosted and cached by a single or related set of nodes that are managed by the Marketplace selling the NFT.  If the Marketplace goes by-bye, so might the storage, and so will your NFT.

While it is not an absolute that it is gone forever, the link from the defunct blockchain will be missing.  It may be possible to execute another block transaction or mint new, to update the reference to the NFT, to keep the NFT on-chain (different or same chain).  But then again, someone else could do that as well before you do.

### My NFT is stored on IPFS, isn't that how it should be stored?

As alluded to in other sections, IPFS (InterPLanetary File System) is focused on content, not a centralized domain, and is a great way to store NFT's.  This means the NFT is assigned a unique identifier called a ContentID.  This ID is unique to the NFT.  If the NFT changes in one way or another, a different hash is generated.  The contentID (a unique hash) will never be the same unless it is the same NFT.  When you purchase your NFT, you may be purchasing the ContentID.  At least that may be what is recorded on chain. Aside from the file going away, as discussed previously, a cloned file with a single pixel changed would generate a different ContentId, even though there is no way to tell which one is the original and which one is the fake.  Other than comparing the ID with the original on-chain you will not know.  The storage node could go down, or malfunction in some way and without active backup nodes, bye-bye NFT.  

The blockchain is where the reference (pointer) to the NFT is stored.  If one or both go away, the NFT you have becomes difficult to prove what you have in your possession is the original.

## What if the marketplace where I purchased my NFT goes out of business?

Not a guaranteed loss of your NFT.  It will still be necessary to maintain the chain of ownership and that the reference to the NFT is still valid.  It is important to  understand exactly how the marketplace conducts business and understand how they manage the lifecycle of an NFT to adequately evaluate the associated risk.

## Ownership

Congrats on your NFT purchase!  It is now a collectable in your crypto wallet.  The same wallet you guard with your private key and/or private phrase.  As previous sections alluded to potential risks, this section attempts to show you what you have.

A strength of blockchain technology is that it is an immutable record of a transaction.  What is stored is the proof that you own the NFT.  The block will contain basic information about the transaction.  For example, the NFT cost, gas cost, wallet addresses involved (yours will be one of them), smart contract information, information about the NFT, date, time, etc.  

### What did I buy, exactly?

Interestingly, what is owned seems to vary by NFT Market.  Here are 2 examples
1. When you purchase a CryptoKittie, you are limited with what you can do with it. [As described in this CryptoKitties Blog post](https://www.cryptokitties.co/blog/post/when-you-purchase-a-cryptokitty-you-get-both-the-kitty-and-its-art/).


2. Let us follow a simple NFT transaction at another marketplace, named [SuperRare](https://superrare.com/artwork-v2/bighorns-24478).  Following the transaction [details](https://etherscan.io/tx/0x9a0b99837b9a15c8451fd54cf81ca2b05470a89b402d5003ce34d91bb7be2b1c) on the block explorer.  We can see that an NFT was minted [#24478](https://etherscan.io/token/0xb932a70a57673d89f4acffbe830e8ed7f75fb9e0?a=24478), and is for sale.  Digging into the token, we can [query](https://etherscan.io/token/0xb932a70a57673d89f4acffbe830e8ed7f75fb9e0?a=24478#readContract) the contract to find a string with the TokenID, representing what was for sale: `https://ipfs.pixura.io/ipfs/QmW2HMPEkkudU9zEzGDJ8ZEhJLx21UDbXTWT1XNCGUEDmE/metadata.json`.  The file points to where the actual NFT is stored.  The NFT is NOT stored on the blockchain, the link above is what is stored.  [Following the link](https://ipfs.pixura.io/ipfs/QmW2HMPEkkudU9zEzGDJ8ZEhJLx21UDbXTWT1XNCGUEDmE/metadata.json)  returns a description of the NFT.  Digging into it you can find where the NFT is actually [stored]("https://ipfs.pixura.io/ipfs/QmeYiwAZpfnFXtMgf8GxaCYfMbvp3V64ec37vrxHkrFpRV/bigHORNS_SR.jpg).  If this site ever goes away, or has something catastrophic happen to it, the NTF associated with the transaction is gone. If you have the file saved on your computer as a backup, that is not what the transaction listed on-chain shows.  You have lost the ability to prove that this is a paid-for collectable, because what is on the chain can't be proven any more.  

Recall, the block transaction references the a file with a reference to the IPFS ContentID of the directory where the NFT resides, as it appears thru an IPFS gateway.  If that gateway goes away, the blockchain reference will not accurately point to the NFT.  However, utilizing the Brave browser, if it remains stored *somewhere* on IPFS, it can still be retrieved `ipfs://bafybeihq2k6oscadxj6mfax6h3ofcjqeu2iseeonget5m6huliaeb4ypza/`, but this is not how it is recorded on-chain.  The assumption remanis that it is stored *somewhere* on IPFS.  Who is going to insure that will happen?

A future article will delve into the details of an NFT transaction to help readers better understand blockchain transactions and how to identify risk.

### NFT disputed ownership?

There is no dispute resolution, arbitration, or global NFT court that exists for NFT's should a dispute arise.  However, it might be good to understand a marketplace's dispute resolution policy.  Also, how crypto is traded, whether there is an escrow, a hold period, or refund process.  

### My NFT shows up in my wallet, that means I own it, right?

Yes, it means you own something.  As previously written, it may not actually end up being what you think, even though it looks like it.

## In Summary

The intended purpose of the FAQ is not to give the criminal minded ideas on how to commit fraudlent activity.  Rather, it is intended to help the individual to better understand the risks associated with NFT's.  As was documented here, having a transaction stored on some public blockchain in and of itself is not the end-all, be-all to NFT ownership.

I personally have not found cases of widespread fraud around NFT's as of this writing.  As Web3 and NFT's gain in popularity, along with a Fear of Missing Out (FOMO), unsuspecting collectors may unwittingly enter into transactions without fully understanding what they are getting into, and that is what the fraudsters are hoping for.

Buyer Beware!
