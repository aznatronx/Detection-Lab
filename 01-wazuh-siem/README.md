# 01 – Wazuh SIEM

This section documents the Wazuh deployment behind the rest of the lab: how it is built, how agents connect to it, and how its alerts are used.

## What is Wazuh

Wazuh is a free, open-source security platform. It works as a SIEM: it collects logs from many machines, correlates them and raises alerts. On top of that it adds endpoint protection features. In simple terms, it is a security guard that reads the "diaries" (logs) of every monitored machine and warns you when something looks wrong.

## What it does

- **Log analysis** – reads system and application logs and matches them against detection rules to spot suspicious behaviour, such as repeated failed logins.
- **File integrity monitoring (FIM)** – raises an alert when important files are changed.
- **Vulnerability detection** – compares installed software with known vulnerabilities (CVEs).
- **Security configuration assessment (SCA)** – checks systems against hardening benchmarks.
- **Active response** – can run an automatic action, for example blocking an IP address, when a rule fires.

## Components

| Component | Role |
|---|---|
| Agent | Small program installed on every monitored machine. Collects logs and events and sends them to the server. |
| Manager (server) | Receives data from agents, decodes it, applies detection rules and generates alerts. |
| Indexer | Stores and indexes alerts so they can be searched quickly. |
| Dashboard | Web interface for searching alerts, viewing agents and building visualizations. |

## This lab at a glance

| Item | Value |
|---|---|
| Wazuh version | 4.14.8 |
| Deployment | Single node: manager, indexer and dashboard on one Ubuntu 22.04 server |
| Connected agents | Kali Linux (more endpoints are added as the lab grows) |
| Server access | SSH with keys only, remote access over a VPN |

## Contents

- [Architecture](01-architecture.md)
- [Server setup and health checks](02-server-setup.md)
- [Connecting agents](03-agents.md)
- Monitoring and alerts – coming next
