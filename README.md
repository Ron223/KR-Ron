# KR-Ron
# Ettercap Network MITM Simulation in VirtualBox (Educational Lab)

> **⚠️ Ethical Use Only:**  
> This lab is designed for **educational and defensive purposes only**.  
> Do **not** run these techniques on production or public networks.  
> Always use an **isolated VirtualBox network** and get explicit permission from network owners.

---

## 📌 Project Overview
This project demonstrates **network-layer man-in-the-middle (MITM) concepts** using [Ettercap](https://www.ettercap-project.org/) in a safe, offline lab environment built with [VirtualBox](https://www.virtualbox.org/).

**Goals:**
- Understand ARP poisoning concepts.
- Capture, detect, and analyze suspicious traffic.
- Develop defensive strategies and IDS rules.
- Practice ethical cybersecurity testing in a closed lab.

---

## 🏗 Lab Architecture

### Virtual Machines
| Role           | OS Example               | Purpose                                      |
|----------------|--------------------------|----------------------------------------------|
| **Attacker**   | Kali Linux               | Runs Ettercap to simulate MITM               |
| **Victim**     | Windows 10 / Ubuntu      | Generates normal user traffic                |
| **Gateway**    | Ubuntu Server / Metasploitable | Acts as a server or DNS target               |
| **Monitor**    | Security Onion / Ubuntu  | Runs Wireshark, Suricata, or Zeek for detection |

### Network Layout
- **VirtualBox Internal Network**: `lab-net`
- All VMs attached to `lab-net` (no internet, no bridging)
- Optionally use **Host-Only** adapter for instructor monitoring

