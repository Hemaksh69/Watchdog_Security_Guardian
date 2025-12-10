🐺 WatchDog – Secret Guardian

A lightweight Bash-based Secret Scanner that detects hardcoded credentials inside your code using regex-powered scanning.

🔍 Features

Detects AWS Access Keys (AKIA / ASIA)

Detects Google API Keys

Detects hardcoded passwords & tokens

Detects private keys

Detects Base64 encoded strings

Detects exposed email addresses

Shows threat count & risk level

Gives security recommendations

Sends a mock alert message

🛠 How It Works

WatchDog scans your code using pattern-based detection:

scan "AKIA[0-9A-Z]{16}" "AWS Access Key"
scan "ASIA[0-9A-Z]{16}" "AWS Temp Key"
scan "password\s*=\s*['\"].+" "Hardcoded Password"
scan "token\s*=\s*['\"].+" "Hardcoded Token"
scan "[A-Za-z0-9+/]{20,}={0,2}" "Base64 String"
scan "[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[A-Za-z]{2,}" "Email Address"

🚀 Usage

Clone the repository

git clone https://github.com/yourusername/watchdog.git


Make script executable

chmod +x watchdog.sh


Run the scanner

./watchdog.sh

📂 Script Overview
echo "----------- Welcome To WatchDog Your Secret Guardian -----------"
sleep 2

USER_CODE='
const password="admin123"
AWS_KEY="AKIA1234567890ABCD"
email="test@example.com"
'
...
scan "AKIA[0-9A-Z]{16}" "AWS Access Key"
...

🖼 Sample Output
SECRET DETECTED: AWS Access Key
SECRET DETECTED: Hardcoded Password
SECRET DETECTED: Email Address

Total Secrets Found: 3
⚠️ RISK LEVEL: HIGH – ALERT TRIGGERED

💡 Why I Built It

To understand how real-world secret scanners like Gitleaks & TruffleHog work

To practice Bash scripting & DevSecOps concepts

To detect accidental credential leaks during development

🚧 Future Improvements

Scan entire project directories

Auto-remove leaked secrets

Generate a JSON/HTML report

Integrate with GitHub pre-commit hooks

Support multi-language scanning

📜 License

This project is open-source under the MIT License.
