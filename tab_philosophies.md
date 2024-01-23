---
title: Philosophies
tab: true
order: 2
tags: cc
---
# The Five Philosophies of Log Design

*TL;DR*: Effective logs should be simple, structured, and informative without compromising sensitive information. Avoid accidental data exposure to prevent security breaches.

## :one: Simplicity, Structure, and Detail

A well-designed log should offer a clear understanding at a glance. Avoid over-complication; logs aren't just data caches but sources of necessary information. Focus on these aspects:

- :pencil2: **Log simplicity and structure**: Ensure uniformity across logs, regardless of the developer.
- :bulb: **Purpose of logs**: Define whether they're for debugging, security events, or performance metrics. Decide this early to avoid logging irrelevant data.
- :gear: **Integration with systems like SIEM**: Consider how logs will be structured for external analysis.

## :two: Tagging and Metadata

Be mindful of the data your application handles. Sensitive information like personal health data (PHI) and personally identifiable information (PII) should be treated cautiously. Consider tagging data to manage privacy levels effectively. Example snippets:

```plaintext
// Non-sensitive data
Logger().info("Smoothie name: \(smoothieName, privacy: .public)")

// Sensitive data
let userPassw : Str = getUserPassw()
Logger().info("User’s Password: \(userPassw, privacy: .secret)")
```

## :three: Clean and Focused Logging

Logs grow with your application. Regular maintenance and cleaning of logs are essential to avoid 'logging debt'. Aim for logs that are informative and relevant. Regular benchmarking and testing of logs should be a part of your development cycle.

## :four: Log with Security in Mind

Assume that a security compromise can occur. Design your logs to assist in forensic analysis and incident response. Logging should cater not only to debugging but also to security and forensic readiness.

## :five: Access, Storage, and Transportation of Logs

Be cautious about who can access logs and how they are stored and transmitted. Logs should be informative yet secure, without exposing sensitive application details or user information.

---


:trophy: **Acknowledgements and Inspiration**

A heartfelt :heart: thank you to Eric and all the dedicated developers and visionaries who contributed their insights and expertise to this project. Their collective wisdom has been invaluable in shaping these philosophies.

:books: This work is also inspired by the insightful narratives found in 'The Unicorn Project' and 'The Phoenix Project', which offer profound lessons in IT, DevOps, and software development.

:loudspeaker: Stay tuned for more in-depth discussions and explorations of these topics. This article was first published on my website and is part of a series dedicated to advancing understanding and best practices in the field of log design.


