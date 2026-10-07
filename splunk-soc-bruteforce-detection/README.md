# Splunk SOC Lab — Brute-Force Detection & Investigation

## 📌 Overview

This project is a small Security Operations Center (SOC) lab built with Splunk to practice security monitoring, detection, and investigation.

The lab simulates a scenario involving repeated failed login attempts from a single source IP, followed by a successful authentication.

The objective is to demonstrate how Splunk can be used to identify suspicious authentication activity and support a basic SOC investigation workflow.

---

## 🎯 Objectives

- Ingest authentication logs into Splunk
- Search and analyze security events using SPL
- Identify repeated failed login attempts
- Detect potentially suspicious authentication behavior
- Investigate the source IP and targeted user
- Analyze the authentication timeline
- Create a dashboard for security monitoring

---

## 🏗️ Lab Architecture

![Splunk SOC Lab Architecture](docs/architecturee.png)

```text
Kali Linux
    │
    │ Simulated authentication events
    ▼
CSV Log File
    │
    ▼
Splunk Enterprise
    │
    ├── Detection
    ├── Investigation
    ├── Timeline Analysis
    └── Dashboard
```

---

## 🛠️ Technologies

- Splunk Enterprise
- SPL (Search Processing Language)
- Kali Linux
- Ubuntu
- CSV
- VirtualBox

---

## 🔍 Detection Scenario

A controlled simulation was created to represent repeated authentication attempts.

The simulated activity contains:

- Multiple failed login attempts
- A single source IP
- A targeted user
- A successful login after the failed attempts

This allows the investigation of behavior potentially associated with a brute-force attack without performing an actual attack.

---

## 🧪 Investigation Workflow

The investigation follows a simple SOC workflow:

### 1. Log ingestion

Authentication events are ingested into Splunk.

### 2. Failed login analysis

Failed authentication events are filtered and analyzed.

### 3. Source IP identification

The number of failed attempts is aggregated by source IP.

### 4. Detection

A threshold is used to identify source IPs generating multiple failed login attempts.

### 5. User investigation

The targeted user associated with the suspicious source is identified.

### 6. Timeline analysis

Authentication events are ordered chronologically to understand the sequence of activity.

### 7. Visualization

A Splunk dashboard is created to provide a visual overview of the authentication activity.

---

## 📊 Dashboard

### Dashboard Preview

![Splunk Dashboard](screenshots/dashboard.png)

The dashboard provides several views of the simulated authentication activity:

- Failed Login Attempts by Source IP
- Login Status
- Targeted Users
- Authentication Activity Timeline

---

## 📸 Investigation Screenshots

### Brute-Force Detection

![Brute-Force Detection](screenshots/detection.png)

### Investigation

![Investigation](screenshots/investigation.png)

### Authentication Timeline

![Authentication Timeline](screenshots/timeline.png)

---

## 🔎 Key Findings

The investigation identified a source IP generating multiple failed authentication attempts against the same user.

The activity was followed by a successful authentication, making the sequence relevant for further investigation in a real SOC environment.

---

## ⚠️ Disclaimer

This project uses simulated authentication data in a controlled laboratory environment.

No real brute-force attack was performed.

The source IP addresses and authentication events are used only for educational and demonstration purposes.

---

## 📚 Skills Demonstrated

- Security monitoring
- Log analysis
- SPL queries
- Authentication event analysis
- Basic threat detection
- SOC investigation methodology
- Security dashboard creation
