# 🛡️ Hybrid LKM Rootkit (C)

A powerful dual-layer Linux kernel rootkit with a userland controller — designed for stealth, red-teaming, and ethical cybersecurity research.

> 🚀 Made with 💻 by **Shibnath Hansda (HansdaTechs)**

---

## ✨ Features

This tool is a **hybrid rootkit** that combines the power of **Linux Kernel Module (LKM)** with a **userland interface**, offering stealth features commonly used in red team operations.

| Feature                    | Description                              |
|---------------------------|------------------------------------------|
| 🥷 PID Hiding              | Hide any running process by PID          |
| 🔐 /proc Interface         | Command interface through `/proc/hide`   |
| 💻 Userland Control Tool   | C-based CLI to trigger hide command      |
| ⚙️ Makefile-based Build    | Easy to compile both kernel/userland     |
| 📦 Installer Script        | Load/unload rootkit with one command     |
| 🧪 ARM + x86 Support       | Compatible with both architectures       |
| ✅ Ethical Design          | No persistence or malware behavior       |

--------

## 📁 Folder Structure

hybrid-rootkit/
├── kernel/
│ ├── invis_module.c # Kernel module to hide process
│ └── Makefile
├── userland/
│ ├── control.c # Userland PID hider interface
│ └── Makefile
├── installer.sh # Auto builder/loader/unloader
└── README.md

---------

## ⚙️ Installation

```bash
chmod +x installer.sh
./installer.sh build

#This builds both:-

invis_module.ko → kernel module

control → userland interface tool

-------------

🚀 Usage
1. Load the Kernel Rootkit
bash
Copy
Edit
sudo ./installer.sh load
2. Hide a PID
bash
Copy
Edit
ps aux | grep nc         # get the PID of target
sudo ./userland/control <PID_TO_HIDE>
✅ Process should now be hidden from ps, top, etc.

3. Unload the Rootkit
bash
Copy
Edit
sudo ./installer.sh unload
4. Clean All Binaries
bash
Copy
Edit
./installer.sh clean
📌 Requirements
Linux OS (Ubuntu/Kali/Debian recommended)

Kernel headers installed

gcc, make

Root privileges

⚠️ Legal Disclaimer
This project is intended only for educational and ethical research purposes.
Do not use this on unauthorized systems.
Run only inside isolated environments (VMs or labs).

.

🧑‍💻 Author
Created by Shibnath Hansda (HansdaTechs)

📷 YouTube Channel: HansdaTechs
🎯 Focus: Ethical Hacking |  Cyber Tools | CTF Labs | Bug Huntings 

📄 License
This project is licensed under the MIT License — you're free to use, modify, and distribute with credit.












