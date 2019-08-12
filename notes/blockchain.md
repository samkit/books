[TOC]

# Distributed Ledger Technology
### Reading
- https://codeburst.io/distributed-ledger-technology-fundamentals-you-must-know-2d0f82628258
    - ![](https://miro.medium.com/max/1200/1*Xll0lheujAWLuztToBikhg.jpeg)
- [UK Government - Distributed  Ledger Technology: beyond block chain](https://www.gov.uk/government/uploads/system/uploads/attachment_data/file/492972/gs-16-1-distributed-ledger-technology.pdf)
    - [Report.pdf](https://assets.publishing.service.gov.uk/government/uploads/system/uploads/attachment_data/file/492972/gs-16-1-distributed-ledger-technology.pdf)
- https://blockchainhub.net/blockchains-and-distributed-ledger-technologies-in-general/
- https://medium.com/@gaurangtorvekar/7-blockchain-technologies-to-watch-out-for-in-2017-4b3fc7a85707
- [A comprehensive List of Blockchain Platforms](https://www.technoduet.com/a-comprehensive-list-of-blockchain-platforms/)
- [Hyperledger Fabric v/s Sawtooth](https://www.blockchain-council.org/hyperledger/hyperledger-sawtooth-or-hyperledger-fabric-which-is-better/)
- [Hyperledger Fabric v/s R3 Corda](https://www.coindesk.com/blockchain-for-banks-startup-switches-from-hyperledger-to-r3s-corda)
    - [More story switching from Hyperledger to Corda](https://www.coindesk.com/all-big-insurers-are-uniting-behind-r3s-blockchain-tech)
- [Ethereum v/s Hyperledger v/s R3 Corda](https://medium.com/@micobo/technical-difference-between-ethereum-hyperledger-fabric-and-r3-corda-5a58d0a6e347)
    ![](https://miro.medium.com/max/678/1*lDgcV0Ivp7e20mI_CHVlHA.png)
- [Solving Blockchain bloat](https://www.devteam.space/blog/can-blockchain-bloat-ever-be-solved/)
#### Hyperledger
- https://www.ibm.com/blogs/blockchain/2019/04/does-hyperledger-fabric-perform-at-scale/

#### R3 Corda
- Performance - https://medium.com/corda/transactions-per-second-tps-de3fb55d60e3
- HA - https://docs.corda.net/head/design/hadr/design.html

### Concepts
#### InterLedger Protocol
- https://interledger.org/
- https://www.hyperledger.org/projects/quilt
#### Sharding
#### DAG based

### Implementations

#### [DAG Based](https://blog.daglabs.com/an-introduction-to-the-blockdag-paradigm-50027f44facb)
##### IOTA Tangle
- https://www.iota.org/get-started/what-is-iota
- https://medium.com/nakamo-to/dags-the-future-of-dlt-8c61f405df8a

##### Peaq
- https://peaq.io/

##### Radix DLT
- https://www.radixdlt.com/

#### R3 Corda
- Designed for banks/finance usecases
- More towards p2p transactions
- Bootcamps: https://www.youtube.com/playlist?list=PLi1PppB3-YrVq5Qy_RM9Qidq0eh-nL11N
- Closest usecase for us: https://github.com/BCSTech-CordaTeam/PropertyListing
- Very well explained feature set [here](https://medium.com/@micobo/technical-difference-between-ethereum-hyperledger-fabric-and-r3-corda-5a58d0a6e347)
- [Top 5 facts](https://medium.com/inside-r3/top-5-facts-about-corda-network-e5ced4287123)

##### Concepts
- [Flow](https://www.youtube.com/watch?v=2ZrRWVktqpE) - transfers messages
    - can be used for barrier kind of things
    - https://docs.corda.net/key-concepts-flows.html
    - ![](https://docs.corda.net/releases/release-M9.2/_images/flowFramework.png)
- Support [reference state](https://docs.corda.net/key-concepts-transactions.html#reference-states) are not consumed in the transaction and they are included in transaction for some reference
    - think of reference data as permissioning model :fa-th:
- Corda runs contracts in JVM which has stricter permissions than normal JVM
    - Compared to docker container in case of Hyperledger
    - no side-effect libs are allowed like IO/network, time, random etc
- Reference state
- Attachment on transactions
- Time window for transactions (may be for quotas)
- [Oracle](https://docs.corda.net/key-concepts-oracles.html) for querying external resources in consistent manner
- [Event Scheduling](https://docs.corda.net/event-scheduling.html)

##### Features
- Ease of installation
    - jvm based (not docker like Hyperledger)

##### Competition Compared
- Hyperledger Fabric: https://medium.com/newcryptoblock/hyperledger-fabric-vs-r3-corda-7954035a4884


##### News
- Goldman was part of consortium but exited in 2018 or so

##### Issues
- Vault service to give snapshot and updates: https://docs.corda.net/api-vault-query.html
    - https://r3-cev.atlassian.net/browse/CORDA-2401

#### Ardor
- https://ardorplatform.org/
- [Whitepaper](https://www.jelurida.com/sites/default/files/JeluridaWhitepaper.pdf) :fa-thumbs-up:
    - Look at page 7-8 for table
- [Code](https://bitbucket.org/Jelurida/ardor/src/master/)

##### Features
- Good pruning policy for child chains
    - also parent chains are very small
- Quotas can be easily implemented using coins

#### Icon
- https://icon.foundation/resources/whitepaper/ICON_Whitepaper_EN.pdf

#### Peaq (coming soon)
- https://peaq.io/

# Blockchain

##  Things to consider
- Inter-operability with other companies
- Conflict resolution and transaction rollback
    - Last point [here](https://medium.com/@micobo/technical-difference-between-ethereum-hyperledger-fabric-and-r3-corda-5a58d0a6e347)
- Documentation and community support
- Distributed Apps (or dApps)
    - Hyperledger doesn't support it naturally

# Awesome things that can be done
- Messaging between multiple nodes
    - Can be used to raise alerts/notifications regarding ongoing/planned issues
    - 
