
# Networking Configuration

The lab's network is architected around a Layer 3 switch that manages four distinct VLANs. The IBM server running ESXi connects to the switch via a trunk port, allowing virtual machines to be placed into any of the defined VLANs.

## 1. VLAN Configuration

| VLAN ID | Name        | IP Subnet         | Gateway (SVI on L3 Switch) | Purpose                                          |
| :------ | :---------- | :---------------- | :------------------------- | :------------------------------------------------|
| 10      | USERS       | `10.10.1.0/24`    | `10.10.1.1`                | Simulates a standard user workstation segment.   |
| 20      | SERVERS     | `10.20.1.0/24`    | `10..20.1.1`               | Hosts target servers and services.               |
| 66      | PENTEST     | `10.66.1.0/24`    | `10.66.1.1`                | Isolated network for the attacker machine.       |
| 99      | MANAGEMENT  | `10.99.1.0/24`    | `10.99.1.1`                | For managing network hardware and the ESXi host. |

## 2. Inter-VLAN Routing

Routing between the VLANs is enabled on the Layer 3 switch. Each VLAN has a Switched Virtual Interface (SVI) configured with the gateway IP address listed above. The `ip routing` command is enabled, allowing devices in one VLAN to communicate with devices in another (e.g., for the Kali machine in VLAN 66 to attack a server in VLAN 20).

## 3. ESXi Host Networking

* The physical network adapter of the IBM server is connected to a switchport configured as an **IEEE 802.1Q trunk**.
* Within ESXi, a separate **Port Group** is created for each VLAN.
* Each Port Group is tagged with its corresponding VLAN ID (e.g., `PG-VLAN20-SERVERS` is tagged with VLAN ID 20).
* Assigning a Virtual Machine to a Port Group connects it to the correct VLAN.
