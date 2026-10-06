# SOC + IT Helpdesk Ticketing Lab

## Project Overview

This project demonstrates a hands-on SOC L1 incident workflow using **Wazuh** for security monitoring and **GLPI** for IT service management and ticket tracking.

The lab simulates investigation of repeated Windows authentication failures (Event ID **4625**) involving a test Active Directory account.

### Architecture

```text
Windows Endpoint / Active Directory
              |
              v
           Wazuh
              |
              v
      Threat Hunting / Logs
              |
              v
       SOC L1 Investigation
              |
              v
            GLPI
        Incident Ticket
              |
              v
 Evidence -> Assessment -> Resolution
```

## Scenario

A Windows authentication failure alert was investigated after repeated Event ID 4625 events were observed.

The investigation identified:

- 5 relevant failed-authentication alerts in the investigation window.
- Events from both a Windows endpoint and the lab Domain Controller.
- The Domain Controller events targeted the lab `testuser` account.
- The activity was treated as **suspicious repeated authentication failures**.
- Brute-force/password-spraying was **not confirmed** because the available evidence was insufficient to prove malicious intent.
- No successful authentication following the failures was identified during the documented investigation.

This demonstrates an important SOC L1 principle: **validate the evidence before escalating an alert as an attack.**

## Tools

- Wazuh SIEM / XDR
- Windows Security Event Logs
- Active Directory lab
- GLPI ITSM / ticketing
- Linux / Ubuntu WSL
- Apache
- MariaDB
- PHP

## Ticket Workflow

1. Alert received
2. Initial triage
3. Identify Event ID 4625
4. Correlate authentication events
5. Validate target account
6. Assess severity and priority
7. Document evidence in GLPI
8. Record analyst assessment
9. Record resolution
10. Solve the ticket

## Key SOC Skills Demonstrated

- Windows authentication event analysis
- Event ID 4625 investigation
- SIEM threat hunting
- Basic event correlation
- False-positive / insufficient-evidence reasoning
- Incident prioritization
- Ticket assignment and ownership
- Investigation documentation
- SOC L1 incident lifecycle
- ITSM workflow

## Evidence

Screenshots are provided in chronological investigation order under `screenshots/`.

> **Privacy note:** IP addresses, hostnames, domain/user identifiers, and similar lab identifiers have been blurred for public portfolio use.

## Suggested Resume Bullet

> Built a hands-on SOC/ITSM lab integrating Wazuh with GLPI to investigate Windows authentication failures, correlate Event ID 4625 activity across endpoints, document evidence, assess incident severity, and manage the incident through an L1 ticket lifecycle.

## Disclaimer

This is a controlled home-lab project using simulated/test activity. No production systems were investigated.
