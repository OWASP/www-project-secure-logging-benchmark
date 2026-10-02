# OWASP Secure Logging Benchmark

[![OWASP Incubator](https://img.shields.io/badge/owasp-incubator%20project-53AAE5.svg)](https://owasp.org/projects/)
[![OWASP Builders](https://img.shields.io/badge/owasp-builders-blue.svg)](https://owasp.org/projects/)
[![OWASP Breakers](https://img.shields.io/badge/owasp-breakers-red.svg)](https://owasp.org/projects/)

This is the home of the OWASP Secure Logging Benchmark project. The project page is at [owasp.org/www-project-secure-logging-benchmark](https://owasp.org/www-project-secure-logging-benchmark/).

## Links

- [Project page](https://owasp.org/www-project-secure-logging-benchmark/)
- [Blog](https://veronica-schmitt.com/category/blog-posts/)

## Introduction

Application logs often contain sensitive information, or expose details such as internal endpoints that give an attacker easy targets. The OWASP Top 10 (2021) recognises this risk under A02 Cryptographic Failures (formerly Sensitive Data Exposure) and A09 Security Logging and Monitoring Failures. Logging is valuable, but it is a double-edged sword.

Developers usually design logs for debugging, and for other developers. A secure logging standard treats logs as security and forensic artefacts as well. Detecting and responding to an incident depends heavily on the information that was built into the application logs before the incident occurred.

Two failure modes are common. In the first, logging is so verbose that critical events are lost in the noise, or are overwritten before anyone reads them. In the second, events are logged with little or no context, so they cannot be interpreted. Logs should therefore be designed not only for developers, but also for the forensic analyst who will one day need to reconstruct what happened.

Messy, noisy logs are often a symptom of unclean code: log levels are not set correctly, data is tagged inappropriately, and sensitive values leak into production logs. Deliberate log design, with controls built in to prevent sensitive data disclosure, avoids these problems.

## Project Overview

The project provides a benchmark for application logs based on NIST SP 800-53 security controls, in particular the Audit and Accountability (AU) family, while taking debugging needs and system performance into account. It covers:

- Log levels and what they mean
- Event categories and why they matter
- Data classification and prevention of sensitive data disclosure
- Log structure
- Log message content and how to identify weaknesses in it
- Building forensic readiness into application logs
- Log hygiene and analysis techniques
- Two weeks of training material for populating logging hygiene backlog items to address within sprints
- A guide to applying the benchmark within an application security team

## Why It Matters

This project is a movement as much as it is a standard. Logs are for more than debugging and system metrics. They give insight into code quality and can reveal problems within development teams. They are essential for understanding a breach, mitigating future breaches, and gathering information for threat modelling.

## Project Leader

- Veronica Schmitt
