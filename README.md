# swiss-cheese
🧀🧀 A demo repository of small OWASP Top 10 vulnerabilities. Like swiss-cheese, this code is full of holes. Goes great with Github Advanced Security 🧀🧀

![License](https://img.shields.io/github/license/austimkelly/swiss-cheese.svg) 
![Python 3](https://img.shields.io/badge/python-3-blue.svg)
[![CodeQL](https://github.com/austimkelly/swiss-cheese/actions/workflows/codeql.yml/badge.svg)](https://github.com/austimkelly/swiss-cheese/actions/workflows/codeql.yml)
[![tfsec](https://github.com/austimkelly/swiss-cheese/actions/workflows/tfsec.yml/badge.svg)](https://github.com/austimkelly/swiss-cheese/actions/workflows/tfsec.yml)

# Purpose

The code samples here here several a couple of main purposes:

## Understanding of Secure Coding Practices

1. Show specific hands on examples of OWASP Top 10 vulnerabilities with small "working" code samples.
2. Demonstrate a specific vulnerability and discuss how a code review might have prevented it. 
3. Practice fixing vulnerabilities.
4. Basic understanding of SAST tooling. Specifically using features in Github Advanced Security.
5. Using an AI coding assistant such as Github Copilot to ask question about code and what security weaknesses may exist. Additionally, AI coding assistants can provide targeted recommendations for fixes. We can also experiment with threat modeling methodologies such as STRIDE and PASTA.

## Github Advanced Security Exercises

This repository is also used as a training exercise for Github Advanced Security (GHAS) features. See [GHAS Exercises](./doc/ghas-exercises.md) for more details.

In short, you can fork this repository and practice enabling and tuning GHAS features on known vulnerable code and dependencies.

# Code Authors

Unless otherwise sited in the code, the scripts herein are generated by a combination of Tim Kelly (human) and AI coding assistants (ChatGPT, Github Copilot).  

* The supply-chain example is based on source from https://github.com/kozmer/log4j-shell-poc
* The IaC Terraform misconfiguration is from https://github.com/aquasecurity/tfsec

# Installation Guide

Follow these steps to install the necessary dependencies for the project:

1. Clone the repository:

`git clone git@github.com:austimkelly/swiss-cheese.git`

2. Navigate to the project directory:

`cd swiss-cheese`

3. Install the dependencies from the `requirements.txt` file:

`pip3 install -r requirements.txt`

4. Navigate to the directory for the demo you want to run and run the python file there (e.g. `$cd idor` then `$python3 idor.py`): 

# Demo Listing & References

| **Demo Link** | **Description** | **References** |
| --- | --- | --- |
| [broken-auth](./broken-auth/) | Demonstrates a session management vulnerability if an attacker get ahold of an authentication session token. | [OWASP Session Management Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Session_Management_Cheat_Sheet.html) |
| [idor](./idor/) | Demonstrates broken access control for easily guessable IDs and no authentication. | [OWASP IDOR](https://owasp.org/www-chapter-ghana/assets/slides/IDOR.pdf) |
| [sqli](./sqli/) | Demonstrates standard SQL Injection being able to dump a database from a form field. | [OWASP SQL Injection](https://owasp.org/www-community/attacks/SQL_Injection) |
| [ssrf](./ssrf/) | Demonstrate a server-side request forgery tricking the app to making an HTTP request to a not-allowed 3rd party domain. | [OWASP Server Side Request Forgery](https://owasp.org/www-community/attacks/Server_Side_Request_Forgery) |
| [xss](./xss/) | Demonstrates executing arbitrary javascript inside the application. | [OWASP Cross Site Scripting](https://owasp.org/www-community/attacks/xss/) |
| [secrets](./secrets/) | An example of leaking a secrets file or environment variable configuration. | [Github Secrets Push Protection](https://docs.github.com/en/enterprise-cloud@latest/code-security/secret-scanning/push-protection-for-repositories-and-organizations), [OWASP Secrets Management Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/Secrets_Management_Cheat_Sheet.html) |
| [supply-chain](./supply-chain/) | An example of a supply chain vulnerability in log4j. This one is to demonstrate dependency vulnerabilities and a security advisory. There are several OWASP Top 10 here: security misconfiguration, using components with known vulnerabilities, insufficient logging and monitoring. | [OWASP Supply Chain Vulnerabilities](https://owasp.org/www-project-kubernetes-top-ten/2022/en/src/K02-supply-chain-vulnerabilities) |
| [iac](./iac-misconfiguration/) | An example of a Terraform misconfiguration. . | [OWASP Security Misconfiguration](https://owasp.org/Top10/A05_2021-Security_Misconfiguration/) |