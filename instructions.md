# Demo Walkthrough

In this simplified demo we simulated three actors who are participating in the supply chain of research information used to counter COVID-19 pandemics. The objective of it is to showcase the case towards setting up a decentralized platform to submit, track and query research data.

## Pre-requisites

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

## Perspective of a research author

From the perspective of research author, our application showcases the process of submitting a research or medical data that is supplied with a (i) digital timestamp of the data regardless of its binary and presentation form supplied with (ii) cryptographic proof of document content, (iii) a unique identifier of a content submitter.

![alt text](https://github.com/hack-the-crisis/sharing-is-caring-123/blob/master/images/1.research-author.png)
![alt text](https://github.com/hack-the-crisis/sharing-is-caring-123/blob/master/images/2.create-content.png )
![alt text](https://github.com/hack-the-crisis/sharing-is-caring-123/blob/master/images/3.create-content-2.png)
![alt text](https://github.com/hack-the-crisis/sharing-is-caring-123/blob/master/images/4.select-research.png)
![alt text](https://github.com/hack-the-crisis/sharing-is-caring-123/blob/master/images/5.submit.png)
![alt text](https://github.com/hack-the-crisis/sharing-is-caring-123/blob/master/images/6.back.png)

## Perspective of a peer reviewer

From the perspective of peer reviewer, our application showcases the process of commenting a research or medical data that is supplied from a uniquely identifiable research author. Any subsequent modificaiton of an existing entry is supplied with a (i) digital timestamp of the data regardless of its binary and presentation form supplied with (ii) cryptographic proof of document content, (iii) a unique identifier of a content submitter. Moreover, this element of the process shows the capability to (iv) register subsequent activities that can be tracked to a uniquely identifiable piece of research.

![alt text](https://github.com/hack-the-crisis/sharing-is-caring-123/blob/master/images/7.peer-reviewer.png)
![alt text](https://github.com/hack-the-crisis/sharing-is-caring-123/blob/master/images/8.select-research-peer.png)
![alt text](https://github.com/hack-the-crisis/sharing-is-caring-123/blob/master/images/9.modify.png)
![alt text](https://github.com/hack-the-crisis/sharing-is-caring-123/blob/master/images/10.modify-2.png)
![alt text](https://github.com/hack-the-crisis/sharing-is-caring-123/blob/master/images/11.submit-2.png)
![alt text](https://github.com/hack-the-crisis/sharing-is-caring-123/blob/master/images/12.back-2.png)

## Perspective of a Regulator

From the perspective of regulator, our application showcases the process of approving a research or medical data that is supplied from a uniquely identifiable research author and is updated by a number of peer reviewers. Again, any interaction with the entry is registered with a (i) digital timestamp of the data regardless of its binary and presentation form supplied with (ii) cryptographic proof of document content, (iii) a unique identifier of a content submitter. Continuously, the entry is tracing back any activities related to a uniquely identifiable piece of research supplied by equally uniquely identifiable author.

![alt text](https://github.com/hack-the-crisis/sharing-is-caring-123/blob/master/images/14.fda-research.png)
![alt text](https://github.com/hack-the-crisis/sharing-is-caring-123/blob/master/images/15.reject-approve.png)
![alt text](https://github.com/hack-the-crisis/sharing-is-caring-123/blob/master/images/10.modify-2.png)
