# Day 1: The Genesis - Hardware & Architecture

### Building a Cybersecurity Range: Hardware Procurement and Lab Design

**Summary:**
Started the journey of building a dedicated home lab to support my studies in Network+, CCNA, Security+, and Pentest+. The goal is to create a realistic, segmented enterprise environment to practice both offensive (Red Team) and defensive (Blue Team) operations safely.

**Hardware Inventory:**
* **Compute:** 1x IBM Server (512GB RAM), multiple Dell Micro PCs.
* **Networking:** 5x Cisco Layer 2/Layer 3 Switches, 4x Cisco Routers.

**The Plan:**
I designed a multi-VLAN architecture to simulate a corporate network. The core network will be built on Cisco gear, with the IBM server acting as a Type 1 hypervisor host for services and targets.

**Key Segments Defined:**
* **VLAN 10 (Users):** Simulated employee workstations.
* **VLAN 20 (Servers):** "Production" servers (Domain Controller, Web Server) to be defended.
* **VLAN 66 (Pentest):** An isolated "dirty" network for attacker machines (Kali) and vulnerable targets (Metasploitable).
* **VLAN 99 (Management):** Out-of-band management for network gear and hypervisor access.

![Desc](./hardware_stack.png)
