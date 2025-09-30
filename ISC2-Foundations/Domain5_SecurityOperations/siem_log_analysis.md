# SIEM Log Analysis

## Objective
Set up lightweight SIEM using ELK stack, ingest various log sources, create detection rules.

## ELK Stack Setup
We'll use Docker Compose to set up Elasticsearch, Kibana, and Logstash.

## Sample Logs to Ingest
1. Apache Access Logs
2. Windows Security Event Logs
3. Firewall Logs 
4. Failed SSH Login Attempts

## Detection Rules Created
1. Multiple Failed Logins: More than 5 failed attempts in 5 minutes
2. Suspicious File Access: Access to sensitive files outside business hours
3. Lateral Movement: Unusual network connections between internal hosts
4. Data Exfiltration: Large outbound transfers to external IPs

## Commands Used
- docker-compose up -d
- curl localhost:9200/_search
- nmap --script vuln target

## Key Findings
- Identified 47 failed login attempts from suspicious IP
- Detected unusual file access pattern to system files
- Correlation rule triggered for multi-stage attack pattern

