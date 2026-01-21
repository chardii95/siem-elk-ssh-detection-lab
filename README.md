# SIEM Lab – SSH Brute Force Detection using ELK Stack

## Overview
This project demonstrates the deployment and use of an ELK Stack (Elasticsearch, Kibana, Filebeat) SIEM environment to ingest, analyze, and detect suspicious SSH authentication activity on a Linux system.

The lab simulates real-world Tier 1–2 SOC workflows including log ingestion, threat detection logic, and investigation using Kibana.

---

## Objectives
- Deploy ELK Stack using Docker
- Ingest Linux authentication logs using Filebeat
- Simulate SSH brute-force activity
- Detect failed authentication attempts using KQL
- Investigate security events in Kibana Discover
- Build custom detection rules

---

## Environment
- Host OS: macOS (Apple Silicon – M1)
- SIEM Stack: Elasticsearch 8.11, Kibana 8.11
- Log Shipper: Filebeat
- Target System: Ubuntu 24.04 LTS
- Virtualization: UTM
- Containerization: Docker Compose

---

## Architecture
- Filebeat collects `/var/log/auth.log` from Ubuntu
- Logs are forwarded to Elasticsearch
- Kibana is used for:
  - Log discovery
  - Timeline analysis
  - Detection rule creation

---

## Attack Simulation
Simulated SSH brute-force activity by repeatedly attempting login with invalid credentials:

```bash
ssh wronguser@<target-ip>
