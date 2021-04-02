---

layout: col-sidebar 
title: OWASP Secure Logging Benchmark 
site_side: true
tags: logging-benchmark
project: true 
level: 2 
type: documentation

---

## Introduction:

The information that is often written in the log may be sensitive in nature or give an attacker access to low-hanging
fruit in terms of exposure of endpoints or other sensitive information. The OWASP in the Top 10 refers to “Sensitive
Data Exposure" as one of the risk factors for any application. Logging of information can be beneficial but this is
often a double ended sword. Developers design logs with debugging in mind. Application logs are designed by developers
for developers. There are important components to have a secure standard of logging. There is great power within logging
and taking into account designing your logs with future breaches in mind. “When nothing goes right, just go left". The
process of detecting or dealing with an incident relies heavily on having the information built into the application
logs prior to an incident occurring. The biggest pitfall of dealing with a potential breach is that your logging is
verbose and critical data is lost between the noise or logs are overwritten. Another extreme is that the information
that is logged has little to no context or information surrounding an event. When designing application logs there
should be consideration taken to not only log what is important to developers but to consider and be kind to the future
forensicator tasked with reading your logs. Logs which are messy and noisy are often the result of not clean code. When
this occurs you have instances where log levels have not been adequately set and data inappropriately tagged and leaked
within production logs. There should be thought placed into your logs, and the information you put into them. There
should be clear attention given to prevent sensitive data disclosure by building in controls.

## Project Overview:
A benchmarking for application logs that are based on the NIST Security Controls taking into account debugging and
system performance.

1. Log levels and what they mean
1. Event categories and why they are important
1. Classification of data and preventions of sensitive data disclosure
1. Logging Structure
1. Content within log messages and identifying weaknesses within these
1. Building in forensic readiness within application logs
1. Log hygiene and analysis techniques
1. Two weeks of training material that you can use to populate logging hygiene backlogs items to address within sprints.
1. A guide on how to apply this within your application security team.

This project is a movement more than it is a standard. Logs are for more than just debugging and system metrics. They
give insights into code quality and can be a symptom of problems within development teams. They are crucial to
understanding a breach, mitigation against breaches and information gathering for threat modeling.
