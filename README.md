# 🚘 Clustering and Trend Analysis for Ride-Sharing Demand and Behavior

## 🧩 Objective

_**How to solve the matching problem between riders and drivers?**_

This is a common problem faced by any company that facilitates transactions between counterparties. Specifically, a problem Uber faces is that sometimes drivers are not around when users need them. 

Even if riders and drivers are not that far away, if users have to **wait 10 to 15 minutes before being picked up**, then they will likely cancel their ride's pickup request. Uber's research shows that users have **a willingness-to-wait time of 5-7 minutes**.

Therefore, it is of first-order importance for Uber to have a methodology that is capable of **recommending hot-spot zones** for drivers to be in major cities in order to help facilitate the successful matching of riders and drivers. Note that these hot-spots can vary by day and intraday hours.

## 🧮 Proposed Solution
Use **clustering algorithms** to group pickups together, then define those groups (clusters) as hotspots where drivers should be encouraged to hang around.
- Analyze the pickup data
- Create clusters
- Assign pickups to clusters
> Rider-pickup clusters help create a matching rule that assigns a rider's pickup request to a group and then broadcast the pickup request to all drivers in the region defined by the cluster.
