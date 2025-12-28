# Day 6: Virtualization Foundations - VMware ESXi 8 Setup

### The Compute Core: Installing and Configuring VMware ESXi 8

**Summary:**
Shifted focus from networking hardware to compute infrastructure. I installed VMware vSphere Hypervisor (ESXi 8) on the IBM server (512GB RAM) to serve as the virtualization host for my lab services.

**Networking Integration:**
The critical part was integrating ESXi with my existing Cisco VLAN infrastructure.
* Connected the ESXi host physical NIC to the trunk port configured on the L3 switch.
* Configured the Management Network to sit on VLAN 99.
* Created specialized **Port Groups** within the ESXi vSwitch, tagging them with VLAN IDs 10, 20, and 66. This allows me to drop any virtual machine directly into a specific network segment just by changing its settings in the hypervisor.

#VMware #ESXi #Virtualization #HomelabSetup
