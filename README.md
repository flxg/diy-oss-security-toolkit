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

  * [CloudSPloit](https://github.com/aquasecurity/cloudsploit)
    * To install CloudSploit, you’ll first need Node.js to download its dependencies and run the engine.
    * Next, you need to configure CloudSploit with read permissions to your cloud account, with support for AWS, Azure, GCP, and Oracle. Follow the directions for your cloud provider, using the repo’s config_example.js file as your template, to create a config.js file with all the details you’ll need to run your first complete diagnostic and get results in JSON.



