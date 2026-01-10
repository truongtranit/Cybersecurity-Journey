# Day 7: Building the Thunderdome - Isolation via ACLs

### Network Segmentation: Isolating the Pentest Zone with Cisco ACLs

**Summary:**
With the network functional, it was time to secure it. The goal was to isolate VLAN 66 (the "dirty" Pentest VLAN containing Kali and vulnerable targets) so it could not access my "production" or management networks.

**Implementation:**
I wrote an Extended Access Control List (ACL) named `PENTEST_BLOCK` on the Layer 3 switch.
* The ACL explicitly denies IP traffic sourced from the `10.66.1.0/24` subnet destined for any other internal subnet (`10.10.1.0`, `10.99.1.0`, etc.).
* It includes a final `permit ip any any` to allow internet access.

**Application Strategy:**
I applied this ACL in the **outbound** direction on the `interface Vlan66` SVI (`ip access-group PENTEST_BLOCK out`). This prevents any traffic *leaving* the Pentest VLAN subnet from entering the rest of the switch's routing engine if it matches the denied criteria.

#NetworkSecurity #ACL #CiscoSecurity #Segmentation
