_**Disclaimer: this was created in the pre-GPT era.**_ :)

---

# auto-abuse-asvs

![](https://img.shields.io/badge/lisense-MIT-green)
[![](https://img.shields.io/badge/LinkedIn-0077B5?logo=linkedin&logoColor=white)](https://www.linkedin.com/in/mllamazares/)
[![Watch on GitHub](https://img.shields.io/github/watchers/mllamazares/auto-abuse-asvs.svg?style=social)](https://github.com/mllamazares/auto-abuse-asvs/watchers)
[![Star on GitHub](https://img.shields.io/github/stars/mllamazares/auto-abuse-asvs.svg?style=social)](https://github.com/mllamazares/auto-abuse-asvs/stargazers)
[![Tweet](https://img.shields.io/twitter/url/https/github.com/mllamazares/STRIDE-vs-ASVS.svg?style=social)](https://twitter.com/intent/tweet?text=Check%20out%20auto-abuse-asvs%21%20https%3A%2F%2Fgithub.com%2Fmllamazares%2Fauto-abuse-asvs)

Automatically select the top [Application Security Verification Standard (ASVS)](https://owasp.org/www-project-application-security-verification-standard) security controls for a given Abuse Case using [Natural Language Processing (NLP)](https://en.wikipedia.org/wiki/Natural_language_processing).

Check the Jupyter Notebook PoC here: **[👉 auto_abuse_asvs_poc.ipynb 👈](./auto_abuse_asvs_poc.ipynb)**

## Rationale 

In order to build a secure application, from a pragmatic point of view, it is important to identify the attacks that the application must defend against, according to its business and technical context. [^1]

A common practice in Security Requirement Engineering is to define *Abuse Cases*, that is, a way to use a feature that was not expected by the implementer, allowing an attacker to influence the feature or outcome of the use of the feature based on the attacker action (or input).

Once we've defined a list of *Abuse Cases* using the business requirements as a reference, is time to mitigate those risks by designing the corresponding countermeasures. [Application Security Verification Standard (ASVS)](https://owasp.org/www-project-application-security-verification-standard) provides an excellent blueprint of security controls organized in the following chapters:

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
