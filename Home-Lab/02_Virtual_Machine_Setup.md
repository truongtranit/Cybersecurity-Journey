# Virtual Machine Setup Notes

## 1. Kali Linux (Attacker VM)

* **OS Version:** Kali Linux 2025.x
* **Purpose:** Attacker machine for running scans and exploits.
* **ESXi Port Group:** `PG-VLAN66-PENTEST`
* **VLAN:** 66
* **IP Address:** 10.66.1.10 (Static)
* **Gateway:** 10.66.1.1

## 2. Metasploitable2 (Linux Server Target)

* **OS Version:** Ubuntu 8.04 (Deliberately Vulnerable)
* **Purpose:** A primary target with numerous known vulnerabilities.
* **ESXi Port Group:** `PG-VLAN20-SERVERS`
* **VLAN:** 20
* **IP Address:** 10.20.1.20 (Static)
* **Gateway:** 10.20.1.1

## 3. Windows 10 (User Workstation Target)

* **OS Version:** Windows 10 Pro (unpatched, firewall disabled)
* **Purpose:** To simulate a typical, vulnerable user workstation.
* **ESXi Port Group:** `PG-VLAN10-USERS`
* **VLAN:** 10
* **IP Address:** 10.10.1.30 (Static)
* **Gateway:** 10.10.1.1
