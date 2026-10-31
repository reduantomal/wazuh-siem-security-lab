
flowchart TB
    subgraph SERVER["CENTRAL MONITORING SERVER"]
        K["Kali Linux"]
        M["Wazuh Manager"]
        I["Wazuh Indexer"]
        D["Wazuh Dashboard"]
        K --> M
        K --> I
        K --> D
    end

    subgraph ENDPOINTS["MONITORED ENDPOINTS"]
        W["Windows Endpoint(s)<br/>Wazuh Agent"]
        L["Linux Endpoint(s)<br/>Wazuh Agent"]
    end

    W -->|"Agent event data"| M
    L -->|"Agent event data"| M
    M --> I
    I --> D



# Lab Architecture

## Overview

This project uses Kali Linux as the central host
for an all-in-one Wazuh deployment.

The environment monitors multiple Windows and
Linux endpoints through Wazuh agents.

## Components

- Kali Linux: Central monitoring host
- Wazuh Manager: Processes endpoint data
- Wazuh Indexer: Stores and indexes security data
- Wazuh Dashboard: Web-based monitoring interface
- Windows Agents: Windows endpoint monitoring
- Linux Agents: Linux endpoint monitoring

## Monitoring Capabilities

- Centralized log monitoring
- Security alert investigation
- Custom detection rules
- File Integrity Monitoring (FIM)
- Vulnerability detection

## Deployment Type

Single-host Wazuh all-in-one deployment
with multiple monitored endpoints.
