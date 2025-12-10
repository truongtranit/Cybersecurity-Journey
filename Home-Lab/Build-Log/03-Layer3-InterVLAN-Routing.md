# Day 3: Layer 3 Core - Inter-VLAN Routing (SVIs)

### Making Connections: Implementing Inter-VLAN Routing with SVIs

**Summary:**
With Layer 2 setup, devices in different VLANs couldn't communicate. Today, I turned my core switch into a Layer 3 device to handle Inter-VLAN routing.

**Implementation:**
Instead of using a "Router on a Stick" topology, I utilized the Layer 3 capabilities of my core switch by creating **Switched Virtual Interfaces (SVIs)**. I assigned IP addresses to `interface vlan 10`, `vlan 20`, etc., to act as the default gateways for each subnet.

**Troubleshooting Initial Connectivity:**
I ran into an immediate issue where I couldn't ping across subnets.
* *Diagnosis:* I realized I hadn't actually enabled the routing function on the switch globally.
* *Fix:* Issued the critical command: `ip routing`. Connectivity between VLANs was immediately established.

![Desc](./core_running_config.png)

#Layer3Switching #InterVLANRouting #Cisco #NetworkingTroubleshooting
