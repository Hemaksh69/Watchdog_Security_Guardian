# 🚨 Watchdog Security Guardian

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Stars](https://img.shields.io/github/stars/Hemaksh69/Watchdog_Security_Guardian?style=flat)](https://github.com/Hemaksh69/Watchdog_Security_Guardian/stargazers)
[![Contributions Welcome](https://img.shields.io/badge/contributions-welcome-brightgreen.svg)](https://github.com/Hemaksh69/Watchdog_Security_Guardian/issues)

A lightweight, regex-powered Bash script designed to scan codebases for hardcoded secrets. Watchdog helps catch accidental credential leaks before they are committed, acting as a simple but effective security audit tool for your local environment.

---

## 🔐 What it detects:
Watchdog scans your files against patterns for common sensitive data, including:

* **API Keys:** AWS, Google, Stripe, and generic high-entropy strings.
* **Credentials:** Hardcoded passwords, database URIs (MongoDB, MySQL, Postgres).
* **Private Keys:** SSH, PGP, and general PEM blocks.
* **Encoded Data:** Base64 obfuscated secrets.
* **Leaks:** Exposed email addresses and internal configuration tokens.

---

## 🚀 Key Features:
* **Zero Dependencies:** Runs on pure Bash. No need for Python, Node.js, or external libraries.
* **High Speed:** Uses optimized `grep` and `find` logic to scan large directories in seconds.
* **Clear Reporting:** Outputs color-coded results directly to your terminal.
* **Risk Assessment:** Categorizes findings to help you prioritize what to fix first.
* **Customizable:** Easily add your own regex patterns to the script logic.

---

## 🛠️ Tech Stack
* **Language:** Bash (v4.0+)
* **Logic:** Regex-based pattern matching
* **Compatibility:** Linux, macOS, WSL

---

## 📦 Installation & Usage

### Prerequisites
* A Bash-compatible shell (GNU Bash is recommended).
* Standard Unix utilities (`grep`, `find`, `sed`).

### Quick Start
```bash
# Clone the repository
git clone [https://github.com/Hemaksh69/Watchdog_Security_Guardian.git](https://github.com/Hemaksh69/Watchdog_Security_Guardian.git)
cd Watchdog_Security_Guardian

# Make the script executable
chmod +x Watchdog

# Run the scanner on a file or directory
./Watchdog path/to/your/codebase
