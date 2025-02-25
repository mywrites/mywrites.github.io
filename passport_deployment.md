---
layout: default
title: "Passport Deployment"
category: "Cybersecurity"
---

Deployment Passport, a Game Warden-specific term, is a body of evidence that includes the artifacts required to meet Authority to Operate (ATO) requirements. A Deployment Passport, signed by a government Information Systems Security Manager (ISSM), allows you as customers to **inherit** our ATO; a permission which authorizes application deployments into both the Staging (STG) and Production (PRD) environments.

The ATO is non-transferable and only valid for Game Warden-hosted applications.

## Components
A Deployment Passport consists of the following artifacts:
* **Certificate to Field**
  * A memo which annotates customer expectations, the Certificate to Field (CtF) serves as the first page (cover letter) of the Deployment Passport which includes the ISSM’s digital signature.
* **Authorization Boundary Diagram**
  * A visual presentation of your software components and data connections. When creating your diagram, you must display all data movement both within your application and outside this boundary. This includes specifications that describe which direction the data moves, such as ingress, egress, or bidirectional. You must denote the ports and protocols on all connections. You also must display all application containers and all external or managed services. Aligning your diagram with required specifications ensures compliance with ATO requirements. 
* **System Security Plan**
  * Form that provides content that proves you meet ATO security requirements. You create the System Security Plan (SSP) from a form within the Game Warden app, and the Game Warden Security team reviews this form. The SSP includes any required external approvals and proof of an active government contract for your company.
* **Security Findings Summary**
  * The Security Findings Summary includes hyperlinks to the Scan Results exported from Scan Lab.
* **ISSM Critical/High/Stop Security Findings Memo (As Applicable)**
  * A waiver memo specific to critical and high Common Vulnerabilities and Exposures (CVEs) that cannot be remediated. These vulnerabilities receive higher scrutiny such that there must be justification relative to how these risks are minimized.
* **Game Warden Authority to Operate Documentation**
  * Copy of the Game Warden ATO signed by an Authorizing Official (AO). The ATO is specific to the Impact Level associated with your application deployment.
* **Other Documentation (Optional)**
  * You may add supporting documentation as part of your body of evidence. If you have an ATO from another AO, for example, you may include this document.

You must have a signature-approved Deployment Passport for each Impact Level containing applications you want to deploy into STG and PRD. Our engineers do not require a signature-approved Deployment Passport to deploy applications into the Development (DEV) environment.

The Game Warden team uploads this body of evidence into the **Deployment Passports** section of the Documents page in the Game Warden Web App.

## Updates and Expiration
You must **update the Deployment Passport and SSP with each major release (or annually and before the current Deployment Passport expires)**. After you update the SSP, the Security team generates the remaining content to include Scan Results. Minor releases or patches do not require a new Deployment Passport or SSP.
