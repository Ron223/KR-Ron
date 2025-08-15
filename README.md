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
  
Victim ↔ Gateway ↔ Attacker ↔ Monitor
```

**Diagram:**
![Network Diagram](docs/network_diagram.png)

---

## 🚀 Getting Started

1. **Clone the Repository**
   ```bash
   git clone https://github.com/Ron223/ettercap-virtualbox-lab.git
   cd ettercap-virtualbox-lab
   ```

2. **Prepare ISOs**
   - Download OS images for chosen VMs.
   - Place them in an `isos/` folder (not tracked in Git).

3. **Set Up VirtualBox**
   - Create VMs per architecture table above.
   - Attach all to `lab-net` (Internal Network mode).
   - Take snapshots before running any simulations.

4. **Generate Baseline Traffic**
   - From Victim VM: browse internal web pages, perform DNS lookups.
   - Capture traffic on Monitor VM using Wireshark.

5. **Run Authorized MITM Simulation**
   - Instructor (or authorized learner) runs Ettercap in Attacker VM.
   - Observe and log changes in network behavior.

6. **Analyze & Mitigate**
   - Compare baseline vs. attack captures.
   - Test mitigations: static ARP, HTTPS enforcement, VLAN segmentation.

---

## 📚 Learning Outcomes
- Identify network anomalies in packet captures.
- Recognize ARP poisoning patterns.
- Understand differences between plaintext and encrypted traffic security.
- Apply defensive measures to mitigate MITM risks.

---

## 📂 Repository Structure
```
ettercap-virtualbox-lab/
│
├── docs/                     # Documentation, diagrams, screenshots
│   ├── network_diagram.png
│   └── lab_instructions.pdf
│
├── pcaps/                    # Example PCAP files (optional)
│   ├── baseline.pcap
│   └── mitm_attack.pcap
│
├── templates/
│   └── lab_report_template.md
│
├── README.md
└── LICENSE
```

 Lab Report Template
The `templates/lab_report_template.md` helps track your learning:

```markdown
# Lab Report — Ettercap MITM Simulation

## Objectives
(Brief description of what you aimed to learn)

## Environment
(VMs used, network layout, software versions)

## Steps Taken
(Setup, baseline traffic generation, attack simulation, analysis)

## Observations
- Baseline Traffic:
- Changes Noticed:
- Security Risks Found:

## Mitigation Actions
(Measures tested and their effectiveness)

## Reflection
(Skills gained and lessons learned)
```

---

## 🔐 Safety Guidelines
- Only use **VirtualBox Internal Network** or **Host-Only**.
- Never connect lab VMs to real networks.
- Always revert to a clean snapshot after testing.
- Keep notes and screenshots for learning review.

---

## 📚 References
- [Ettercap Project](https://www.ettercap-project.org/)
- [VirtualBox Networking Guide](https://www.virtualbox.org/manual/ch06.html)
- [Suricata IDS](https://suricata.io/)
- [Wireshark](https://www.wireshark.org/)
- [Zeek Network Security Monitor](https://zeek.org/)

---



