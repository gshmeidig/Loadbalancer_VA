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

### Conf 

Creat AddressPool with YML File:
```
apiVersion: metallb.io/v1beta1
kind: IPAddressPool
metadata:
    name: first-pool
    namespace: metallb-system
spec:
    addresses:
    -10.1.38.60-10.1.38.70
```

Apply AddressPool YML File:
```
kubectl -n metallb-system apply -f pool-1.yml
```

Verify deployed Pool:
```
kubectl -n metallb-system get IPAddressPool 
```

Create L2Advertisement:
```
apiVersion: metallb.io/v1beta1
kind: L2Advertisement
metadata:
 name: valab-l2
 namespace: metallb-system
spec:
 ipAddressPools:
 - first-pools
```

Apply L2Advertisement YML File:
```
kubectl -n metallb-system apply -f l2advertisement.yml
```

Verify deployed L2Advertisement:
```
kubectl -n metallb-system get l2advertisement 
```



vim Editor:
there are diffrent Modis:
- Insert :i (exit with ESC)

:set number --> Line number are visible
:wq --> write out

