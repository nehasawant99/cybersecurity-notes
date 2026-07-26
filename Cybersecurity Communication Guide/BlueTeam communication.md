# Cybersecurity Communication Guide
### Blue Team | SOC Analyst | Incident Response

These notes cover the communication style, terminology, and reporting practices commonly used by SOC analysts in professional environments.

---

# Communication Principles

- Be factual, not emotional.
- Report only what evidence supports.
- Avoid assumptions.
- Keep reports clear and concise.
- Use professional terminology.
- Separate observations from conclusions.
- If evidence is insufficient, state that further investigation is required.

---

# Professional Investigation Verbs

Use these words while documenting investigations.

- Observed
- Identified
- Detected
- Investigated
- Reviewed
- Analyzed
- Correlated
- Verified
- Collected
- Confirmed
- Validated
- Monitored
- Escalated
- Isolated
- Contained
- Blocked
- Remediated
- Documented

---

# Words to Avoid

Avoid absolute statements unless evidence confirms them.

❌ Hacked

❌ Definitely malicious

❌ Virus entered

❌ Clearly compromised

❌ 100% attack

❌ Someone attacked the system

❌ User is the attacker

Use evidence-based language instead.

---

# Better Professional Wording

Instead of

> Someone hacked the computer.

Use

> Suspicious activity was observed on the endpoint.

---

Instead of

> Malware infected the device.

Use

> Suspicious process execution was identified.

---

Instead of

> User account hacked.

Use

> Multiple failed authentication attempts were observed.

---

Instead of

> PowerShell attack.

Use

> PowerShell execution was observed and requires further analysis.

---

Instead of

> This is malicious.

Use

> Additional evidence is required before confirming malicious activity.

---

# Common Investigation Statements

- Multiple failed logon attempts were observed.
- Successful authentication followed repeated failed logins.
- PowerShell execution was detected.
- A new local user account was created.
- Windows Defender generated a security alert.
- Remote authentication activity was identified.
- Suspicious process creation was observed.
- Evidence suggests abnormal activity.
- Activity deviates from the normal baseline.
- Further investigation is recommended.
- No evidence currently confirms malicious activity.

---

# Common Blue Team Vocabulary

## Authentication

- Logon
- Logoff
- Authentication
- Authorization
- Credentials
- Account Lockout
- Privilege
- MFA
- Session

---

## Endpoint

- Endpoint
- Host
- Asset
- Process
- Parent Process
- Child Process
- Service
- Registry
- Scheduled Task
- Command Line
- File Path

---

## Network

- Source IP
- Destination IP
- Internal IP
- External IP
- Port
- Protocol
- DNS
- Connection
- Traffic

---

## Threat Detection

- IOC
- IOA
- Detection
- Correlation
- Alert
- Investigation
- Threat Hunting
- Triage
- Containment
- Remediation
- Recovery

---

# Common SIEM Terms

- Alert
- Event
- Log Source
- Data Source
- Dashboard
- Search Query
- Detection Rule
- Correlation Rule
- IOC Match
- Timeline
- Severity
- Risk Score
- Case
- Investigation

---

# Report Writing Sections

## Incident Summary

Brief overview of what happened.

---

## Timeline

Events listed in chronological order.

---

## Investigation

Evidence reviewed.

Analysis performed.

Observations recorded.

---

## Findings

Facts supported by evidence.

---

## Conclusion

Current assessment based on available evidence.

---

## Recommendations

Suggested next investigation or remediation steps.

---

# Questions Every SOC Analyst Should Ask

- What happened?
- When did it happen?
- Which user performed the activity?
- Which system was affected?
- Which Event IDs are involved?
- Which process was executed?
- Is this expected behavior?
- Does the activity match the normal baseline?
- What evidence supports this finding?
- What additional logs are required?
- Is escalation necessary?

---

# Common Reporting Phrases

- Based on available evidence...
- Initial analysis indicates...
- Evidence suggests...
- At this stage...
- No evidence currently confirms...
- Additional investigation is required.
- Correlation with additional logs is recommended.
- Activity appears consistent with normal behavior.
- Activity deviates from the established baseline.
- Investigation remains ongoing.

---

# Common Windows Event IDs

| Event ID | Description |
|----------|-------------|
| 4624 | Successful Logon |
| 4625 | Failed Logon |
| 4634 | Logoff |
| 4648 | Logon with Explicit Credentials |
| 4672 | Special Privileges Assigned |
| 4688 | Process Created |
| 4698 | Scheduled Task Created |
| 4720 | User Account Created |
| 4726 | User Account Deleted |
| 4732 | User Added to Security Group |
| 7045 | Service Installed |

---

# Severity Levels

| Severity | Meaning |
|----------|---------|
| Informational | Normal activity |
| Low | Low risk |
| Medium | Requires investigation |
| High | Likely suspicious |
| Critical | Immediate response required |

---

# Documentation Checklist

Before closing an investigation, verify:

- Incident summary completed
- Timeline documented
- Evidence collected
- Findings recorded
- Conclusion supported by evidence
- Recommendations provided
- No assumptions included
- Report is clear and concise

---

# Interview Communication Tips

During interviews:

- Explain your investigation step by step.
- Mention the evidence before giving a conclusion.
- Do not guess.
- Use phrases like "Based on available logs..." or "I would investigate further..."
- Explain why an activity is suspicious instead of simply calling it an attack.
- Show your thought process.

---

# Professional Mindset

A SOC analyst should:

- Think like an investigator.
- Stay objective.
- Validate evidence.
- Document everything.
- Correlate multiple events.
- Avoid assumptions.
- Escalate when necessary.
- Continue investigating until evidence supports a conclusion.

---

# Golden Rule

> Never report what you think happened.

> Report what the evidence shows.
