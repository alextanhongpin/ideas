## Load balanced across different nodes

Say, you have 10 nodes connected to the network. Each node may leave/join the network at any time. So, how would you design a system that can:

- distribute workload equally across the different nodes
- handle leave/join gracefully, and also when there are no nodes at all (see `consistent hashing`)
- penalize the nodes that are misbehaving (see OWASP AppSensor)
- check status of each nodes


## Checking status of each node

It is possible to know the status of the nodes through different ways. One of them is to perform reverse healthcheck. We need a central gateway to achieve this. The nodes would consistently call the gateway to indicate that it is active (this can be done by normal http request, or websocket connection etc). Whenever the gateway stop receiving signal from the nodes for a certain time range, it will be automatically disconnected.

This gives us a few other conditions:
- if nodes are not connected for `t` period of time continuously, they may get penalised. On the other hand, we may reward nodes that are connected continuously for `t` period of time, e.g. for a week/month, or consecutive days of 10.
- if nodes are connected with a different ip address (we can keep an iptable and addresses to compare), we may suspect them of malicious activity (or they might be hacked)


## Distribute workload equally across the different nodes

This is a little hard, but let's look at some approach:

- assuming the number of nodes are static, we can first sort them by the tasks assigned to them. If all of them start with zero allocation, then the weightage is the same.
- if we assign node 1 with a task, increment the count
- sort the node lists in ascending order - the nodes without the tasks will have higher weightage.
- assign a task to the node without tasks/lesser priority
- repeat the steps until all have been assigned with some tasks

This can be accomplished using a priority queue with the count of tasks set to negative (lesser priority on nodes that performs more tasks).

But how do we actually give the nodes the task when they are the ones requesting for it? One way is to use websocket to deliver real-time notifications. This requires us to connect to all the nodes before delivering the tasks.

Another way is to perform a race-like competition for clients. At a given time, if the client make a call, we first mark the client as active. We set an epoch of 5s for example. In this given period, we will receive calls from other nodes as well. All the nodes making the calls within this epoch would be placed in a pool. They would make another call at a fixed interval given by the gateway in the first requests, and attempt to retrieve the package in the second call. The first verified node, sorted by weightage would be able to receive the package to process it.
