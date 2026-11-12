# Windows Failed Logon Investigation — SOC Analyst Portfolio

## Overview

A practical cybersecurity investigation examining failed Windows authentication events in a Windows 11 Pro virtual machine.

The project demonstrates how a SOC Analyst can use Windows Event Viewer to identify authentication failures, analyse event metadata, correlate timestamps and assess potential security threats.

## Technologies

- Windows 11 Pro
- Oracle VirtualBox
- Windows Event Viewer
- Windows Security Logs
- Event ID 4625

## Investigation Summary

Two failed authentication events involving the same Windows account were identified on 23 September 2026.

The events occurred 17 minutes and 13 seconds apart.

Analysis of the second event revealed an incorrect-password authentication failure with Logon Type 2.

The investigation found insufficient evidence to establish malicious activity.

## Key Findings

- Two Event ID 4625 records identified.
- Both events involved the same account.
- Incorrect password confirmed for the second event.
- Event timestamps correlated.
- No confirmed security incident established.

## Documentation

See [SOC Investigation Report](incident-report.md) for the full investigation, evidence analysis, findings and security recommendations.

## Skills Demonstrated

Windows Event Log Analysis | Authentication Monitoring | Event Correlation | Threat Assessment | Incident Documentation

## Disclaimer

This project was conducted in a personal Windows 11 Pro virtual lab for cybersecurity education and portfolio development. The analysed events were historical records; their original cause was not established.
