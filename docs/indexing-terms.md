# Indexing terms and definitions


### Subgraph

A subgraph is an index of the child objects related to a single root document. 
A subgraph would contain the most basic representation of the child document. Such as the streamID, schemaID, the DID of the creator, etc.
From there more complicated processing of the subgraph content can be done to create a full document index of subgraph documents. 
The first step is knowing what data is related to a root document, and being able to discovery more related data from the network.

In the case of the SPK network:
First, two terms must be mentioned. Below, are the two main roles a node will play while taking part in indexing the network.
* Regular node: a node acting as a bystander, only reading/writing to the network without taking part in indexing subgraphs. These nodes will likely still the store child documents, just not the subgraphs.
* Custodian node: a node announcing themselves as responsible for indexing a subgraph of a particular root document.

Ideally, all nodes will do both of the above, with some variation depending upon environmental/operator factors.

Let's dial in on the custodian node:

The responsibilities of a custodian are providing, storing, and keeping a subgraph index up to the date.
To do this a custodian node must first announce their presence and interest of a subgraph to the network. 
The announcement would be done through a pubsub/multicast message to the rest of the network.
Foreign custodian nodes and normal nodes will listen to announcements from the network and build a routing table of who does what.
In the case of normal nodes, the routing table would be used for putting and getting subgraph indexes from the network.
In the case of custodians, they will connect with foreign custodians to keep the local subgraph index up to date.


Custodians will:
* Validate subgraphs against required schemas
* Ask for subgraph indexes from foreign custodians.
* Receive and store subgraph indexes from foreign custodians. (assuming the data is valid and not against blacklists)
* Provide subgraph indexes matching requested criteria to normal nodes
* Receive subgraph indexes from normal nodes to be indexed (assuming the data is valid and not against blacklists)


### Child documents



### Root document
*Also called a root parent* Is the top level object of a data structure from the perspective of the viewer. 
Large datastructures can have many child documents with many children under each one. While there is a root document, there are also many smaller roots, some of which might be treated as independant from the root document. 
When we consider one of these child documents to be highest level of the tree, then to the perspective of the viewer that is the root document.
What is called the root document dials down to the most basic level of a graph architecture, that is parent-child relationship.
From there more complicated, interconnected and interrelated webs of information can be conceptualized.
The root is interest is dialing down to the most basic level of the architecture ignoring the rest of the graph. The most basic level of the architecture is parent-child relationship. 
From that relationship, complicated interconnected and interrelated webs of information can be conceptualized. 

In a distributed social media system, you can consider the root document to be a blog post, and the comments be the child documents.

Important note: It is theoretically possible to have multiple root documents pointing to a single child document. 
However, this is not a bridge the SPK network is going to cross anytime soon. Simply it is too complex to handle.
For now, the maximum level of complexity will be: One (root) --> Many (children) and Many (children) --> One (root).

