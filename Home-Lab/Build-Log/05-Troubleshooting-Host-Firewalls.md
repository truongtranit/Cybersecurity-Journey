# Day 5: The Invisible Wall - Troubleshooting Host Firewalls

### The Silent Blocker: Diagnosing Host-Based Firewall Issues

**Summary:**
A major troubleshooting session occurred today. Despite having perfect routing and no Access Control Lists (ACLs) on the network gear yet, my PCs in different VLANs suddenly stopped being able to ping each other, though they could still ping their gateways.

**The Investigation:**
* I verified routing tables on the switch—they were correct.
* I verified IP configurations on the endpoints—they were correct.
* I ran `show access-lists` on the Cisco gear to ensure no rogue configs existed—none did.

**The Breakthrough:**
I realized that while the network was delivering the packets, the *operating systems* on the destination devices were dropping them. Modern OSs (Windows 10/11, recent Linux distros) have host-based firewalls enabled by default that block incoming ICMP (ping) requests from different subnets.

**Resolution:** Temporarily disabled `ufw` (Linux) and Windows Defender Firewall on endpoints to confirm connectivity. This was a valuable lesson in checking all layers of the OSI model, not just the network gear.

#Troubleshooting #SysAdmin #Firewalls #Networking
