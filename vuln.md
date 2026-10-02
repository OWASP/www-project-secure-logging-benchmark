# Logging Vulnerabilities

## Overview

> **Note:** Weaknesses in how applications write, store and monitor logs expose them to security, privacy and compliance risks. This page describes the most common logging vulnerabilities, maps each to its Common Weakness Enumeration (CWE) entry, and gives practical mitigations. The figures quoted come from the Secure Logging Benchmark developer survey, in which respondents reported the vulnerabilities they had encountered (n = 102, multiple selections allowed).

## Common Logging Vulnerabilities

### 1. Insufficient Logging

> **Warning:** Security-relevant events such as failed logins, privilege changes and access to sensitive data are not recorded, or are recorded without the context needed to investigate them. This was the most frequently encountered vulnerability in the survey (46.1%).

- **Weakness:** CWE-778 Insufficient Logging; CWE-223 Omission of Security-relevant Information; OWASP A09:2021
- **Mitigation:** Define the security events every component must log. Include a timestamp, user or service identifier, source address, action, target resource and outcome in each entry.

### 2. Logging Sensitive Information

> **Important:** Passwords, session tokens, API keys, personal data (PII) or health data (PHI) are written to logs. 44.1% of respondents had encountered sensitive information in logs, and 35.3% had found authentication information.

- **Weakness:** CWE-532 Insertion of Sensitive Information into Log File
- **Mitigation:** Classify data before logging it. Apply allow-list logging or masking filters in the logging framework, never log authentication material, and scan existing logs for leaked secrets.

### 3. Information Disclosure Through Logs

> **Important:** Logs record more detail than diagnostics require, such as full stack traces, internal hostnames, endpoints or query strings, and are exposed to users or attackers. 43.1% of respondents had encountered this.

- **Weakness:** CWE-200 Exposure of Sensitive Information to an Unauthorized Actor
- **Mitigation:** Log only what is necessary for diagnostics and auditing. Return generic error messages to users and keep detailed diagnostics in protected logs.

### 4. Log Injection and Poisoning

> **Warning:** Unvalidated input written to a log allows an attacker to forge entries, break log parsing or inject content that misleads analysts. 11.8% of respondents had encountered log poisoning.

- **Weakness:** CWE-117 Improper Output Neutralization for Logs
- **Mitigation:** Encode or strip control characters such as CR and LF from user-supplied values. Use structured formats such as JSON, so that input is stored as a field value and never interpreted as log syntax.

### 5. Log Flooding and Suppression

> **Warning:** An attacker generates excessive log volume to exhaust storage, push older entries out of rotation or hide activity in noise, or blocks logging entirely. 16.7% of respondents had encountered blocking or overloading of logging systems.

- **Weakness:** CWE-779 Logging of Excessive Data; CWE-400 Uncontrolled Resource Consumption
- **Mitigation:** Use appropriate log levels in production, rate-limit repetitive events, size storage for peak volume, and alert when log sources go silent.

### 6. Tampering and Insecure Storage

> **Important:** Logs stored without access controls or integrity protection can be read, altered or deleted, which destroys their value as evidence.

- **Weakness:** CWE-117 (forged entries); CWE-532 (exposure of stored logs)
- **Mitigation:** Restrict access to authorised personnel, encrypt logs in transit and at rest, forward them to a central store, and make entries tamper-evident through hash chaining or signatures.

### 7. Inconsistent Timestamps and Formats

> **Warning:** Unsynchronised clocks and inconsistent formats between systems make it impossible to reconstruct an accurate event timeline across components.

- **Mitigation:** Synchronise clocks with a trusted time source such as NTP and record timestamps in UTC using ISO 8601. Where synchronisation is not possible, preserve ordering with monotonic counters. Adopt one structured log format across teams.

### 8. Failure to Monitor and Retain Logs

> **Warning:** Logs that are never reviewed, or are purged before an incident is discovered, provide no detection capability and no evidence.

- **Mitigation:** Feed logs into monitoring and alerting such as a SIEM, and set retention periods that match detection timelines and regulatory obligations.

## Best Practices for Secure Logging

> **Tip:** These practices address the vulnerabilities above and align with the benchmark's forensic-ready logging requirements.

- **Structured format:** Use a consistent, machine-readable format across all teams and systems.
- **Security events:** Record authentication attempts, access to sensitive data, privilege changes and configuration changes.
- **Context:** Enrich every entry with the metadata needed to attribute and correlate it.
- **Minimise data exposure:** Exclude or mask sensitive data, and log only what is necessary.
- **Trusted time:** Synchronise timestamps, or preserve event order where synchronisation is not possible.
- **Integrity:** Make log entries tamper-evident and restrict access to authorised personnel.
- **Monitoring and retention:** Alert on suspicious activity and retain logs long enough to support investigation.
- **Regular audits:** Review logging configuration and log content as part of each release.
