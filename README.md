<div align="center">

# Watchdog Security Guardian

### Automated Secret Detection & Leak Prevention Engine

[![License](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge&color=2ea44f)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/Version-1.0.0-brightgreen?style=for-the-badge&logo=github&color=2ea44f)](https://github.com/Hemaksh69/Watchdog_Security_Guardian/releases)
[![Status](https://img.shields.io/badge/Status-Active-brightgreen?style=for-the-badge&logo=checkmarx&logoColor=white&color=2ea44f)](https://github.com/Hemaksh69/Watchdog_Security_Guardian)
[![ShellCheck](https://img.shields.io/badge/ShellCheck-Passing-brightgreen?style=for-the-badge&logo=gnu-bash&logoColor=white&color=2ea44f)](https://github.com/koalaman/shellcheck)
[![Code Quality](https://img.shields.io/badge/Code%20Quality-A+-blue?style=for-the-badge&color=2ea44f)](https://github.com/Hemaksh69/Watchdog_Security_Guardian)
[![PRs Welcome](https://img.shields.io/badge/PRs-Welcome-brightgreen?style=for-the-badge&color=2ea44f)](https://github.com/Hemaksh69/Watchdog_Security_Guardian/pulls)
[![Platform](https://img.shields.io/badge/Platform-Linux%20%7C%20macOS%20%7C%20WSL-informational?style=for-the-badge&color=007ec6)](https://github.com/Hemaksh69/Watchdog_Security_Guardian)
[![Security Scan CI](https://github.com/Hemaksh69/Watchdog_Security_Guardian/actions/workflows/main.yml/badge.svg)](https://github.com/Hemaksh69/Watchdog_Security_Guardian/actions/workflows/main.yml)

<br/>

> *"The most effective security gate is the one closest to the developer."*

<br/>

[Overview](#-overview) · [Key Capabilities](#-key-capabilities) · [Quick Start](#-quick-start) · [CI/CD Integration](#-cicd-integration)

---

</div>

## 📖 Overview

**Watchdog Security Guardian** is a high-performance, regex-powered secret detection engine built for modern development workflows. Engineered for **zero-dependency portability**, it performs static analysis against codebases, configuration files, and documentation to identify high-entropy strings, API keys, private credentials, and other sensitive data before they are committed to version control. By integrating seamlessly into pre-commit hooks and CI/CD pipelines, Watchdog enforces a critical security gate, operationalizing the **'shift-left' philosophy** by preventing secrets from ever entering the repository history.

Unlike heavyweight static analysis security testing (SAST) tools that require complex setup or cloud services, Watchdog is a pure, POSIX-compliant Bash script. It achieves sub-second scan times through optimized `grep` and `find` operations, delivering immediate, actionable feedback directly in the terminal. Its design prioritizes speed, simplicity, and extensibility, making it an essential utility for individual developers and large engineering teams alike.

---

## 🎯 Key Capabilities

| Capability | Description | Detection Method |
|:---|:---|:---|
| **API Key & Token Scanning** | Detects secrets for major cloud providers (AWS, Google Cloud) and SaaS platforms (Stripe, Twilio), along with generic API tokens. | Provider-specific key prefixes and high-entropy string analysis via `grep -E`. |
| **Private Key Identification** | Identifies leaked cryptographic private keys, including SSH (RSA/ED25519), PGP, and generic PEM-encoded keys. | Regex matching for standard PEM block boundaries (`BEGIN/END PRIVATE KEY`). |
| **Credential & URI Exposure** | Finds hardcoded database connection strings, user credentials, and authentication tokens within configuration files and source code. | Heuristic matching for common URI schemes (`mongodb://`, `postgres://`) and password-like strings. |
| **High-Entropy String Analysis** | Catches generic, unclassified secrets by identifying long, random alphanumeric strings common in Base64 or Hex-encoded tokens. | Shannon entropy calculation heuristics combined with character set and length-based regex. |
| **Structured, Prioritized Reporting** | Outputs color-coded, line-specific findings directly to the console, categorized by risk level (Critical, High, Medium) for rapid triage. | Formatted `echo` output with ANSI escape codes for clear, human-readable reports. |
| **Zero-Dependency Execution** | Runs on any Unix-like system with a standard Bash shell and core utilities, requiring no external libraries or interpreters. | Pure Bash 4.0+ implementation using `grep`, `find`, `sed`, and `awk`. |

---

## 🚀 Quick Start

### Prerequisites

Watchdog is designed for maximum portability and has no external dependencies beyond standard Unix utilities.

*   **Shell:** `Bash` v4.0+
*   **Utilities:** `grep`, `find`, `sed`, `awk` (pre-installed on virtually all Linux, macOS, and WSL systems).

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/Hemaksh69/Watchdog_Security_Guardian.git

# 2. Navigate into the directory
cd Watchdog_Security_Guardian

# 3. Make the script executable
chmod +x watchdog.sh
