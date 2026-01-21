# Detection – SSH Brute Force Attempt

## Objective
Detect repeated failed SSH authentication attempts indicative of brute-force activity.

---

## Data Source
- Linux authentication logs (`/var/log/auth.log`)
- Ingested via Filebeat into Elasticsearch

---

## Detection Logic
```kql
message : "Failed password"
