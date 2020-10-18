# Distributed hash table
- Provides lookup service similar to hash table
- Any participating node can effectively retrieve the value associated to key
- Node can be add/remove with minimum work around re-distributing keys
- Responsibility for maintaining the mapping of keys to values are distributed among nodes
- It only directly support exact-match search, rather than keyword search

# Usage
DHTs forma a infrastructure that can be used to build more complex services. Following are few example
- anycast
- cooperative web caching
- distributed file systems
- domain name services
- instant messaging
- multi cast
- peer to peer file sharing
- content distributions

Following are popular distributed networks using DHTs
- BitTorrent distributed tracker
- Coral content distribution network 
- Kad network
- Storm botnet
- Tox instant messenger
- Freenet
- YaCy search engine
- Inter Planetary file system

# properties
- Autonomy and decentralization - nodes collectively form the system without any central coordinations
- Fault tolerant - the system should be reliable even with nodes continuously joining, leaving and failing
- Scalability - the system should function efficiently even with thousands or millions of nodes
A key technique used to achieve these goal is that one node needs to coordinate with only a few other nodes in the system. Most commonly, O(log n) of n participant, so that limited amount of work needs to be done for each change in membership.

# Structure
- A set of 160 bit strings as keyspace
- A keyspace partitioning schema splits ownership of this keyspace among participate nodes.
- An overlay network then connects the nodes, allowing them to find the owner of any given key in keyspace

Following are steps to illustrate flow using example
- To index a file with given filename and data in DHT, SHA-1 hash of filename is generated, producing a 160 bit key 
- message put(k, data) is sent to any node participating in the DHT
- message is forwarded from node to node through the overlay network until it reaches the single node responsible for keys `k` as specified by keyspace partitioning
- That node then store the key and data
- Any client then retrive the data by passing the hash of filename `k`  with a message `get(k)` 
- The message will again routed through the overlay to the node responsible for `k` which will reply with the data

# Keyspace partitioning
- Consistent hashing
- Rendezvous hashing
- Locality preserve hashing
# Overlay network

# Reference
https://en.wikipedia.org/wiki/Chord_(peer-to-peer)
https://pdos.csail.mit.edu/papers/ton:chord/paper-ton.pdf
https://medium.com/techlog/chord-building-a-dht-distributed-hash-table-in-golang-67c3ce17417b
https://en.wikipedia.org/wiki/Distributed_hash_table
https://courses.cs.washington.edu/courses/cse550/14au/notes/lect15.pdf