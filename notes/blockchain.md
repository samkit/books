---
presentation:
    center: false
#   .reveal p {
#     text-align: left;
#   }
#   .reveal ul {
#     display: block;
#   }
#   .reveal ol {
#     display: block;
#   }
---

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
- blockchain free solution

##### Quorum (from JPMC)
- https://www.goquorum.com/

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


# Presentation

<!-- slide -->

# Blockchain
###### (a very simple study)

<!-- slide -->

## Distributed Ledger Technology
- Blockchain
- DAG based
- Other simpler DLT

<!-- slide -->

# Blockchain
![](https://crypto-beginners-media-storage.s3-ap-southeast-2.amazonaws.com/static/img/blockchain_illustration.png)
- Consensus - PoW/PoS/BFT etc
- Slow as it grows linearly - lot of wastage if PoW is discarded
- Everynode has to have all blocks stored
- Ledger is bloated with past transactions

<!-- slide -->

# DAG
![](https://crypto-beginners-media-storage.s3-ap-southeast-2.amazonaws.com/static/img/dag_2.png)

<!-- slide -->
# DAG
- Much better performance than [linear?] blockchains
- Performance improves with time
- Ledger bloat is still there

<!-- slide -->

# Sharding
![](https://miro.medium.com/max/1400/0*6qw4xUQxY5jxMPU0)
- Partial data with every node
- Only few implementations have this
    - couldn't find opensource

<!-- slide -->

# Hyperledger Fabric
- [A good overview](https://medium.com/coinmonks/demystifying-hyperledger-fabric-1-3-fabric-architecture-a2fdb587f6cb)

<!-- slide -->

# ![R3 Corda](https://www.corda.net/wp-content/themes/corda/assets/images/crda-logo-big.svg)
- Awesome documentation - https://docs.corda.net/
- [Good bootcamp/kata](https://www.youtube.com/playlist?list=PLi1PppB3-YrVq5Qy_RM9Qidq0eh-nL11N)
- Designed specifically for finance industry
    - Permissioned / Auditable Governance
    - P2P
    - Easy deployability - JVM based
    - Counterparty identification - legally provable

<!-- slide -->
## High Level Notables
- Permissioned / Auditable governance
- Smart Contracts
- Distributed Apps (CorDapps)
- Pluggable consensus
- Scalable as there is no blockchain and is more p2p
- Easy deployability - JVM based
- Support for complete privacy by onlookers ==TODO(vendor)==

<!-- slide -->
###### Network
![](https://docs.corda.net/_images/network.png)
- Every node is indepdent and doesn't share anything unless required
- Heavy on "need-to-know-basis" paradigm

<!-- slide -->

###### Ledger
![](https://docs.corda.net/_images/ledger-venn.png)
- Facts are shared only when necessary

<!-- slide -->
###### State
- States are immutable facts
- Transaction is required to change state
- Past states are kept in db
- Support for reference states
    - which doesn't participate in transaction commit but can be used for validation (REG) ==TODO==

<!-- slide -->

###### Transaction
- Contains earlier state reference and proposed state, along with command (i.e. action)
- Types of transactions can be time bounded
- Notary service is the authority to approve a transaction (distributed)
    - Similar to "Orderer" in Hyperledger
- Supports Smart Contracts
    - can do validation
- Supports Oracle - while validating if you need external state then architectural term is to use Oracle (REG?) ==TODO==

<!-- slide -->

###### Transaction
![](https://docs.corda.net/_images/commands.png)

<!-- slide -->

###### Flows!!
- Distributed apps running on Corda nodes
- Can be as simple as "do this transaction"
- Flows can have side-effects/impure - so good for complex workflows
    - where multiple nodes talk to each other
- Can be started by various mechanisms
    - Via RPC/REST
    - by other flows
- Supports sub-flows
- Very scalable

<!-- slide -->
###### Flow Example
![](https://docs.corda.net/_images/flow-sequence.png)

<!-- slide -->
###### CorDapps (Distributed Apps)
![](https://docs.corda.net/_images/node-diagram.png)
- Are jar files
- Consists of flows, states, commands, contracts and custom services

<!-- slide -->

###### Notary
- Responsible for uniqueness as consensus
- Can also do validation consensus based on data
- Notaries can be configured to look at data for validity consensus
    - otherwise notaries don't see the data in messages
    - hence are scalable
- Horizontally scalable
- Multiple notary clusters can run different consensus algo

<!-- slide -->
###### Vault
- Interface to facts/states
- Can query via RPC/REST or JDBC

---
###### Oracle
- Provides external data for smart contracts in a deterministic manner
    - kind of milestoned by Corda nodes 

<!-- slide -->

###### Corda Node
![](https://docs.corda.net/_images/node-architecture.png)

<!-- slide -->

**Corda Node**
- JVM processes
- Provides interface for RPC/REST and Gossip with other nodes
- Hosting service for CorDapps
- Upgrading contracts

<!-- slide -->

![](https://docs.corda.net/_images/vault.png)

<!-- slide -->
###### End to End Flow ==TODO==
- Pub sub
- What to store and when/where
- Callbacks on new data
- Scalability
- Data Pruning??? - not possible

<!-- slide -->
# Others
- [Ardor](https://www.radixdlt.com/) - from NXT platform
    - very good features like pruning
    - but is hosted
- [Peaq](https://peaq.io/) (under development)
- [Quorum](https://www.goquorum.com/) - from JPMC
- [RadixDLT](https://www.radixdlt.com/) - not opensource
<!-- slide -->

