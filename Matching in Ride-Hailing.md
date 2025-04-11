# Matching in Ride-Hailing

## Ride-Hailing Platforms

Ride-hailing platforms such as Uber and Lyft have achieved explosive growth and reshaped urban transportation. For example, Uber has completed **over 10 billion trips globally** and is active in **over 80 countries and 700 cities** since its initial launch in 2009. By some estimates, the global ride-hailing industry is projected to grow to a **285 billion dollar total market value by 2030**.

Ride-hailing platforms connect riders and drivers via a centralized and automated matching and pricing system in a two-sided marketplace. Ride-hailing platforms have three components:

- Driver app (for drivers to offer services and communicate with their customers).

- Rider app (for customers to book and track their journeys and select vehicle types).

- A dispatch system (a system that connects the driver and the customer via their mobile phones).

There are two key levers in building a successful ride-hailing platform:

- **Matching algorithms:** the process of dispatching available drivers to pick up riders.

> Efficiently match riders and drivers.

- **Dynamic pricing algorithms:** the adjustment of prices for rides over time based on real-time demand and supply conditions.

  - Dynamic pricing is called surge pricing by Uber and prime time by Lyft.  

> Keep the supply of drivers and demand of riders in balance.
  
A successful implementation of matching and pricing can be leveraged to create an experience with low waiting times for both riders and drivers.

## Matching Algorithms

Rides can be either **non-shared**, meaning that the ride is arranged for only one customer group, or **shared**, meaning that several customer groups with different pickup and dropoff locations share the ride.

### Non-shared Ride (First-dispatch)

In the simpler case of a non-shared ride, drivers participating on the platform cycle through three states sequentially:

- **"open"** (waiting to be dispatched),

- **"en route"** (on the way to the pickup location), and

- **"on-trip"** (driving riders to their destination).

A request can be matched with a dispatchable driver using very simple algorithms, such as the first-dispatch protocol. 

In the first-dispatch protocol, only open drivers are considered as dispatchable. Each request is immediately assigned to the open driver who is predicted to have the shortest en route time. 

This matching algorithm is also called the on-call policy, the closest driver policy, and the committed driver-rider matching protocol.

### Shared Ride (Batching-based Optimization)
An alternative matching approach is batching where rider requests are collected for a short time window (typically on the order of seconds), at the end of which an optimization problem is solved to pair each request with an open driver.

If there are riders that are not matched in this batch, then they are carried over and used for the optimization problem in the next batching window. Batching can reduce the rider waiting time relative to the first-dispatch protocol by consolidating requests and making better use of supply.

Note that the first-dispatch protocol can be viewed as a special case of the batching protocol when each batch consists of exactly one rider request.

Due to its substantial benefits, batching has been implemented widely in major ride-hailing platforms.
