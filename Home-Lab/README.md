
# My Cybersecurity Home Lab

This document outlines the architecture and components of my personal cybersecurity home lab. The environment is built on enterprise-grade hardware and uses network segmentation via VLANs to simulate a realistic corporate network.

The purpose of this lab is to provide a sandboxed environment for practicing penetration testing techniques, understanding network security controls, and studying for advanced certifications.

## Lab Diagram

![My Enterprise Lab Network Diagram](./home_lab_diagram.png)

## Core Components

* **Physical Hardware:** IBM Server, Layer 3 Switch (e.g., Cisco Catalyst)
* **Hypervisor:** VMware ESXi 8
* **Networking:** VLAN-based segmentation with Inter-VLAN routing managed by a Layer 3 switch.
    * **VLAN 10:** USERS (10.10.1.0/24)
    * **VLAN 20:** SERVERS (10.20.1.0/24)
    * **VLAN 66:** PENTEST (10.66.1.0/24)
    * **VLAN 99:** MANAGEMENT (10.99.1.0/24)

## Table of Contents

1.  [Lab Architecture](./01_Lab_Architecture.md)
2.  [Virtual Machine Setup](./02_Virtual_Machine_Setup.md)
3.  [Networking Configuration](./03_Networking_Configuration.md)
4.  [Experiments and Write-ups](./Experiments/)
5.  [Build Log](./Build-Log/)
