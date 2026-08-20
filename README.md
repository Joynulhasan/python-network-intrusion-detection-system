# 🛡️ Python Network Intrusion Detection System (NIDS)

A real-time Network Intrusion Detection System built with Python and Scapy. It captures and analyzes raw network traffic to detect port scanning attempts and malicious payload signatures, sending real-time email security alerts via SMTP.

## 🚀 Features

🔍 Live Packet Sniffing: Inspects IP, TCP, UDP, and Raw application layers in real time.

🚨 Port Scan Detection: Tracks unique destination ports accessed per source IP and triggers an alert when exceeding defined thresholds.

🧬 Payload Signature Matching: Detects malicious execution keywords (e.g., cmd.exe, /bin/sh, etc/passwd, SQL injection strings).

📧 Automated Email Alerts: Sends structured incident reports via Gmail/SMTP directly to your inbox.

📝 Timestamped security alerts

🛑 Safe shutdown using `Ctrl+C`

## 🛠️ Technologies

* Python
* Scapy
* SMTP
* TCP/IP
* Network Security
* Intrusion Detection

## 📂 Project Structure

```text
python-network-intrusion-detection-system/
│
├── README.md
├── nids.py
├── requirements.txt
├── .gitignore
│
├── screenshots/
│   ├── nids-running.png
│   ├── port-scan-alert.png
│   ├── payload-alert.png
│   └── email-alert.png

```

## ⚙️ Installation

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/python-network-intrusion-detection-system.git
```

Enter the project directory:

```bash
cd python-network-intrusion-detection-system
```

Create a virtual environment:

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

## 📧 Gmail Configuration

For email alerts, use a Gmail **App Password** instead of your normal Gmail password.

Configure the following values through environment variables:

```text
SMTP_SERVER=smtp.gmail.com
SMTP_PORT=587
SENDER_EMAIL=your_email@gmail.com
SENDER_PASSWORD=your_app_password
RECEIVER_EMAIL=receiver_email@gmail.com
```

⚠️ **Never upload your Gmail password or App Password to GitHub.**

## ▶️ Running the NIDS

Run:

```bash
python nids.py
```

On Linux/Kali, packet sniffing may require elevated privileges:

```bash
sudo python3 nids.py
```

You should see:

```text
============================================================
🚀 Initializing Python Network Intrusion Detection System...
============================================================
[*] Sniffing network traffic...
Press Ctrl+C to stop.
```

## 🚨 Port Scan Detection

The system tracks destination ports contacted by each source IP.

If an IP scans more than **20 unique ports**, the system generates an alert.

Example:

```text
[🚨 ALARM] Potential Port Scan Detected!

Source IP: 192.168.1.10
Unique Ports Scanned: 21
Protocol: TCP
Time: 2026-08-20 16:20:35
```

An email alert is then sent to the configured receiver.

## 🕵️ Suspicious Payload Detection

The system checks packet payloads for predefined suspicious signatures such as:

```text
etc/passwd
cmd.exe
/bin/sh
union select
' OR '1'='1
```

Example:

```text
[🚨 ALARM] Suspicious Payload Detected!

Source IP: 192.168.1.10
Destination IP: 192.168.1.20
Protocol: TCP
Time: 2026-08-20 16:22:10
Matched Signature: /bin/sh
```

## 📧 Email Alert

When suspicious activity is detected, the system sends an email containing:

* Alert type
* Source IP
* Destination IP
* Protocol
* Detection time
* Matched signature / number of scanned ports

## 📸 Screenshots

Add screenshots of:

1. NIDS running
2. Port scan detection
3. Suspicious payload detection
4. Email notification

Place them inside the `screenshots/` directory.

Example:

```markdown
![NIDS Running](screenshots/nids-running.png)
```

## 🎯 Learning Objectives

This project demonstrates practical knowledge of:

* Packet analysis
* Network monitoring
* TCP/IP protocols
* Port scanning detection
* Signature-based intrusion detection
* Python network programming
* Security alerting
* SMTP email integration

## 🔮 Future Improvements

Possible future improvements:

* Add IP reputation checking
* Add DNS monitoring
* Add HTTP/HTTPS traffic analysis
* Add UDP scan detection improvements
* Add configurable thresholds
* Store alerts in SQLite
* Create a web dashboard
* Add SIEM integration
* Add Telegram/Discord notifications
* Add logging to JSON/CSV
* Implement time-window based port scan detection

## ⚠️ Disclaimer

This project is intended for **educational and authorized security monitoring purposes only**.

Only monitor networks and systems that you own or have explicit permission to monitor.

## 👨‍💻 Author

**Joynul Hasan**

Cybersecurity / SOC Student

Skills demonstrated:

`Python` `Scapy` `Network Security` `Packet Analysis` `NIDS` `SOC`
