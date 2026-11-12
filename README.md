# Windows Failed Logon Analysis — SOC Analyst Home Lab

## Project Overview

This project demonstrates a practical Windows security investigation conducted in a Windows 11 Pro virtual machine using Oracle VirtualBox.

The objective was to generate and analyse failed authentication attempts using Windows Event Viewer, demonstrating foundational Security Operations Centre (SOC) monitoring and investigation techniques.

## Lab Environment

| Component | Technology |
|---|---|
| Operating System | Windows 11 Pro |
| Virtualisation | Oracle VirtualBox |
| Log Analysis | Windows Event Viewer |
| Audit Policy | Logon Success and Failure enabled |
| Test Account | SOC-TestUser |
| Security Event | Windows Event ID 4625 |

## Investigation Scenario

A dedicated Windows test account was created to simulate repeated unsuccessful authentication attempts.

Incorrect passwords were deliberately submitted using the Windows `runas` command.

The resulting Windows Security events were examined to understand how failed authentication activity can be detected and investigated.

## Investigation Methodology

1. Configured Windows Advanced Audit Policy to record authentication events.
2. Created a dedicated standard-user test account.
3. Generated controlled failed authentication attempts using incorrect credentials.
4. Opened Windows Event Viewer and filtered the Security log for Event ID 4625.
5. Identified failed authentication events.
6. Examined the affected account and available event metadata.
7. Assessed the security significance of repeated failed logons.

## Security Event Analysis

### Event ID 4625 — An Account Failed to Log On

Event ID 4625 is generated when Windows records a failed logon attempt.

Important fields include:

- **Account Name:** Identifies the account involved.
- **Logon Type:** Indicates the authentication method.
- **Failure Reason:** Explains why authentication failed.
- **Status and Sub Status:** Provide technical details about the failure.
- **Time Created:** Establishes when the attempt occurred.
- **Source Network Address:** Identifies the network source when available.

## Findings

Windows Security Event ID 4625 was successfully generated and identified within the virtual machine.

The exercise demonstrated how Windows Security auditing can provide evidence of unsuccessful authentication attempts.

Repeated failures can be associated with password-guessing activity, although they are not sufficient by themselves to establish malicious intent.

In this investigation, the activity was generated intentionally in an authorised lab environment.

## Conclusion

The investigation successfully demonstrated foundational Windows authentication monitoring and security event analysis.

**Final Classification:** Benign — Authorised Security Testing.

## Skills Demonstrated

- Windows Event Log Analysis
- Security Auditing
- Failed Authentication Investigation
- Security Event Filtering
- Basic Threat Detection
- SOC Incident Documentation
