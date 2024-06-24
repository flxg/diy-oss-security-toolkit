# DIY OSS Security Toolkit
A DIY guide on how to set up your code scanning and app security toolkit, covering ten different types of scanning solutions.

You’re confident in your development chops—confident enough to know the apps you’ve built aren’t completely free of security and configuration flaws. You’ve also researched the deep ecosystem of scanning tools available and perhaps got overwhelmed by the sheer volume of choice. What’s the right “portfolio” of open-source app security tools to identify vulnerabilities in your dependencies, Infrastructure as Code (IaC) configurations, containers, and more?

To get you on the right track, we’ll cover 10 essential categories of code scanning and security tooling, and recommend 9 OSS projects, with just the essential information you need to get started:

How that scan helps the security of your app.
Which open-source project you can install and how to run it.
Some alternatives (when available) you can pick from.
With that, you’ll have a no-BS path to scan your apps for critical security issues in code and cloud configurations. What’s not to love?

Well, the configuration and management part isn’t all roses—but we’ll get to that later.

This list results from Pull Requests, reviews, ideas, and work done by 1600+ people. You can also help by sending Pull Requests to add more services or remove ones whose offerings have changed or been retired.

NOTE: This list is only for open source solutions, not for closed source solutions. To be eligible, an OSS project must be free to use under a blablabla license.

# Table of Contents

  * [#1: Cloud security posture management (CSPM)](#cspm)
  * [#2: Software composition analysis (SCA) of open-source dependencies](#sca)
  * [#3: Secrets detection](#secrets)
  * [#4: Static application security testing (SAST)](#sast)
  * [#5: Dynamic application security testing (DAST)](#dast)
  * [#6: Infrastructure as code (IaC) scanning](#iac)
  * [#7: Container image scanning](#container)
  * [#8: Open-source license scanning](#license)
  * [#9: Malware detection](#malware)
  * [#10: End-of-life (EOL) runtime detection](#eol)


## #1: Cloud security posture management (CSPM)
CSPM helps you enhance the security and compliance of your cloud environments. By continuously monitoring your applications and their upstream services against industry best practices and your internal policies, CSPM tools assess issues, prioritize them based on their criticality, and offer recommendations for remediation. With CSPM, you take more ownership of the baselines and guardrails that prevent yourself or others from promoting vulnerable applications to production while also rooting out misconfigurations and overly permissive user roles.

  * [Syft]([https://github.com/anchore/syft) + [Grype](https://github.com/anchore/grype)
    * For locally-run SCA, you’ll need Syft to create a software bill of materials (SBOM) and Grype to analyze said SBOM for known vulnerabilities. Since the same team makes Syft and Grype, they support many installation methods but recommend their respective one-liners:

## #2: Software composition analysis (SCA) of open-source dependencies
Your apps inevitably have a large tree of open-source dependencies that you now rely on, from your UI framework all the way down to helper libraries you use in a single LOC, like a validator for email addresses. SCA is like a background check on your code’s extended family, identifying security vulnerability and licensing issues not once, but continuously. Because your SCA tools notify you about new vulnerabilities and remediations, you’ll have confidence your open-source supply chain remains a helper, not a hindrance, to productivity.

  * [CloudSploit](https://github.com/aquasecurity/cloudsploit)

**[⬆️ Back to Top](#table-of-contents)**

## #3: Secrets detection
A secrets detection tool scans your code and configurations for credentials you don’t want to expose publicly. These secrets can include API keys, access tokens to third-party providers, passwords to upstream databases, certificates, encryption keys, and more, and once they’re pushed to a public repository, you’ll have to go through a painful process to remove them from your Git history—better to detect them early and take action before you commit.

  * [Gitleaks](https://github.com/gitleaks/gitleaks)
  * [Bandit](https://github.com/PyCQA/bandit) (Python)
  * [gosec](https://github.com/securego/gosec) (Go)
  * [Brakeman](https://github.com/presidentbeef/brakeman) (Ruby on rails)

**[⬆️ Back to Top](#table-of-contents)**

## #4: Static application security testing (SAST)
SAST is the fine-toothed comb of app security tools, analyzing your codebase line by line to check for flawed syntax, structure, or logic that could leave your app vulnerable. Think SQL injection attacks, cross-site scripting (XSS) opportunities, buffer overflows, and more. By checking against popular databases of known CVEs, a solid SAST tool will give you confidence that you’re not leaving big security flaws on the table—and some even offer autofix suggestions for quick remediation.

  * [SemGrep](https://github.com/semgrep/semgrep)

**[⬆️ Back to Top](#table-of-contents)**

## #5: Dynamic application security testing (DAST)
Unlike SAST, DAST simulates commonly exploited vulnerabilities against your app in a live environment. It’s less about the syntax and structure of the code you wrote and much more about replicating the approaches an attacker might take against your production deployment. DAST tools will double-check known CVEs in frameworks and libraries you use and test whether logged-in users can access sensitive data due to broken permissions or “toxic combinations” of multiple vulnerabilities that open your app to far worse consequences.

**[⬆️ Back to Top](#table-of-contents)**

## #6: Infrastructure as code (IaC) scanning
Your code is just half the equation in getting to production—today, most teams use IaC tools like Terraform, CloudFormation, and “base” Kubernetes Helm charts to provision cloud services in a declarative, version-controlled, and repeatable fashion. IaC scanners identify vulnerabilities in these JSON or YAML blueprints to prevent you from ever deploying an insecure state to production.

**[⬆️ Back to Top](#table-of-contents)**

## #7: Container image scanning
We love containers because they abstract away so much complexity, but whenever you build a container image, it can inherit vulnerabilities from its base image or package dependencies. Container image scanners discover vulnerabilities in your base images and Dockerfiles, however deep the dependency tree goes, to prevent you from unwittingly deploying an exploitable app.

**[⬆️ Back to Top](#table-of-contents)**

## #8: Open-source license scanning
The legality of using open-source software in your commercial products isn’t something you check with legal or compliance teams once and forget about. OSS projects change licenses more frequently than you might understand, requiring you to either pay for an enterprise version, seek an alternative, or open-source some of your private code. License scanners identify changes and help you sail through security audits with a ready-to-go software bill of materials (SBOM).

**[⬆️ Back to Top](#table-of-contents)**

## #9: Malware detection
Malware scanners help you identify a threat that’s taken off in recent years: malware injected into dependency packages by attackers. The recent zx backdoor attempt is a fantastic—and frightening—example. Malware scanners detect these software supply chain attacks before you even merge your code to prevent you from having to make time-sensitive and costly fixes once the CVE goes public.

**[⬆️ Back to Top](#table-of-contents)**

## #10: End-of-life (EOL) runtime detection
The more frameworks, libraries, and runtimes you include in your app, the more opportunities there are for you to be leveraged dangerously against outdated versions or unmaintained dependencies. This is especially critical for runtimes directly exposed to the public internet. EOL runtime detectors read your dependency tree through lockfiles—even those in containers—to alert you well ahead so you can prepare for updates or migrations.


**[⬆️ Back to Top](#table-of-contents)**
