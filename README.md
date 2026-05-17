<div align="center">

# Wazuh SIEM Deployment on Ubuntu Server 22.04

[![Ubuntu](https://img.shields.io/badge/Ubuntu-22.04.5_LTS-E95420?style=for-the-badge&logo=ubuntu&logoColor=white)](https://ubuntu.com/)
[![Wazuh](https://img.shields.io/badge/Wazuh-4.12.0-005571?style=for-the-badge&logo=wazuh&logoColor=white)](https://wazuh.com/)
[![VirtualBox](https://img.shields.io/badge/VirtualBox-7.x-183A61?style=for-the-badge&logo=virtualbox&logoColor=white)](https://www.virtualbox.org/)
[![Status](https://img.shields.io/badge/Status-Active%20%26%20Running-brightgreen?style=for-the-badge)]()

<br/>

*Full deployment of the Wazuh open-source SIEM/XDR platform on a virtualized Ubuntu Server environment — covering VM provisioning, OS installation, SSH access via PuTTY, and Wazuh all-in-one stack setup with a live web dashboard.*

<br/>

| Field | Details |
|---|---|
| *Course* | Threat Modelling and Security Monitoring Sessional |
| *Course Code* | SEC 203 |
| *Student* |Md Firoz Hasan|
| *ID* | 2304039 |
| *Submitted To* | Masud Rana (Lecturer) |

</div>

---

## 📌 Objective

Deploy and configure *Wazuh 4.12.0* — an open-source Security Information and Event Management (SIEM) and Extended Detection & Response (XDR) platform — on *Ubuntu Server 22.04.5 LTS* running inside Oracle VirtualBox. Access the server remotely via PuTTY over SSH and verify the full stack through the Wazuh web dashboard.

---

## 🧰 Stack & Tools

| Category | Tool / Version |
|---|---|
| Hypervisor | Oracle VirtualBox |
| Guest OS | Ubuntu Server 22.04.5 LTS |
| SIEM Platform | Wazuh 4.12.0 (All-in-One) |
| SSH Client | PuTTY 0.83 |
| Browser | Mozilla Firefox |
| Network | NAT / Host-Only — IP ⁠ 192.168.1.20 ⁠ |

---

## 🏗️ Architecture


┌─────────────────────────────────────────────────┐
│              Windows Host Machine                │
│                                                  │
│  ┌─────────────────────────────────────────┐    │
│  │        VirtualBox VM                    │    │
│  │   Ubuntu Server 22.04.5 LTS            │    │
│  │   IP: 192.168.1.20                     │    │
│  │                                         │    │
│  │  ┌──────────┐  ┌──────────┐  ┌──────┐ │    │
│  │  │  Wazuh   │  │  Wazuh   │  │Wazuh │ │    │
│  │  │ Manager  │  │ Indexer  │  │ Dash │ │    │
│  │  │(OSSEC)   │  │(OpenSrch)│  │board │ │    │
│  │  └──────────┘  └──────────┘  └──────┘ │    │
│  └─────────────────────────────────────────┘    │
│                                                  │
│   PuTTY (SSH :22) ──────────► VM Terminal       │
│   Firefox (HTTPS :443) ──────► Wazuh Dashboard  │
└─────────────────────────────────────────────────┘


---

## 📸 Lab Walkthrough

### 1 — Download Ubuntu Server ISO

Downloaded Ubuntu Server 22.04.5 LTS from the official Canonical website.

<img width="1427" height="637" alt="u1" src="https://github.com/user-attachments/assets/33fd91ae-70ef-49ef-96ac-c266022bed52" />



---

### 2 — Create Virtual Machine in VirtualBox

Configured the VM with name, ISO image path, OS type (Linux / Ubuntu 64-bit), RAM, CPU, and disk size.

<img width="671" height="573" alt="u2" src="https://github.com/user-attachments/assets/12081b78-59c7-4463-9888-32c6867a5836" />

<img width="543" height="518" alt="u3" src="https://github.com/user-attachments/assets/dc1d935b-5816-4959-952e-42e7f276ba8b" />

<img width="540" height="535" alt="u4" src="https://github.com/user-attachments/assets/7fd3a3ff-deb4-4df1-adcb-bf65db4eb790" />
<img width="520" height="556" alt="u5" src="https://github.com/user-attachments/assets/6c8003d6-0348-4cc9-a61f-ea18fa290b99" />

---

### 3 — Ubuntu Server Installation

Walked through the full Ubuntu Server text-based installer — language, install type, network, proxy, mirror, and storage layout.



<img width="1313" height="692" alt="u6" src="https://github.com/user-attachments/assets/715b3074-1e63-4880-a598-16d0cc7fdba8" />
<img width="1265" height="764" alt="u7" src="https://github.com/user-attachments/assets/96676ab3-36ef-4a18-8079-b9c28febf309" />


<img width="1235" height="585" alt="u8" src="https://github.com/user-attachments/assets/a3de9bcf-0bf4-4af4-90de-4ea8e614d9da" />

<img width="1089" height="551" alt="u9" src="https://github.com/user-attachments/assets/081fcf65-7382-402c-9472-de0cdc466f8b" />

<img width="1171" height="466" alt="u10" src="https://github.com/user-attachments/assets/ef3db04b-d60e-4527-abfa-aefcfe3526be" />

<img width="1152" height="650" alt="u11" src="https://github.com/user-attachments/assets/be7618f6-4a56-4761-b9a6-fb9d13f859c8" />


<img width="1278" height="377" alt="u12" src="https://github.com/user-attachments/assets/ebbed8bc-60d1-40ed-a856-0708059b3364" />
<img width="1272" height="279" alt="u13" src="https://github.com/user-attachments/assets/dc68d82a-21c2-48ac-b333-bd8c71cac2af" />
<img width="1274" height="666" alt="u14" src="https://github.com/user-attachments/assets/da7583fe-c104-42c0-bda8-b53b9317f207" />
<img width="1265" height="390" alt="u15" src="https://github.com/user-attachments/assets/480f3734-b027-4569-b6fd-59266497d79c" />

<img width="1470" height="931" alt="u16" src="https://github.com/user-attachments/assets/df065945-3f84-44f8-9fe2-5bcfe27789ad" />

---

### 4 — Post-Installation Login & SSH Access

Logged into the server directly from the VirtualBox console, then connected remotely using PuTTY over SSH.

![First Login — Ubuntu Console](screenshots/13.png)
![PuTTY — Host Configuration (192.168.1.20 :22)](screenshots/22.png)
![PuTTY — Successful SSH Session](screenshots/23.png)

---

### 5 — Wazuh Installation

Installed Java (required dependency), downloaded the official Wazuh install script, and ran the all-in-one deployment which provisions the Manager, Indexer, and Dashboard in a single pass.







![Installation Complete — Credentials Displayed](screenshots/17.png)

---

### 6 — Network Verification

Confirmed the VM's IP address (⁠ 192.168.1.20 ⁠) using ⁠ ip a ⁠ to ensure it is reachable from the host browser.

![IP Address Verification](screenshots/18.png)

---

### 7 — Wazuh Web Dashboard

Navigated to ⁠ https://192.168.1.20 ⁠ from the host browser. Bypassed the self-signed TLS certificate warning (expected in a lab environment) and logged in with the auto-generated admin credentials.

![Browser TLS Warning — Self-Signed Cert](screenshots/19.png)
![Wazuh Login Page](screenshots/20.png)
![Wazuh Dashboard Overview](screenshots/21.png)

---

### 8 — Service Status Verification

Confirmed all three Wazuh components are active and running via ⁠ systemctl ⁠.

![Wazuh Manager — Active (running)](screenshots/24.png)
![Wazuh Indexer — Active (running)](screenshots/25.png)
![Wazuh Dashboard — Active (running)](screenshots/26.png)

---

## ✅ Results

| Component | Status |
|---|---|
| Ubuntu Server 22.04.5 LTS | ✅ Installed & Running |
| SSH Access via PuTTY | ✅ Connected on port 22 |
| Wazuh Manager | ✅ Active (running) |
| Wazuh Indexer (OpenSearch) | ✅ Active (running) |
| Wazuh Dashboard | ✅ Active (running) |
| Web Dashboard Access | ✅ Accessible at https://192.168.1.20 |

---

## 💻 Key Commands Used

⁠ bash
# Check IP address
ip a
hostname -I

# Update system
sudo apt update && sudo apt upgrade -y

# Install Java (Wazuh dependency)
sudo apt install default-jdk -y

# Download Wazuh installer
sudo curl -sO https://packages.wazuh.com/4.12/wazuh-install.sh

# Run all-in-one installation
sudo bash wazuh-install.sh -a

# Verify services
systemctl status wazuh-manager --no-pager
systemctl status wazuh-indexer --no-pager
systemctl status wazuh-dashboard --no-pager
 ⁠

---

## 📝 Conclusion

This lab successfully demonstrated the end-to-end deployment of a *Wazuh SIEM/XDR stack* on a virtualized Ubuntu Server environment. All three core components — Manager, Indexer, and Dashboard — were verified as active and operational. The web dashboard is fully accessible and ready for endpoint agent enrollment, log analysis, threat hunting, and compliance monitoring.

The deployment provides a solid foundation for further NetGuard integration, where Wazuh can serve as the central alert aggregation and correlation layer.

---

<div align="center">

*Md Firoz Hasan* · ID: 2304039 · SEC 203


</div>
