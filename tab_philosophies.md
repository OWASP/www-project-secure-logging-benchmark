# The Five Philosophies of Log Design

*TL;DR*: Effective logs should be simple, structured, and informative without compromising sensitive information. Avoid accidental data exposure to prevent security breaches.

## 1. Simplicity, Structure, and Detail

A well-designed log should offer a clear understanding at a glance. Avoid over-complication; logs aren't just data caches but sources of necessary information. Focus on these aspects:

- **Log simplicity and structure**: Ensure uniformity across logs, regardless of the developer.
- **Purpose of logs**: Define whether they're for debugging, security events, or performance metrics. Decide this early to avoid logging irrelevant data.
- **Integration with systems like SIEM**: Consider how logs will be structured for external analysis.

## 2. Tagging and Metadata

Be mindful of the data your application handles. Sensitive information like personal health data (PHI) and personally identifiable information (PII) should be treated cautiously. Consider tagging data to manage privacy levels effectively. For example:

```plaintext
// Non-sensitive data
Logger().info("Smoothie name: \(smoothieName, privacy: .public)")

// Sensitive data
let userPassw : Str = getUserPassw()
Logger().info("User’s Password: \(userPassw, privacy: .secret)")
```


## 3. Clean and Focused Logging

Logs grow with your application. Regular maintenance and cleaning of logs are essential to avoid 'logging debt'. Aim for logs that are informative and relevant. Regular benchmarking and testing of logs should be a part of your development cycle.



## 4. Log with Security in Mind

Assume that a security compromise can occur. Design your logs to assist in forensic analysis and incident response. Logging should cater not only to debugging but also to security and forensic readiness.

## 5. Access, Storage, and Transportation of Logs

Be cautious about who can access logs and how they are stored and transmitted. Logs should be informative yet secure, without exposing sensitive application details or user information.

---

Special thanks to Eric and all the developers and wizards who contributed to these insights. Inspired by 'The Unicorn Project' and 'The Phoenix Project'.

This article was first published on my website. Stay tuned for more in-depth discussions on these topics.
