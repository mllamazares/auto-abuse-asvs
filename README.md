# 🥊 auto-abuse-asvs

![](https://img.shields.io/badge/license-MIT-green)
[![](https://img.shields.io/badge/LinkedIn-0077B5?logo=linkedin&logoColor=white)](https://www.linkedin.com/in/mllamazares/)
[![Watch on GitHub](https://img.shields.io/github/watchers/mllamazares/auto-abuse-asvs.svg?style=social)](https://github.com/mllamazares/auto-abuse-asvs/watchers)
[![Star on GitHub](https://img.shields.io/github/stars/mllamazares/auto-abuse-asvs.svg?style=social)](https://github.com/mllamazares/auto-abuse-asvs/stargazers)
[![Tweet](https://img.shields.io/twitter/url/https/github.com/mllamazares/STRIDE-vs-ASVS.svg?style=social)](https://twitter.com/intent/tweet?text=Check%20out%20auto-abuse-asvs%21%20https%3A%2F%2Fgithub.com%2Fmllamazares%2Fauto-abuse-asvs)

_Automagically_ selecting the top [Application Security Verification Standard (ASVS)](https://owasp.org/www-project-application-security-verification-standard) security controls for a given Abuse Case leveraging [Natural Language Processing (NLP)](https://en.wikipedia.org/wiki/Natural_language_processing).

Check out the Jupyter Notebook proof of concept here: [auto_abuse_asvs_poc.ipynb](./auto_abuse_asvs_poc.ipynb)

⚠️ **Disclaimer**: This project was created before the ChatGPT era.

## Rationale

To build a secure application, it's crucial to identify the potential attacks the application must defend against, based on its business and technical context. [^1]

In Security Requirement Engineering, a common practice is to define *Abuse Cases*. These describe how a feature can be exploited in ways the implementer did not anticipate, allowing an attacker to manipulate the feature or its outcome based on their actions or inputs.

Once we've defined a list of *Abuse Cases* using the business requirements as a reference, it’s time to mitigate those risks by designing the appropriate countermeasures. The [Application Security Verification Standard (ASVS)](https://owasp.org/www-project-application-security-verification-standard) provides an excellent framework of security controls, organized into the following chapters:

* V1 - Architecture, Design, and Threat Modeling
* V2 - Authentication
* V3 - Session Management
* V4 - Access Control
* V5 - Validation, Sanitization, and Encoding
* V6 - Stored Cryptography
* V7 - Error Handling and Logging
* V8 - Data Protection
* V9 - Communication
* V10 - Malicious Code
* V11 - Business Logic
* V12 - Files and Resources
* V13 - API and Web Services
* V14 - Configuration

### Why use this script?

Selecting the appropriate security controls can be a tedious task, considering there could be multiple *Abuse Cases* for each *User Story*, and nearly 300 ASVS controls to choose from.

Given an *Abuse Case* as input, this script automatically selects the top 10 ASVS security controls by matching descriptions using [NLP](https://en.wikipedia.org/wiki/Natural_language_processing). The output is ranked by similarity score.

For testing purposes, I’ve selected 14 *Abuse Cases* from the [MITRE ATT&CK Enterprise Tactics](https://attack.mitre.org/tactics/enterprise/) (one per section).

Please note that this script is just a Proof of Concept and should not be relied upon for the complete selection of security controls. I strongly recommend double-checking the output. However, it can assist in identifying the most relevant controls for your *Abuse Case*.

## TODO
- [ ] Create a REST API using [FastAPI](https://fastapi.tiangolo.com/).
- [ ] Develop a user-friendly UI with [TailwindUI](https://tailwindui.com/).
- [ ] Include support for other ASVS languages.
- [ ] Dockerize the project.
- [ ] Allow users to edit the list of security controls.
- [ ] Enable export of the output to CSV, JSON, or Jira.

[^1]: Extracted from https://cheatsheetseries.owasp.org/cheatsheets/Abuse_Case_Cheat_Sheet.html
