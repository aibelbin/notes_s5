

## Store and forward Packet switching
![[Pasted image 20251107233033.png]]

1. A packet is sent to the router next to it or over point to point to the carrier 
2. Packet is then stored there to wait for the checksum | verify
3. continue forwarding like this until the destination is reached 


## Service provided to the  transport layer 


The network layer services have been designed with the following goals in
mind.
• The services should be independent of the router technology.
• The transport layer should be shielded from the number, type, and
topology of the routers present.
• The network addresses should use a uniform numbering plan, even across
LANs and WANs.
• Network layer should provide connection-oriented service or connectionless
service.
• However, it is interesting to note that as quality-of-service guarantees are
becoming more and more important.


## Connection less service 

Packets are injected into the subnet and routed individgually 
packets are called **datagrams**


but if connection is established beforehand, its called vc **(virtual connection)**

![[Pasted image 20251107234305.png]]

explain this along with store and forward 


The algorithm that manages the tables and makes the routing decisions is called
the **routing algorithm**


## Connection oriented service 

first creates a vc during network boot, 
When a connection is established, a route from the source machine to the
destination machine is chosen as part of the connection setup and stored in
tables inside the routers.

When the connection is released, the virtual circuit is also terminated. With
connection-oriented service, each packet carries an identifier telling which
virtual circuit it belongs to.

## Difference 

![[Pasted image 20251107235141.png]]

• Virtual circuits also have a vulnerability problem.
• If a router crashes and loses its memory, even if it comes back up a second
later, all the virtual circuits passing through it will have to be aborted.
• In contrast, if a datagram router goes down, only those users whose packets
were queued in the router at the time will suffer, and maybe not even all
those, depending upon whether they have already been acknowledged.
• The loss of a communication line is fatal to virtual circuits using it but can be
easily compensated for if datagrams are used.
• Datagrams also allow the routers to balance the traffic throughout the subnet,
since routes can be changed partway through a long sequence of packet
transmissions.


# Routing 

The process of moving packet from source to the destination is known as routing

function of the network layer is to route this packet from source to the destination, sometimes the packets require multiple hops to go from the source to the destination 

**routing algorithm** decides which output line the packet should be sent on 



## VC (Virtual Connection) contd.. 

• If the subnet uses virtual circuits internally, routing decisions are made only
when a new virtual circuit is being set up.
• Thereafter, data packets just follow the previously-established route.
• This is sometimes called session routing because a route remains in force for
an entire user session


A router has 2 processes inside it, 
			> forwarding 
			> updating route tables 
			

## Desirable properties of routing algorithms 

![[Pasted image 20251108000345.png]]

## Adaptive Routing Algorithms 


• Adaptive algorithms, in contrast, change their routing decisions to reflect
changes in the topology, and usually the traffic as well.
• Adaptive algorithms differ in where they get their information (e.g., locally,
from adjacent routers, or from all routers), when they change the routes
(e.g., every ΔT sec, when the load changes or when the topology changes),
and what metric is used for optimization (e.g., distance, number of hops, or
estimated transit time).


## Non Adaptive Routing Algorithms 

• Nonadaptive algorithms do not base their routing decisions on
measurements or estimates of the current traffic and topology.
• Instead, the route get in advance, off-line, and downloaded to the routers
**when the network is booted.**
• This procedure is sometimes called **static routing.**


## Optimality principle 

Optimality Principle: The principle states that if I to K through J is the
optimal path, then both segments I to J and J to K must be optimal as
well.


## Sink tree 

 set of all optimal routes to the destination form a tree keeping the destination as the root of the tree such a tree is called a sink tree
`this is on the bases of hops`


## Shortest path routing (Non Adaptive)

Here the idea is to build a graph of the subnet, with each node of the graph representing a
router and each arc of the graph representing a communication line.

To choose a route between a given pair of routers, the algorithm just finds the shortest path
between them on the graph.

• One way of measuring path length is the number of hops.
• Many other metrics besides hops and physical distance are also possible.

The labels on the arcs could be computed as a function of the distance, bandwidth, average
traffic, communication cost, mean queue length, measured delay, and other factors. By
changing the weighting function, the algorithm would then compute the ''shortest'' path
measured according to any one of a number of criteria or to a combination of criteria.


## Dijkstra Algorithm for shortest path

	  yet to fill 


## Flooding (non adaptive)

Every incoming packet is also sent out to every out going line **except the on it came from**

Flooding  generates vast numbers of duplicate packets, in fact, an infinite
number unless some measures are taken to damp the process.

One such measure is to have a **hop counter** contained in the header of each packet,
which is decremented at each hop, with the packet being discarded when the counter
reaches zero.  Ideally, the hop counter should be initialized to the length of the path from source to destination.

An alternative technique for damming the flood is to keep track of which packets
have been flooded, to avoid sending them out a second time achieve this goal is to
have the source router put a sequence number in each packet it receives from its
hosts


### Selective flooding

• A variation of flooding that is slightly more practical is selective flooding.
• In this algorithm the routers do not send every incoming packet out on every
line, only on those lines that are going approximately in the right direction.



## Distance vector routing 

Distance vector routing algorithms operate by having each router maintain a
table (i.e, a vector) giving the best known distance to each destination and
which line to use to get there. These tables are updated by exchanging
information with the neighbours

The distance vector routing algorithm is sometimes called by other names,
most commonly the distributed *Bellman-Ford* routing algorithm and the
*Ford-Fulkerson algorithm*

• In distance vector routing, each router maintains a routing table containing one
entry for, each router in the subnet.
• This entry contains two parts: the preferred outgoing line to use for that
destination and an estimate of the time or distance to that destination.
• The metric used might be number of hops, time delay in milliseconds, total
number of packets queued along the path, or something similar.
• The router is assumed to know the ''distance'' to each of its neighbours.


### Count to infinity problem 

The Count to Infinity problem is a routing issue that occurs in distance vector routing protocols, such as RIP, where incorrect routing information propagates through a network, causing the hop count to a destination to increase indefinitely until it reaches a theoretical infinity


## Link state routing 

> `replaced the distance vector routing as this takes bandwidth to the consideration and also made sure count to infinity problem didnt exist`

The idea behind link state routing is simple and can be stated as five parts. Each router must
do the following:

• Discover its neighbours and learn their network addresses.
• Measure the delay or cost to each of its neighbours.
• Construct a packet telling all it has just learned.
• Send this packet to all other routers.
• Compute the shortest path to every other router.


When a router is booted, its first task is to learn who its neighbours are.
• It accomplishes this goal by sending a special HELLO packet on each point-to-point line.
• The router on the other end is expected to send back a reply telling who it is.
• When two or more routers are connected by a LAN, the situation is slightly more
complicated.

b) Measuring Line Cost
• The link state routing algorithm requires each router to know, the delay to each of its
neighbours.
• The most direct way to determine this delay is to send over the line a special ECHO
packet that the other side is required to send back immediately.
• By measuring the round-trip time and dividing it by two, the sending router can get a
reasonable estimate of the delay.
• For even better results, the test can be conducted several times, and the average
used.

An interesting issue is whether to take the load into account when measuring the delay.
• To factor the load in, the round-trip timer must be started when the ECHO packet is
queued.
• To ignore the load, the timer should be started when the ECHO packet reaches the front
of the queue.

• Once the information needed for the exchange has been collected, the next step
is for each router to build a packet containing all the data.
• The packet starts with the identity of the sender, followed by a sequence
number and age (to be described later), and a list of neighbours.

d) Distributing the Link State Packets
• The trickiest part of the algorithm is distributing the link state packets reliably.
• The fundamental idea is to use flooding to distribute the link state packets.
• To keep the flood in check, each packet contains a sequence number that is
incremented for each new packet sent.
• Routers keep track of all the (source router, sequence) pairs they see.

• If a packet with a sequence number lower than the highest one seen so far ever
arrives, it is rejected.


## Multicast routing 

• we need a way to send messages to well-defined groups that are
numerically large in size but small compared to the network as a whole.
• Sending a message to such a group is called multicasting, and the routing
algorithm used is called multicast routing.

Multicast routing uses spanning tree to efficiently distribution information 



## Routing for mobile hosts 

