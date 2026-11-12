# SOC Investigation Report 001

## Investigation of Windows Authentication Failures

**Environment:** Windows 11 Pro — Oracle VirtualBox  
**Investigation Type:** Authentication Failure Analysis  
**Account Investigated:** Caius  
**Event ID:** 4625  
**Date of Events:** 23 September 2026  
**Classification:** Historical Authentication Activity  
**Severity:** Informational  
**Status:** Investigation Completed — Limited Evidence

---

## 1. Executive Summary

An investigation was conducted into failed Windows authentication events recorded within a Windows 11 Pro virtual machine.

Using Windows Event Viewer, two Event ID 4625 records were identified involving the same local Windows account.

The events occurred at 11:27:54 and 11:45:07 on 23 September 2026, approximately 17 minutes and 13 seconds apart.

Analysis of the second event identified an interactive authentication failure associated with an incorrect password.

The available evidence did not establish malicious activity.

## 2. Investigation Objectives

- Identify Windows authentication failures.
- Determine the account involved.
- Analyse relevant Windows Security event metadata.
- Compare event timestamps.
- Assess whether the authentication pattern suggested potentially malicious behaviour.
- Document findings and security recommendations.

## 3. Lab Environment

| Component | Configuration |
|---|---|
| Operating System | Windows 11 Pro |
| Virtualisation | Oracle VirtualBox |
| Monitoring Tool | Windows Event Viewer |
| Event Log | Windows Logs → Security |
| Event ID | 4625 |
| Account | Caius |

## 4. Evidence Timeline

| Time | Event ID | Account | Result |
|---|---|---|---|
| 11:27:54 | 4625 | Caius | Authentication failed |
| 11:45:07 | 4625 | Caius | Authentication failed |

**Time between recorded failures:** 17 minutes and 13 seconds.

The two records were the only Event ID 4625 results visible in the filtered Security log at the time of review. This does not establish that no other authentication activity occurred.

## 5. Technical Analysis

### Event ID 4625

Event ID 4625 is generated when Windows records a failed account logon.

The second event contained the following information:

- **Logon Type:** 2 — Interactive
- **Failure Reason:** Unknown user name or bad password
- **Status:** 0xC000006D
- **Sub Status:** 0xC000006A
- **Account:** Caius

The status code indicates an authentication failure, while the substatus code indicates an incorrect password.

The event's process information referenced a Microsoft Edge WebView2 component.

This may indicate application-related authentication activity, but the precise cause cannot be determined from the available evidence.

The first event was confirmed as a failed authentication involving the same account. Its detailed status codes, logon type and process information were not verified.

## 6. Threat Assessment

Repeated failed authentication attempts can be associated with:

- Incorrect user credentials.
- Outdated stored passwords.
- Application authentication errors.
- Password-guessing attempts.

In this investigation, only two failures were identified, separated by approximately 17 minutes.

There was insufficient evidence of a sustained password-guessing attack, credential compromise or unauthorised access.

**Assessment:** Suspicious activity not established.

## 7. Recommendations

1. Continue monitoring Windows Security Event ID 4625.
2. Investigate significant increases in failed authentication frequency.
3. Correlate account names, logon types, timestamps and source information.
4. Review applications that repeatedly attempt authentication with invalid credentials.
5. Implement appropriate authentication controls, including multifactor authentication where supported.
6. Establish alerting thresholds appropriate to the environment.

## 8. Investigation Conclusion

The investigation successfully identified and correlated two Windows authentication failures involving the same account.

The available evidence supported an incorrect-password finding for the second event.

No malicious activity was established.

**Final Disposition:** Inconclusive cause — no confirmed security incident.

## 9. Skills Demonstrated

- Windows Security Event Log Analysis
- Event ID 4625 Investigation
- Authentication Failure Analysis
- Windows Event Viewer
- Event Timeline Reconstruction
- Security Event Correlation
- Threat Assessment
- Technical Incident Documentation

## 10. Evidence Limitations

This investigation was conducted retrospectively using historical events recorded within a virtual machine.

The first event's detailed metadata was not fully examined, and the available records did not establish the root cause of the authentication failures.

Further investigation would require additional log correlation and application context.
