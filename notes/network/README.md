# network

network
function: communication-broadcast(cocktail party) or address table(letter writing); security, which I will not consider; scalability and mobility (end system move from one net to another); policy
structure: unreliable channel-loss and error happens; historical structures exist 
fragmentation

for a system design, we should separate architecture design and algorithm/mechanism design
good abstraction should be layering of architecture and separation between architecture and algorithm

we can change or update each layer and each algorithm independently

physical layer
direct connection and broadcast only
use mesh link (complete graph) or network core "hub" to broadcast
efficient(or tractable) only for small networks (too much links, hubs, interfaces on hubs, and resources consumed)

link layer
indirect connection and addressing/broadcast
use network core "switch" to address, which contains an address table
efficient(or tractable) only for medium networks (too large the address table)
every end system must have an address now
though we can dynamically allocate one
1.due to historical reasons i.e. historical structures implemented, which works well for medium networks, we have a burn-in address in each end system, MAC, for ethernet
2.based on different physical implementation, we can have diffferent link layer protocol e.g. retransmission for wireless link


to unify heteromorphic historical structures i.e. different addressing, to communicate them and build a network of networks, we introduce logical addressing
and also, MAC address in a network has no structure (i.e. no common prefix)

given IP in a subnet, ARP to get its MAC
given IP in another net, set MAC as the router's

network layer
use network core "router" to address, which contains an address table
how to dynamically allocate logical addresses: depend on topology of network
subnet share a common prefix, which largely reduce the table size
each subnet has its own political identity and thus policy may be applied

transport layer
implement function reliable channel, as TCP
UDP mainly an "empty" protocol
implement function port-to-port, this is trivial

application layer
do more general/abstract communication, given a reliable (or not) channel


