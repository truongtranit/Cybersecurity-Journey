# Lab Architecture

## Physical Hardware

* **Server:** IBM System x Server
* **Switch:** Cisco Catalyst 3750 X Series Layer 3 Switch

## Hypervisor

* **Platform:** VMware ESXi 8.0.3
* **Management:** The ESXi host is managed via a web client connected to the **Management VLAN (99)**.

## Design Philosophy

The lab is designed to mirror a professionally segmented network. Each VLAN represents a different security zone. The **Pentest VLAN (66)** serves as the attacker's launch point, while targets are placed in the **Users (10)** and **Servers (20)** VLANs. All inter-VLAN traffic is routed through the Layer 3 switch, allowing for the future implementation of Access Control Lists (ACLs) to practice bypassing network security controls.
