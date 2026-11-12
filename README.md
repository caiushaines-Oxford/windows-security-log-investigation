
# Windows Security Log Investigation — SOC Analyst Home Lab

## Project Overview

This project documents a practical security investigation conducted in a Windows 11 Pro virtual machine using Oracle VirtualBox.

The objective was to investigate Windows authentication activity, identify failed and successful login attempts, and understand how a Security Operations Centre (SOC) Analyst can correlate Windows Security events.

## Lab Environment

- **Operating System:** Windows 11 Pro
- **Virtualisation:** Oracle VirtualBox
- **Monitoring Tool:** Windows Event Viewer
- **Audit Configuration:** Success and Failure auditing enabled for Logon events
- **Test Account:** SOC-TestUser
- **Investigation Type:** Windows Authentication Event Analysis

## Investigation Scenario

A controlled series of incorrect password attempts was performed against a dedicated Windows test account, followed by a successful authentication.

The investigation focused on identifying and interpreting:

| Event ID | Description |
|---|---|
| 4625 | Failed account logon |
| 4624 | Successful account logon |

This sequence was used to simulate an authentication pattern that could warrant investigation in a production environment.

## Methodology

1. Configured Windows security auditing.
2. Created a dedicated standard-user test account.
3. Generated controlled authentication failures using the Windows `runas` command.
4. Successfully authenticated using the correct credentials.
5. Filtered Windows Security logs in Event Viewer.
6. Identified Event IDs 4625 and 4624 associated with the test account.
7. Examined authentication activity and prepared an investigation report.

## Findings

- Failed authentication activity was successfully recorded as Event ID 4625.
- A subsequent successful authentication was recorded as Event ID 4624.
- Both event types were identified for the dedicated test account.
- The activity was part of an authorised lab simulation, not a confirmed malicious attack.

Exact timestamps, event counts and additional metadata will be documented in the incident report after verification.

## Security Considerations

In a real SOC environment, repeated authentication failures followed by a successful login may justify further investigation.

Analysts should correlate account names, timestamps, logon types, source information and relevant environmental context before drawing conclusions.

## Skills Demonstrated

- Windows Security Event Log Analysis
- Authentication Monitoring
- Windows Audit Policy Configuration
- Security Event Correlation
- Basic Threat Investigation
- Incident Reporting

## Investigation Evidence

Supporting screenshots and the completed incident report will be added after verification and redaction.

## Conclusion

This project demonstrates foundational SOC Analyst investigation skills through a controlled Windows authentication exercise.

**Final classification:** Authorised lab activity — no malicious behaviour established.
