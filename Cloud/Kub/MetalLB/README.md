# MetalLB
## Info
MetalLB is a tool for Kubernetes clusters without a cloud provider. It offers network load balancing by assigning IP addresses and making them accessible externally. It has two main features: address allocation and external announcement. Address allocation involves defining IP address pools, while external announcement uses standard networking protocols (ARP, NDP, or BGP) to inform the network about IP addresses residing in the cluster. In layer 2 mode, address discovery protocols are used, and in BGP mode, BGP peering enables true load balancing and traffic control across nodes.

Mad with Version: v0.13.11

## Installation

There are four possibilities to install <strong>MetalLB</strong>. Please check on teh [MetalLB](https://metallb.universe.tf/installation/) Webseit to verify what's best for the System.

To check Installation:
```
kubectl -n metallb-system get pods
```
Check alongside installed Ressources:
```
kubectl api-ressources | grep metallb
```

## Configuration

There are also diffrent Ways to Configura [MetalLB](https://metallb.universe.tf/configuration/), so again verify whats best.

### AdressPool

