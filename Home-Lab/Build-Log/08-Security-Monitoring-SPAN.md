# Day 8: The Watchtower - Designing Security Monitoring with SPAN

### Eyes on the Network: Designing Intrusion Detection with SPAN and ESXi

**Summary:**
To practice Blue Team defensive skills, I needed a way to monitor network traffic. I decided to deploy Security Onion as my IDS/SIEM platform.

**The Challenge:**
How to get raw network traffic from the physical Cisco switch into a virtual machine inside ESXi.

**The Solution:**
1.  **Physical:** Dedicated a specific port on the L3 switch as a **SPAN (Switched Port Analyzer) destination** and connected it to a second physical NIC on the IBM server.
2.  **Cisco Config:** Configured a monitor session on the switch to mirror traffic from VLANs 10, 20, and 66 to that destination port.
3.  **Virtual Config:** Created a new, dedicated vSwitch in ESXi connected to that second NIC. Crucially, I enabled **Promiscuous Mode** on this vSwitch so the virtual interface could accept traffic not addressed to its own MAC address.

This setup provides a "tap" for the Security Onion VM to sniff live wire traffic.

![Desc](./flow_of_mirrored_traffic.png)



#BlueTeam #SPANPort #NetworkMonitoring #ESXiNetworking
