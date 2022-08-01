# auto-abuse-asvs
Automatically select the top [Application Security Verification Standard (ASVS)](https://owasp.org/www-project-application-security-verification-standard) security controls for a given Abuse Case using NLP.

Check the Jupyter Notebook here: **[👉 auto_abuse_asvs_poc.ipynb 👈](./nlp_auto_asvs_poc.ipynb)**

## Rationale 

In order to build a secure application, from a pragmatic point of view, it is important to identify the attacks which the application must defend against, according to its business and technical context. [^1]

A common practice in Security Requirement Engineering is to define *Abuse Cases*, that is, a way to use a feature that was not expected by the implementer, allowing an attacker to influence the feature or outcome of use of
the feature based on the attacker action (or input).

Once we've defined a list of Abuse Cases using the Business Requirements as reference, is time to mitigate those risks by design the corresponding contermeasures. [Application Security Verification Standard (ASVS)](https://owasp.org/www-project-application-security-verification-standard) provides an excellent blueprint to select security controls. It is organized in the following sections:

* V1 - Architecture, Design and Threat Modeling
* V2 - Authentication
* V3 - Session Management
* V4 - Access Control
* V5 - Validation, Sanitization and Encoding
* V6 - Stored Cryptography
* V7 - Error Handling and Logging
* V8 - Data Protection
* V9 - Communication
* V10 - Malicious Code
* V11 - Business Logic
* V12 - Files and Resources
* V13 - API and Web Service
* V14 - Configuration

### Why do we need this script?

Selecting the corresponding security controls can be a tedious task, considering that could be 1 to N *Abuse Cases* by each *User Story*, and there are nearly 300 ASVS controls available.

Given an input *Abuse Case*, this script will automatically select the top 10 ASVS security controls by matching the descriptions using [NLP](https://en.wikipedia.org/wiki/Natural_language_processing). The output is ranked by similarity score.

For testing purposes, I've selected 14 *Abuse Cases* from [MITRE ATT&CK Enterprise Tactics](https://attack.mitre.org/tactics/enterprise/) (one per section).

Note that this script is just a Proof Of Concept, it will not completely replace the security control selection. I strongly encourage you to double-check the output. However, it can help you to identify the most related to your *Abuse Case*.

## TODO
- [ ] Create an REST API with [FastAPI](https://fastapi.tiangolo.com/).
- [ ] Create a nice UI with [TailwindUI](https://tailwindui.com/).
- [ ] Include other ASVS languages.
- [ ] Dockerize.
- [ ] Let the user edit the list of security controls.
- [ ] Export the output to CSV, JSON or Jira. 

[^1]: Extracted from https://cheatsheetseries.owasp.org/cheatsheets/Abuse_Case_Cheat_Sheet.html
