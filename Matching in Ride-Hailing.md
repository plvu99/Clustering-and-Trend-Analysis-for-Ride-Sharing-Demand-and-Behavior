# Matching in Ride-Hailing
Rides can be either **non-shared**, meaning that the ride is arranged for only one customer group, or **shared**, meaning that several customer groups with different pickup and dropoff locations share the ride.

## Non-shared ride (First-dispatch)
In the simpler case of a non-shared ride, drivers participating on the platform cycle through three states sequentially:
- **"open"** (waiting to be dispatched),
- **"en route"** (on the way to the pickup location), and
- **"on-trip"** (driving riders to their destination).

A request can be matched with a dispatchable driver using very simple algorithms, such as the first-dispatch protocol. 

In the first-dispatch protocol, only open drivers are considered as dispatchable. Each request is immediately assigned to the open driver who is predicted to have the shortest en route time. 

This matching algorithm is also called the on-call policy, the closest driver policy, and the committed driver-rider matching protocol.

## Shared ride (Batching-based optimization)
An alternative matching approach is batching where rider requests are collected for a short time window (typically on the order of seconds), at the end of which an optimization problem is solved to pair each request with an open driver.

If there are riders that are not matched in this batch, then they are carried over and used for the optimization problem in the next batching window. Batching can reduce the rider waiting time relative to the first-dispatch protocol by consolidating requests and making better use of supply.

Note that the first-dispatch protocol can be viewed as a special case of the batching protocol when each batch consists of exactly one rider request.

Due to its substantial benefits, batching has been implemented widely in major ride-hailing platforms.
