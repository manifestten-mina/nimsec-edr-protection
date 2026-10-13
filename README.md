# nimsec-edr-protection

# 🛡️ NIMSec EDR Protection v2.5

**NIMSec EDR Protection** is an open-source, ultra-lightweight **Endpoint Detection and Response (EDR)** and Anti-Ransomware framework engineered specifically for Windows environments.

Developed under the **Nevzat İnan MTAL Security Lab** project umbrella, NIMSec goes beyond signature-based legacy protection by leveraging **Local PE Entropy Analysis (Heuristics)**, **Process & Memory Shields**, and **Canary Trap Mechanisms** to detect and neutralize Zero-Day threats in real time.

---

### ✨ Key Features

* **🧠 Local Heuristic & PE Entropy Engine:** Analyzes Portable Executable (PE) headers (`.exe`, `.dll`, `.scr`, `.vbs`) using Shannon's Entropy formula ($Entropy > 7.4$). Detects obfuscated, encrypted, or packed Zero-Day payloads without requiring an active internet connection.
* **🛡️ Ransomware Canary Trap:** Deploys honeypot files (`.nimsec_canary`) across critical user directories (`Documents`, `Desktop`, `Downloads`). The moment a ransomware process attempts to modify or encrypt a canary file, the engine instantly identifies its Process ID (PID) and terminates it.
* **🚀 Event-Driven Process & Memory Shield:** Utilizes optimized, event-driven process auditing instead of aggressive polling loops. Blocks malicious execution patterns such as shadow copy deletion (`vssadmin delete shadows`) or obfuscated PowerShell commands (`-encodedcommand`).
* **⚡ Ultra-Low Resource Overhead:** Engineered for high efficiency with **~0.1% CPU utilization** and **~20 MB RAM footprint**, ensuring zero system lag, freezing, or I/O bottlenecks.
* **🎛️ Dynamic Monitoring & HTML Reporting:** Real-time event log viewer, isolated quarantine vault management, and automated HTML forensic security report generation.

---

### 🛠️ Tech Stack & Dependencies

* **Core Language:** Python 3.10+
* **GUI & UX:** CustomTkinter, Pillow
* **Process & System Auditing:** `psutil`, `watchdog`, `winreg`
* **System Tray Integration:** `pystray`
* **OS Notifications:** `plyer`

---

### 🚀 Quick Start

#### 1. Clone the Repository & Install Dependencies

```bash
git clone [https://github.com/YOUR_USERNAME/nimsec-edr-protection.git](https://github.com/YOUR_USERNAME/nimsec-edr-protection.git)
cd nimsec-edr-protection
pip install customtkinter pystray pillow psutil watchdog requests plyer
