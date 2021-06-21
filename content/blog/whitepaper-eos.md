+++
title = "EOSIO Blockchain Enables Secure and Permissioned Smart Contracts"
description = "A Blockchain for building dApps"
author = "MaTTeo DeCaPa"
date = "2021-04-11"
tags = ["web3", "blockchain", "dApps", "crypto"]
categories = ["web3", "blockchain"]
[[images]]
  src = "img/whitepaper/eosio.png"
  alt = "eosio"
  stretch = "horizontal"
+++

## Premise

The EOSIO blockchain is utilized by several decentralized projects.  Understanding the permissioning capabilities of the platform will help to gain an understanding of not only the EOSIO platform, but also how permissioned blockchains differ from fully permissionless blockchains.

## EOSIO Value Proposition

EOSIO is a platform for building and vertically scaling decentralized applications (dApps).  EOSIO creates an operating-system-like platform from which dApps can be built and maintained.  EOSIO considers authorization, RAM storage, database, and asynchronous communication clusters scaling to millions of transactions per second.  

In contrast to Ethereum-based smart contracts, EOSIO-based dApps do not necessarily need to charge the user fees for interacting with the platform.  Rather, costs for interacting with the platform are paid for by either the dApp creator or the account owner.  Not all use-cases require a public user to pay for a particular service.  Consider consortium, enterprise, internal, or private decentralized systems use cases.  Real Estate, Insurance and Healthcare come to mind as examples where one would want data to be protected and not publicly accessible.  Other use cases could follow a web2 (or web2.5) strategy where dApps could implement legacy monetization strategies.   EOSIO attempts to be applicable to any number of use cases.

## Technology Categorization

* **Type:** level one, permissioned (restricted) Blockchain
* **Project Differentiator:**   Built with developers in mind.  It aims to be a decentralized computing operating system while applying a security and access model to enable more use cases than public-only blockchains.
* **[Whitepaper](https://github.com/EOSIO/Documentation/blob/master/TechnicalWhitePaper.md)**
* **Consensus:**  Delegated Proof of Stake (DPOS)
* **Token:** EOS.  Each project which forks the EOSIO codebase will have its own crypto currency.  By looking at the blockchain explorer, blocks.io, we can see a list of projects each with their own EOS based token.  

{{< rawhtml >}}
  <center><img src="../img/EOSIO-blockchain-implemenations.PNG" alt="EOSIO Blockchain implementations" /></center>
{{< /rawhtml >}}

## Security Considerations

### Accounts

Accounts identify a participant on the EOSIO blockchain.  A participant can be an individual or a group.  They also represent the smart contract actors that push and receive actions to and from other accounts in the blockchain.  Actions are contained within transactions whose actors are accounts.

### Permissions

Permissions control what accounts can do, and how actions are authorized.  Account permissions are used to authorize actions and transactions to other accounts.   Permissions can be structured so that a particular named permission’s authorization can be satisfied with implicit authorization (if the parent is authorized, then the child is implicitly allowed).

The permissions table includes all permissions and any associated hierarchy dependencies within those permissions.  Each permission is linked to an authority table.  The table utilizes “thresholds” before an action associated with a permission can execute.  The authority table associated with the permission contains not only the account’s threshold weight, but also any accounts which may execute on behalf of the account permission.  The weighting structure grants more trusted users a greater weight, or requires accounts with lesser authority to collectively participate (add together) to meet a certain weight.  The weighted solution may result in privilege escalation by a lower weighed user increasing weight to gain greater privileges.  Understanding how the platform minimizes this threat is outside the article’s scope.  

{{< rawhtml >}}
  <center><img src="../img/EOSIO-perms.PNG" alt="EOSIO accounts authorities permissions" /></center>
{{< /rawhtml >}}

All accounts will have Owner permission and Active permission.  All permissions utilize public key and private key pairs for each permission.  Private keys associated with each permission need to be protected.  The Owner permission private key should be kept in cold storage since it should only be used for account recovery.  Like a Root account, it should not be used to administer or operate the account. The Active permission would be used to make account changes.  Additional permissions can be created (along with key pairs) to do whatever may be necessary.   From a security perspective, this is where least privilege must come into play.   For any of these permissions, the private key is utilized to sign the transaction in order to validate the public key.

It is this mechanism which determines how Actions and Handlers behave when they are received.  It is this interaction between (and among) accounts with the defined permissions associated with the Actions and Handlers which define a smart contract.   The permissioned architecture is what allows transactions to be secured and how Confidentiality and Integrity is upheld.

## Concluding Remarks

There is a debate in the web3 community regarding permissioned versus permissionless blockchains, and to what degree of decentralization one may have over another.  Both solutions seem to have strengths and weaknesses.  I have not found a one size fits all, silver bullet.  I do not attempt to judge one approach over another.  Rather, I look at the architecture, the approach to securing the platform, the smart contracts, and the data of each decentralized solution.