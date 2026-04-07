# 🚨 Watchdog Security Guardian

**[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)**
**[![Stars](https://img.shields.io/github/stars/Hemaksh69/watchdog_security_guardian?style=social)](https://github.com/Hemaksh69/watchdog_security_guardian/stargazers)**
**[![Contributions Welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg?style=flat)](https://github.com/Hemaksh69/watchdog_security_guardian/issues)**

A **lightweight, regex-powered Bash script** that scans your codebase for **hardcoded secrets**, helping you prevent accidental credential leaks before they reach production. Think of it as your **first line of defense** against accidental data exposure.

---

## ✨ **Why Watchdog Security Guardian?**

### 🔐 **Protects Against:**
✅ **API Keys** (AWS, Google, Stripe, etc.)
✅ **Passwords & Tokens** (hardcoded in config files, scripts, or code)
✅ **Private Keys** (SSH, PGP, or encryption keys)
✅ **Base64 Encoded Secrets** (often used for obfuscation)
✅ **Exposed Email Addresses** (potential phishing targets)
✅ **Database Credentials** (MySQL, PostgreSQL, MongoDB)

### 🚀 **Key Features:**
🔍 **Fast & Lightweight** – No heavy dependencies, runs in seconds.
📊 **Clear Threat Reporting** – Shows detected secrets with risk levels.
💡 **Security Recommendations** – Suggests fixes for found issues.
📝 **Mock Alerts** – Simulates real-world security notifications.
🔄 **Easy to Extend** – Simple regex-based detection for custom patterns.

---

## 🛠️ **Tech Stack**
- **Language:** Bash (v4.0+)
- **Detection Method:** Regex-based pattern matching
- **Dependencies:** None (pure Bash)
- **Works On:** Linux, macOS, WSL (Windows Subsystem for Linux)

---

## 📦 **Installation**

### **Prerequisites**
- A **Bash-compatible shell** (GNU Bash recommended)
- **Basic file permissions** (read access to your codebase)

### **Quick Start (Copy-Paste Friendly!)**
```bash
# Clone the repository
git clone https://github.com/Hemaksh69/watchdog_security_guardian.git
cd watchdog_security_guardian

# Make the script executable
chmod +x watchdog.sh

# Run the scanner on a file or directory
./watchdog.sh path/to/your/codebase
