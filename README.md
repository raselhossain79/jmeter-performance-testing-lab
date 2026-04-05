<div align="center">

<img src="https://img.shields.io/badge/Apache%20JMeter-D22128?style=for-the-badge&logo=apache&logoColor=white" />
<img src="https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white" />
<img src="https://img.shields.io/badge/Kali_Linux-557C94?style=for-the-badge&logo=kalilinux&logoColor=white" />
<img src="https://img.shields.io/badge/Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white" />

<br/>

# 🚀 Apache JMeter — Performance Testing Lab

### Simulate real-world traffic. Measure server limits. Learn load testing from scratch.

<img src="https://img.shields.io/badge/Status-Educational%20Project-blue?style=flat-square" />
<img src="https://img.shields.io/badge/Level-Beginner%20Friendly-green?style=flat-square" />
<img src="https://img.shields.io/badge/License-MIT-yellow?style=flat-square" />

</div>

---

## 📌 Overview

This project demonstrates how to perform **basic performance and load testing** on a web application using **Apache JMeter** — one of the most widely used open-source tools in the industry for testing server behavior under high traffic.

By following this lab, you will simulate multiple concurrent users making requests to a target server and analyze:

| Metric | Description |
|---|---|
| ⏱️ Response Time | How fast the server processes and returns a response |
| 📈 Throughput | Number of requests handled per second |
| ❌ Error Rate | Percentage of failed or timed-out requests |

> ⚠️ **This project is strictly for educational purposes.**
> Only test on systems you own or have **explicit written permission** to test.

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| 🔴 Apache JMeter | Load & performance testing engine |
| ☕ Java (JDK/JRE) | Required runtime for JMeter |
| 🐉 Kali Linux | Primary testing OS |
| 🪟 Windows | Alternative OS support |
| 🌐 testphp.vulnweb.com | Legal practice target (Acunetix sandbox) |

---

## ⚙️ Installation Guide

### 🐉 On Kali Linux

```bash
# Step 1 — Update system packages
sudo apt update && sudo apt upgrade -y

# Step 2 — Check if Java is installed
java -version

# Step 3 — Install Java if not present
sudo apt install default-jre -y

# Step 4 — Install Apache JMeter
sudo apt install jmeter -y

# Step 5 — Launch JMeter GUI
jmeter
```

---

### 🪟 On Windows

**1. Install Java (JDK)**
- Download from: [https://www.oracle.com/java/technologies/downloads/](https://www.oracle.com/java/technologies/downloads/)
- After installation, verify:

```cmd
java -version
```

**2. Install Apache JMeter**
- Download ZIP from: [https://jmeter.apache.org/download_jmeter.cgi](https://jmeter.apache.org/download_jmeter.cgi)
- Extract the ZIP file
- Navigate to the `bin/` folder
- Run:

```
bin\jmeter.bat
```

---

## 🧪 Basic Test Setup (Step-by-Step)

### Step 1 — Create a Test Plan

Open JMeter → Right-click **Test Plan** → Add → Threads → **Thread Group**

| Setting | Value |
|---|---|
| Number of Threads (Users) | `50` |
| Ramp-Up Period | `10` seconds |
| Loop Count | `1` |

> 📝 Ramp-up = JMeter will gradually start all 50 users over 10 seconds (5 users/sec)

---

### Step 2 — Add HTTP Request Sampler

Right-click Thread Group → Add → Sampler → **HTTP Request**

| Field | Value |
|---|---|
| Protocol | `http` |
| Server Name / IP | `testphp.vulnweb.com` |
| HTTP Method | `GET` |
| Path | `/` |

---

### Step 3 — Add Listeners (Result Viewers)

Right-click Thread Group → Add → Listener:

- ✅ **View Results Tree** — See individual request/response details
- ✅ **Summary Report** — See aggregated stats (avg time, throughput, errors)
- ✅ **Aggregate Report** *(optional)* — More detailed percentile breakdown

---

### Step 4 — Run the Test

Click the green **▶️ Start** button in the toolbar.

Watch results populate in real-time in your listeners.

---

## 📊 Results Analysis

After running your test, analyze the following metrics:

```
┌─────────────────────────────────────────────────────────┐
│                   KEY METRICS TO WATCH                  │
├──────────────────┬──────────────────────────────────────┤
│ Avg Response Time│ Should be < 2000ms for good UX       │
│ 90th Percentile  │ 90% of users got response within X ms│
│ Throughput       │ Higher = server handles more traffic  │
│ Error %          │ Should be close to 0% ideally        │
│ Min / Max        │ Identify best-case vs worst-case      │
└──────────────────┴──────────────────────────────────────┘
```

**What to look for:**
- 🟢 Low response time + low error rate = Healthy server
- 🟡 Increasing response time as users grow = Potential bottleneck
- 🔴 High error % = Server is struggling under load

---

## 🗂️ Project Structure

```
jmeter-performance-lab/
│
├── test-plans/
│   └── basic_load_test.jmx        # JMeter test plan file
│
├── results/
│   ├── summary_report.csv         # Exported summary data
│   └── results_tree.xml           # Full results log
│
├── screenshots/
│   ├── thread_group_config.png
│   ├── http_request_config.png
│   └── summary_report_output.png
│
└── README.md
```

---

## 🎯 Learning Outcomes

After completing this lab, you will be able to:

- [x] Understand the fundamentals of **load testing** and **performance testing**
- [x] Configure **Thread Groups** to simulate concurrent users
- [x] Set up **HTTP Request samplers** in JMeter
- [x] Read and interpret **Summary Reports** and **Results Trees**
- [x] Identify performance bottlenecks in web servers
- [x] Understand the difference between **load testing**, **stress testing**, and **spike testing**

---

## 🔮 Future Improvements

- [ ] 🔌 **API Testing** — Test REST APIs with POST/PUT/DELETE requests
- [ ] 🔗 **Burp Suite Integration** — Combine with proxy interception for deeper analysis
- [ ] 🤖 **Automated Test Scripts** — Run JMeter in CLI (non-GUI) mode with `.jmx` files
- [ ] 📉 **Grafana + InfluxDB Dashboard** — Real-time visual metrics during tests
- [ ] ☁️ **Cloud-Based Load Testing** — Simulate thousands of users using distributed JMeter
- [ ] 🔐 **Authenticated Endpoints** — Test login-protected pages using session handling

---

## ⚠️ Legal Disclaimer

> This project is created **for educational and ethical security research purposes only.**

**DO NOT** use this tool against:
- 🏛️ Government or military websites
- 🏦 Banking or financial systems
- 🔒 Any private or corporate systems
- 🌐 Any website **without explicit written permission**

Unauthorized load testing can be considered a **Denial of Service (DoS) attack** and is **illegal** under cybercrime laws in most countries.

**Always test on:**
- ✅ Your own local servers
- ✅ Legal sandboxes (e.g., `testphp.vulnweb.com`, `DVWA`, local VMs)
- ✅ Systems where you have written authorization

---

## 👤 Author

<div align="center">

**Rasel Hossain**
Cybersecurity Enthusiast | Penetration Tester

[![GitHub](https://img.shields.io/badge/GitHub-raselhossain79-181717?style=for-the-badge&logo=github)](https://github.com/raselhossain79)
[![TryHackMe](https://img.shields.io/badge/TryHackMe-theloser-212C42?style=for-the-badge&logo=tryhackme)](https://tryhackme.com/p/theloser)

</div>

---

<div align="center">

**⭐ If this lab helped you learn something new, consider starring the repo!**

</div>
