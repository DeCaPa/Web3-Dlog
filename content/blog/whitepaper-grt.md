+++
title = "The Graph (GRT) Whitepaper Review"
description = "Making Web3 Queryable"
author = "MaTTeo DeCaPa"
date = "2021-08-15"
tags = ["web3", "GRT", "crypto", "dApps"]
categories = ["web3", "infrastructure"]
[[images]]
  src = "img/whitepaper/grt.png"
  alt = "The Graph"
+++

## Premise

Searching for meaningful information from blockchain data and decentralized storage (IPFS) is extremely difficult. To begin, data stored on a blockchain is transactional and based sequentially upon when the transaction was added to the chain.  A traditional database is relational but blockchains are not.  Imagine having to search thru every block beginning with the genesis block to the most recent to find what you are looking for.  It will not only be slow, but the amount of processing and transformation into something meaningful is cumbersome and requires that you do it all yourself.  Not to mention, the solution would be centralized and proprietary.  

## The Graph Value Proposition

Originally defined as a _Decentralized Query Protocol_, The Graph provides the tools and the community network to create a simplified and fully decentralized means to query data that has been indexed into what is called a _subgraph_.   Data in context is _information_, and the capability to query information is what makes The Graph so valuable for use in the Web3 dApp universe.

## Technology Categorization

* **Type:** Web3 Query and Index.  A means to provide dApps with decentralized-sourced data (blockchain and storage) upon which to easily use.  A decentralized network for providing data in context, i.e. providing _Information in a queryable way_.  The specific information is termed a _subgraph_.
* **Project Differentiator:**  Current approaches require dApp developers to create their own solutions.  The Graph provides the tools and the network community to simplify inclusion of blockchain information into dApps.
* **Original [Whitepaper](https://github.com/graphprotocol/research/blob/master/papers/whitepaper/the-graph-whitepaper.pdf)** and current [documentation](https://thegraph.com/docs/).
* **Consensus:**  Proof of Indexing.  I think of this as the quality of information the subgraph provides.  The better it is, the greater the value.  If it is deemed untrustworthy it risks getting slashed.
* **Token:** GRT.  It is used for all aspects within The Graph network.  Paying for a query, as a staking coin, to compensation for all the entities which are needed to make the network community to operate.

## The Network Entities

There are several entities that make up The Graph Network.   The Graph calls them Network Roles.  Images taken from [TheGraph.com](https://thegraph.com).

{{< rawhtml >}}
  <center>
    <img src="../img/subgraph-developer.PNG" width="100" height="100" alt="a subgraph developer" />
    <img src="../img/subgraph-indexer.PNG" width="100" height="100" alt="a subgraph indexer" />  
    <img src="../img/subgraph-curator.PNG" width="100" height="100" alt="a subgraph curator" /> 
    <img src="../img/subgraph-delegator.PNG" width="100" height="100" alt="a subgraph developer" />
  </center>
{{< /rawhtml >}}

### End User

The Client is the dApp running on the end user's device that queries a particular subgraph.  The end user receives the information which is provided thru the particular dApp calling it.

### Developer

It is a developer who creates a subgraph.  The developer indexes based on a smart contract on a Graph-supported blockchain. The subgraph is then deployed to a Graph Node.

Also, it is the developer who builds a dApp to query a subgraph thru a GraphQL endpoint. Accomplished in much the same way a developer will program a call to an API, using GraphQL


### Indexer

Indexers are Node Operators.  They provide indexing and processing services.  The Indexer is required to stake GRT to operate a node.  At time of this writing, the minimum amount is 100,000GRT.  Indexers can also have GRT delegated to them from the Delegators.  Think of this as Delegated Proof of Stake (DPOS), See Delegators below.

Indexers earn query fees and index rewards.  The Indexer selects which subgraphs to index, in part based on what curators think about a particular subgraph.  

Indexers use the Curators recommendations (signal) to process subgraphs as a determinant of which ones to Index.

### Curator

Curators signal subgraphs that they feel should be indexed. Think of this as the Influencer group, with "skin in the game".  Curators will look at [The Graph Explorer](https://thegraph.com/explorer/) and determine if the subgraph has enough value to it to stake GRT on it.  The curator stakes GRT on specific subgraphs to earn royalties.  A developer is likely to curate his own subgraph.

Becoming a curator requires depositing GRT following a bonding curve to mint shares of the subgraph.  The amount of minted shares is the proportional size of your ownership.  Since signaling uses a bonding curve to determine your subgraph shares, the sooner you decide to Curate a subgraph, the greater the potential reward.  A developer will be first in, because they wrote it and believe it contains great potential.  If you think it's a great subgraph too, you will want to signal as early as possible.  

There are risks associated with Curators.  Risks such as a bad or buggy subgraph.  A subgraph that is not used will not earn query fees, so no rewards for you. You are subject to a 2.5% curation tax that you will not get back.

In essence, you are depositing GRT (staking), to mint shares of the subgraph (ownership shares in return).  The shares proportionately allocate the royalties that are earned for the subgraph.  Getting in early to a particular subgraph means you'll need to stake less GRT than someone who gets in later.  To unsignal, you will need to burn your subgraph shares to get your GRT back after a waiting period.

### Delegator

A Delegator stakes GRT to Indexers. As stated above, this is similar to DPOS when it comes to staking governance tokens to allow others to vote on your behalf.  The benefit of doing this is that you earn a portion of the Indexer rewards and the Query Fees.  So, if you own GRT and want to have an opportunity to earn while hodling, you can become a Delegator.  

__Understand everything before you do it!__
* There is a charge (.5%) to delegate. 
* There is an unbonding period of 28 days before you get your GRT back, and you stop earning query fees.
* __Choose your Indexer wisely!__  The indexer decides your cut. They can't steal your GRT, but they can take advantage of you in some ways. All this info is found in [The Graph Explorer](https://thegraph.com/explorer/).

The Delegator role is the path of least resistance and the least technical to become a player in The Graph Network.  Do you want to know more about the Delegator role?  Here is a great  [introductory video](https://www.youtube.com/watch?v=2G7S2gdURdc) for prospective Delegators.  

## GraphQL Security Considerations
It is no coincidence The Graph's name comes from the Graph Query Language (GraphQL).  GraphQL is a carryover technology from the Web2 world and was developed by Facebook as an alternative to JSON for querying API's.  Secure development considerations also apply in Web3. An indexer isn't going to list your subgraph if they think it is a security risk.  [OWASP API Security](https://owasp.org/www-project-api-security/) is your friend when it comes to subgraph development.

* Validate Input
* Add pagination to limit data being returned. It reduces unexpected usage costs, keeps queries performant, and keeps indexers happy.
* Enforce rate limiting based on IP
* Implement timeouts to limit resource usage.  It will also keep your indexers happy and will help reduce complaints within The Graph network keeping everyone else happy.
* Evaluate your code for nested queries.  Nested queries are used in Denial of Service attacks.  
* Remember to disable excessive error messages in production environments to limit risky information disclosure.

## Concluding Remarks

Web3 developers face many challenges when architecting and developing data-rich dApps.  Retrieving meaningful information from across the decentralized web is a huge challenge.  The Graph provides a sustainable network ecosystem to query blockchain data by means of a simple GraphQL query from within a dApp.
