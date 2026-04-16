# 🌐 Retail Technical Network - Comprehensive Training Report

## 📖 Overview
[cite_start]This repository contains the detailed Summer Training Report focusing on the Retail Technical Network at Telecom Egypt (WE). [cite_start]It serves as a technical manual for configuring, managing, and troubleshooting customer premises equipment (CPE) across DSL, Fiber (FTTH), and Mobile Internet technologies[cite: 22, 24, 26, 269].

## 🧑‍🎓 Training & Administrative Details
* [cite_start]**Trainee Name:** Hazem Hamdi Mahmoud Abdelqader [cite: 4]
* [cite_start]**University:** NUB - Nahda University [cite: 6]
* [cite_start]**Faculty:** Faculty of Engineering Communications and Electronics Engineering [cite: 8]
* [cite_start]**Training Provider:** We, Telecom Egypt [cite: 10]
* [cite_start]**Training Location:** Alharih Central in Fayoum [cite: 20]
* [cite_start]**Company Supervisor:** Mr. Aymen Hossam El-Din [cite: 12]
* [cite_start]**Academic Supervisor:** Engineer: Paula Atef Naguib [cite: 14]
* **Contact:** h.hamdy0491@nub.edu.eg | [cite_start]+20 106 238 6571 [cite: 16, 18]
* [cite_start]**Submission Date:** 24/8/2025 [cite: 19]

---

## 📡 1. DSL, VDSL & SuperVector (Copper Networks)

### Technology Comparison
| Feature | ADSL Router | VDSL Router | SuperVector Router |
| :--- | :--- | :--- | :--- |
| **Max Speeds** | [cite_start]Up to 15 Mbps DL / 1 Mbps UL [cite: 28] | [cite_start]Up to 100 Mbps DL / 30 Mbps UL [cite: 28] | [cite_start]Up to 300 Mbps DL / 100 Mbps UL [cite: 28] |
| **Distance Limit** | [cite_start]Performs poorly beyond 2 km [cite: 29] | [cite_start]Performs well up to 1 km [cite: 29] | [cite_start]Best performance under 500 meters [cite: 29] |
| **Use Case** | [cite_start]Basic browsing, email [cite: 29] | [cite_start]HD streaming, online gaming [cite: 29] | [cite_start]4K streaming, smart home, heavy usage [cite: 29] |
| **Line Sensitivity**| [cite_start]Very sensitive to line quality [cite: 28] | [cite_start]Moderate [cite: 28] | [cite_start]Improved noise cancellation [cite: 28] |

### Troubleshooting
* [cite_start]**Physical Issues:** Cutting in the wire (causing Data/Voice Down), wrong card configuration (two lines in the same port), or physical instability (rusted cable, hardware problems)[cite: 30, 33, 34, 35, 36, 40, 42, 44, 45].
* [cite_start]**Logical Issues (Managed by NOC):** IP Conflicts (two devices on the same IP), DNS Errors (failure to resolve website addresses), and DHCP failures (device fails to obtain IP)[cite: 49, 50, 51, 52, 53, 54, 55, 56].

### Device Configurations
* **Huawei HG531 V1 (ADSL):** Access via `192.168.1.1` (User/Pass: `admin`/`admin`). [cite_start]Set VPI/VCI to `0/35` in Basic → WAN[cite: 130, 133, 135, 136, 138, 141].
* **ZTE ZXHN H168N (VDSL):** Access via `192.168.1.1` (User: `admin`, Pass: On sticker). [cite_start]Set WAN Type to VDSL[cite: 146, 148, 150, 151, 153, 154].
* **Huawei DN8245V (SuperVector):** Access via `192.168.1.1` (User: `telecomadmin`, Pass: On sticker). [cite_start]Configured under Internet → WAN[cite: 158, 160, 162, 163, 165].

---

## ⚡ 2. FTTH: ONT & ONU (Fiber Networks)

### Device Comparison
* [cite_start]**ONT (Optical Network Terminal):** Typically installed inside the home, provides full fiber speeds (1 Gbps+), includes built-in Wi-Fi/router capabilities, and is powered by the customer[cite: 57, 59]. 
* [cite_start]**ONU (Optical Network Unit):** Used in shared buildings, may have fewer ports, usually requires a separate external router, and is powered from a shared cabinet[cite: 57, 59].

### Troubleshooting
* [cite_start]**Physical Layer:** Inspect/clean SC/APC or LC connectors and check for bends or breaks[cite: 61, 62, 63, 64]. [cite_start]Use a power meter to ensure Rx levels are between **-28 to -8 dBm**[cite: 66].
* [cite_start]**LED Indicators:** * PON LED off/blinking = no sync with OLT[cite: 72]. 
  * [cite_start]LOS (Loss of Signal) ON = fiber break or dirty connector[cite: 73, 75].
* [cite_start]**Logical Layer:** Verify IP assignment, check DHCP pools, and run ping/traceroute to the OLT gateway or `8.8.8.8`[cite: 81, 82, 83, 84, 85].

### Device Configurations
* **Huawei EchoLife HG8245H (ONT):** Access via `192.168.100.1` (User: `telecomadmin`, Pass: `admintelecom` or `admin@Huawei123`). [cite_start]Set WAN Mode to `Route WAN`, Connection to `PPPoE`, and Enable VLAN ID `835`[cite: 225, 230, 232, 233, 237, 238, 239].
* **ZTE ZXHN F660 (ONU):** Access via `192.168.1.1` (User/Pass: `admin`/`admin`). [cite_start]Set Connection Type to `Bridge` with VLAN ID `835`, then connect to an external router (e.g., TP-Link) to handle PPPoE, Wi-Fi, and NAT[cite: 248, 254, 255, 256, 260, 261, 263, 265, 266].

---

## 📱 3. Mobile Internet (MiFi, Wingle, WE Air)

### Device Comparison
| Feature | MiFi | Wingle | WE Air |
| :--- | :--- | :--- | :--- |
| **Portability / Power** | [cite_start]High (Rechargeable battery) [cite: 86] | [cite_start]Medium (USB powered) [cite: 86] | [cite_start]Low (Fixed AC adapter) [cite: 86] |
| **Max Devices** | [cite_start]10-15 devices [cite: 86] | [cite_start]5-10 devices [cite: 86] | [cite_start]32+ devices [cite: 86] |
| **Max Speeds** | [cite_start]Up to 150 Mbps [cite: 86] | [cite_start]Up to 150 Mbps [cite: 86] | [cite_start]Up to 300 Mbps [cite: 86] |
| **Best For** | [cite_start]On-the-go travel/outdoors [cite: 86] | [cite_start]Laptop/PC users [cite: 86] | [cite_start]Stable home/office high-speed [cite: 86] |

### Troubleshooting
* [cite_start]**Connection Issues:** Check SIM status/data balance, verify signal strength, or restart device[cite: 90, 91, 93, 95, 97]. [cite_start]If a Wingle is not detected, check USB ports, missing drivers, or power supply[cite: 99, 100, 102, 105].
* [cite_start]**Speed/Signal Issues:** Network congestion or too many connected users can slow speeds[cite: 106, 107, 109, 110]. [cite_start]Ideal signal quality should be between **-70 dBm to -90 dBm**[cite: 111, 112]. [cite_start]Some models allow frequency band locking to 1800 MHz (4G)[cite: 113, 114].
* [cite_start]**Wi-Fi Issues:** Check for hidden SSIDs, reset incorrect passwords via admin panel, or change Wi-Fi channels to reduce interference[cite: 115, 117, 119, 121, 122].

### Device Configurations
* **Huawei E5577Cs-321 (MiFi):** Access via `192.168.8.1` (User/Pass: `admin`/`admin`). [cite_start]Set APN to `internet.te.eg` in Profile Management[cite: 174, 178, 179, 180, 182, 184].
* **Huawei E8372h-608 (Wingle):** Access via `192.168.1.1` (User/Pass: `admin`/`admin`). [cite_start]Set APN to `internet.te.eg` in Profile Management[cite: 189, 195, 196, 197, 199, 201].
* **ZTE MF253V (WE Air):** Access via `192.168.1.1` (User/Pass: `admin`/`admin`). [cite_start]Go to Network → APN Settings, set APN to `internet.te.eg`, and Mode to `Auto`[cite: 206, 212, 213, 214, 216, 217, 218].

---

## 📚 Glossary
* [cite_start]**CPE:** Customer Premises Equipment[cite: 269].
* [cite_start]**BLQ:** Bad Line Quality[cite: 269].
* [cite_start]**STB:** Receiver which is responsible for IPTV[cite: 270].
* [cite_start]**DHCP:** Dynamic Host Configuration Protocol[cite: 271].
