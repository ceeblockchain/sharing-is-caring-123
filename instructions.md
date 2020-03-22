# Technical deep-dive and demo walkthrough

In this simplified demo we simulated three actors who are participating in the supply chain of research information used to counter COVID-19 pandemics. The objective of it is to showcase the case towards setting up a decentralized platform to submit, track and query research data.

## Technical overview of our solution

Our platform is a showcase of functionalities that allow for a submission of research data and tracking of subsequent activities related to its lifecycle (peer reviews, approals for manufacturing and other activities). It does so while making sure the integrity of data and unique identification of changes is maintained.

<img src="https://github.com/hack-the-crisis/sharing-is-caring-123/blob/master/solution.png">

Data saved on the ledger is responding to a need to quickly secure copyright over the content without a need to rely on a trusted third party. It does so by providing a uniquevocal intellectual property recognition back to the author or her/his employer (i)(ii) and using qualified digital signatures to validate the identities of authors and publishers (iii). Due to the fact that central institutions that traditionally provide these services may now be overrun by emergency tasks and are further impacted by a reduction of available staff to support the ongoing activities, we used Hyperledger Fabric distributed ledger network to provide a decentralized trust layer. The use of blockchain as a single (albeit fault tolerant and highly available) source of truth for research data (iv) reduces proliferation of copies of the same data, generating redundant activities across small community pockets unrelated or unaware of each other. The functionalities addressing each of these requirements are described below.

(i) digital timestamp of the data which is a result of Hyperledger Fabric consensus process. To read more about decentralized consensus please click [here](https://hyperledger-fabric.readthedocs.io/en/release-2.0/orderer/ordering_service.html).
<br><br>
(ii) cryptographic proof of document content using cryptographic hash (sha256). To read more about how the hash function is working, please click [here](https://www.movable-type.co.uk/scripts/sha256.html) 
<br><br>
(iii) a unique identifier of a content submitter which is governed under the hood by Hyperledger Fabric. To read more about how Hyperledger Fabric manages identities in a permissioned ledger network please click [here](https://hyperledger-fabric-ca.readthedocs.io/en/latest/index.html) 
<br><br>
(iv) research metadata attached to a particular document which is a key/value store. In the context of blockchain, every entry can be queried against its history of changes and tracked to a uniquely identifiable piece of research.
<br>

## Communication flow

<img src="https://github.com/hack-the-crisis/sharing-is-caring-123/blob/master/images/txflow.png">

When a new research data in registered by research author, the blockchain layer built on Hyperledger Fabric essentially saves the metadata and a cryptographic hash (sha256) of a document. BCAssetManagement framework governs the communication with Hyperledger Fabric peer node and a chaincode (smart contract). Every time when a new user (Peer Reviewer, FDA etc.) is referring back to an already registered data, BCAssetManagement framework connects to Hyperledger Fabric peer node ledger state (CouchDB) and extracts the information about the current state before allowing that user to append the state of a research data. At any time, any person who has a copy of the document can verify its existence and integrity through the search mechanism. In background, the document's hash is checked against the ledger state.

## Other technical knowledge pre-requisites

Before starting the demo, it is important to acquire some essential knowledge about technical components used in our solution. This will provide a better understanding in terms of timestamp, tracking of a uniquely identifiable asset and cryptographic proof of existence of supplied documents.

### What is blockchain

In general terms, a blockchain is an immutable transaction ledger, maintained within a distributed network of peer nodes. These nodes each maintain a copy of the ledger by applying transactions that have been validated by a consensus protocol, grouped into blocks that include a hash that bind each block to the preceding block.

The first and most widely recognized application of blockchain is the Bitcoin cryptocurrency, though others have followed in its footsteps. Ethereum, an alternative cryptocurrency, took a different approach, integrating many of the same characteristics as Bitcoin but adding smart contracts to create a platform for distributed applications. Bitcoin and Ethereum fall into a class of blockchain that we would classify as public permissionless blockchain technology. Basically, these are public networks, open to anyone, where participants interact anonymously.

### What is Hyperledger Fabric

Hyperledger Fabric is an open source enterprise-grade permissioned distributed ledger technology (DLT) platform, designed for use in enterprise contexts, that delivers some key differentiating capabilities over other popular distributed ledger or blockchain platforms.

The Fabric platform is also permissioned, meaning that, unlike with a public permissionless network, the participants are known to each other, rather than anonymous and therefore fully untrusted. This means that while the participants may not fully trust one another (they may, for example, be competitors in the same industry), a network can be operated under a governance model that is built off of what trust does exist between participants, such as a legal agreement or framework for handling disputes.

We chose Hyperledger Fabric as it satisfies the following functionalities that we intend to build in long term:

- Participants must be identified/identifiable
- Networks need to be permissioned
- High transaction throughput performance
- Low latency of transaction confirmation
- Privacy and confidentiality of transactions and data pertaining to business transactions

## Demo Walkthrough

### Perspective of a research author

From the perspective of research author, our application showcases the process of submitting a research or medical data that is supplied with a (i) digital timestamp of the data regardless of its binary and presentation form supplied with (ii) cryptographic proof of document content, (iii) a unique identifier of a content submitter.

1. We start by clicking on the *Research Author* role.

<img src="https://github.com/hack-the-crisis/sharing-is-caring-123/blob/master/images/1.research-author.png" width="480" />

2. We will now create a new research content by clicking *Create*.

<img src="https://github.com/hack-the-crisis/sharing-is-caring-123/blob/master/images/2.create-content.png" width="480" />

3. We fill out all the necessary information and attach a document representing our original piece of research through *Add publication* field. Then, we click *Create*.

<img src="https://github.com/hack-the-crisis/sharing-is-caring-123/blob/master/images/3.create-content-2.png" width="480" />

4. Once the publication is registered, it will show up on the list. Let's click on it to see the details.

<img src="https://github.com/hack-the-crisis/sharing-is-caring-123/blob/master/images/4.select-research.png" width="480" />

5. As we can see, a new block on the blockchain has been created and represents the submission of our original piece of research data. The creation of this block is a result of decentralized consensus and is supplemented with a timestamp of action. Its content reveal all essential data to verify the integrity of a document we just submitted and its metadata, including authorship which is essential for copyright and intellectual property purposes. At this stage, our work, its origin, moment of creation and authorship are secured but are not yet visible to the outside world. Let's click on *Submit* to officially publish the document to Peer Reviewers.

<img src="https://github.com/hack-the-crisis/sharing-is-caring-123/blob/master/images/5.submit.png" width="480" />

6. As we can see, every action, including submission generates a new event that is saved on the ledger with a new timestamp record. As we go further into this scenario we will see that all subsequent actions related to a particular piece of original research data can be traced back to the same uniquely identifiable work initially published by Research Author.

<img src="https://github.com/hack-the-crisis/sharing-is-caring-123/blob/master/images/6.back.png" width="480" />

## Perspective of a peer reviewer

From the perspective of peer reviewer, our application showcases the process of commenting a research or medical data that is supplied from a uniquely identifiable research author. Any subsequent modificaiton of an existing entry is supplied with a (i) digital timestamp of the data regardless of its binary and presentation form supplied with (ii) cryptographic proof of document content, (iii) a unique identifier of a content submitter. Moreover, this element of the process shows the capability to (iv) register subsequent activities that can be tracked to a uniquely identifiable piece of research.

7. We start by clicking on the *Peer Reviewer* role.

<img src="https://github.com/hack-the-crisis/sharing-is-caring-123/blob/master/images/7.peer-reviewer.png" width="480" />

8. We then select the newly published work.

<img src="https://github.com/hack-the-crisis/sharing-is-caring-123/blob/master/images/8.select-research-peer.png" width="480" />

9. As a Peer Reviewer, we want to add our feedback from the lecture of the research data. To do that we click on *Modify* button.

<img src="https://github.com/hack-the-crisis/sharing-is-caring-123/blob/master/images/9.modify.png" width="480" />

10. We then add a comment to the original work and click *Modify*.

<img src="https://github.com/hack-the-crisis/sharing-is-caring-123/blob/master/images/10.modify-2.png" width="480" />

11. Similarly to previous actions, the peer review generates a new event that is saved on the ledger with a new timestamp record which can be traced back to the same uniquely identifiable work initially published by Research Author.

<img src="https://github.com/hack-the-crisis/sharing-is-caring-123/blob/master/images/11.submit-2.png" width="480" />

## Perspective of a Regulator

From the perspective of regulator, our application showcases the process of approving a research or medical data that is supplied from a uniquely identifiable research author and is updated by a number of peer reviewers. Again, any interaction with the entry is registered with a (i) digital timestamp of the data regardless of its binary and presentation form supplied with (ii) cryptographic proof of document content, (iii) a unique identifier of a content submitter. Continuously, the entry is tracing back any activities related to a uniquely identifiable piece of research supplied by equally uniquely identifiable author.

![alt text](https://github.com/hack-the-crisis/sharing-is-caring-123/blob/master/images/14.fda-research.png)
![alt text](https://github.com/hack-the-crisis/sharing-is-caring-123/blob/master/images/15.reject-approve.png)
![alt text](https://github.com/hack-the-crisis/sharing-is-caring-123/blob/master/images/10.modify-2.png)
