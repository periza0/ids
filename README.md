# Network Intrusion Detection System (IDS)

A lightweight Python-based Network Intrusion Detection System that monitors live network traffic, detects suspicious activities such as port scans and SYN flood attempts, and generates real-time alerts for potential security threats.

## Features

* Real-time packet capture using Scapy
* Detection of TCP SYN scan and port scan activity
* Configurable detection thresholds
* Live console alerts for suspicious hosts
* Lightweight and easy to deploy
* Modular architecture for adding new detection rules

---

## Tech Stack

* Python 3
* Scapy
* Nmap (for testing)
* macOS/Linux

---

## Project Structure

```text
ids/
├── ids.py              # Main IDS script
├── detector.py         # Detection logic
├── utils.py            # Helper functions
├── requirements.txt
└── README.md
```

---

## Installation

Clone the repository:

```bash
git clone <repository-url>
cd ids
```

Install the required dependencies:

```bash
pip install -r requirements.txt
```

Install Nmap (used for testing):

### macOS

```bash
brew install nmap
```

### Ubuntu

```bash
sudo apt install nmap
```

---

## Usage

Run the IDS:

```bash
sudo python ids.py
```

Example output:

```text
[*] Starting IDS on interface: en0
[!] NMAP-STYLE SCAN DETECTED from 172.16.147.9 (SYNs=31)
```

---

## Detection Logic

The IDS continuously monitors incoming packets and:

* Tracks TCP SYN packets from each source IP
* Counts connection attempts within a time window
* Flags excessive SYN requests as potential reconnaissance or port scans
* Generates real-time alerts without interrupting network traffic

---

## Testing

Generate scan traffic using Nmap:

```bash
nmap -sS <target-ip>
```

The IDS should detect the scan and produce an alert similar to:

```text
[!] NMAP-STYLE SCAN DETECTED from <source-ip>
```

---

## Future Improvements

* Web dashboard for monitoring alerts
* Email and Telegram notifications
* Signature-based attack detection
* Machine learning–based anomaly detection
* Packet logging and visualization

---

## Resume Summary

Developed a Python-based Network Intrusion Detection System (IDS) using Scapy to monitor live network traffic and detect TCP SYN/port scan attacks in real time through packet inspection, threshold-based detection, and automated alert generation.
