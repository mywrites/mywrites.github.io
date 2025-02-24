---
layout: default
title: "Game Warden Platform"
category: "Cybersecurity"
---
 <link rel="stylesheet" href="styles.css">
Game Warden is a Department of Defense (DoD)-authorized DevSecOps platform that quickly, securely, and cost-effectively deploys SaaS solutions into government networks – streamlining the software delivery process. Game Warden provides all tooling required to secure, harden, and run your applications.

## GitLab
Game Warden tooling includes GitLab, which is a DevSecOps platform used to store code, track issues, and develop and deploy Continuous Integration and Continuous Delivery (CI/CD) pipelines. These pipelines move your applications through Game Warden's scanning, hardening, and deployment processes. Within these pipelines, the Game Warden team uses Anchore Enterprise and Prisma Cloud to perform primary image security scans which produce a manifest of Common Vulnerabilities and Exposures (CVEs). As the name implies, this report identifies application image issues that require your attention. You can view and address CVEs in Scan Lab, accessible via the Game Warden Web App and, more specifically, App Central.

## Registries
Currently, you can push images to both the Nexus and Harbor registries. The Game Warden team is slated to transition to Harbor registry use only. With both registries, CI/CD pipelines move your images through the scanning and hardening processes. The Game Warden team uses Anchore Enterprise and Prisma Cloud to both scan/harden images and identify vulnerabilities. The team also uses ClamAV for malware detection.

**NOTE:**
First, a bit of clarity relative to images and containers . . .

Docker, at its core, is a Platform as a Service (PaaS) that enables developers to build and deploy containers which store applications and their dependencies. Since a container stores applications and all components that applications need to run successfully, containerized applications function as designed despite where you deploy them.

A Dockerfile is a text file that includes instructions on how to build a base image. A Docker image can have several layers. The first layer is the base image and represents the foundation upon which you can build other images. You must not modify the base image.

Multiple images combine to form a single application, with each image providing a specific function. For example, you might use `rhel`, commonly known as `ubi`, as your base image; `ubi` is a universal base image that functions as an operating system. From `ubi` , you might add `nginx` (pronounced “engine-x”) atop this unmodified base image. `nginx`, which has many uses, might function as your web server. You might add other images as well. These other images provide additional functionality, and each additional image aligns with a specific application need. Again, all images combine to form a single application that includes the functionality designated by each.

## Nexus
Nexus is a secure image registry. As containerized images enter GitLab, a GitLab pipeline or API interacts with this registry.

There are three primary Nexus registries:

* External – This registry contains unhardened images. When you initially send us your containerized images, you add them to the External registry.
* Unapproved – This registry contains hardened images. After you send our team images, we scan them and produce CVEs. After you resolve or justify CVEs, our team hardens images and stores them in this registry. Hardening removes unneeded components, such as ports or libraries, which may trigger breaches/attacks/vulnerabilities. After you have resolved or justified vulnerabilities, this image may be deployed to your Development (DEV) environment. Here, our engineers perform preliminary application testing and configuration. In many cases, the images may need to be hardened again, contingent upon subsequent discovered vulnerabilities. When image vulnerabilities are at an acceptable level such that they satisfy Authority to Operate (ATO) requirements, they are moved to the Approved registry.
* Approved – This registry contains hardened images. The Game Warden team, after Security team consent, deploys images from this Approved registry to your Kubernetes cluster.

## Harbor
Harbor is a secure image registry. As an open source and feature-rich registry, Harbor manages the images you push into this environment. As your images navigate the scanning and hardening processes, tags are appended to the end of your image names to designate the status of each.

## Pipelines, Processes
A pipeline is a set of automated tasks, and the vehicle the Game Warden team uses to move your applications through the scanning, hardening, and deployment processes. Our engineers establish Game Warden infrastructure, tooling, and access controls for your application. They also establish pipelines along with bootstrap scripts. Pipelines determine the CI/CD path for coding, testing, and deploying your applications. Bootstrap scripts are written to automate image or container movement, promoting both efficiency and speed. You can view some of the pipelines in Scan Lab, which provide insight into your image progression through our processes.

Your application must undergo a rigorous process of image scanning and hardening coupled with mandatory approval by our Security team prior to any deployments.

As your images reside in the Approved registry, a green-light meeting takes place with Game Warden leadership to ensure applications are secure with solely a limited yet acceptable level of vulnerabilities.

Our Security team examines three layers of security controls:

* Infrastructure as Code (AWS)
* Platform (Kubernetes)
* Applications

Game Warden generates a body of evidence, the Deployment Passport, that allows the government to make a security determination and grant a Certificate to Field (CtF). A memo which annotates customer expectations, the CtF also serves as the cover letter for the Deployment Passport and includes the signature of the government Information Systems Security Manager (ISSM). The Security team along with a government official must review your architecture, diagrams, and other information before approving this Deployment Passport. The Deployment Passport document includes the System Security Plan (SSP), vulnerability scan results, any required external approvals, and proof of a government contract for your company. This ISSM signature-approved document serves as your ticket into the DoD, as you inherit our ATO.

You must have a signature-approved Deployment Passport for each Impact Level containing applications you want to deploy into Staging (STG) and Production (PRD). Our engineers do not require a signature-approved Deployment Passport to deploy applications into DEV.

ATO is a designation a government official provides on behalf of a Federal agency that authorizes companies or organizations to operate their IT systems on a government network. Government officials grant ATOs to companies who have proven that their IT systems are secure and pose limited (if any) risks to their environments. Similar to an admissions ticket, an ATO is the government’s official approval and acceptance that allows you to run your applications in this government space.

While your first deployment is into DEV, you neither require a signature-approved Deployment Passport nor an ATO. Clients have full access to DEV. In GovCloud, DEV is an Impact Level 2 (or IL2) space. DEV IL2 houses non-classified data with generally open access policies. As such, both clients and engineers have access to this environment. Our engineers commonly access DEV IL2 to configure the environment and ensure your application functions as designed.

After you have completed functional testing in DEV, have addressed any security concerns, and received a signed Deployment Passport (and inherited our ATO), Game Warden engineers deploy your application into the STG environment. In GovCloud, STG is commonly IL4 and can house Controlled Unclassified Information (CUI). Limited persons have access to this environment. Here, engineers usually perform application-level tasks and, again, must ensure your application functions properly. Extensive testing is performed at this juncture.

Upon testing completion, Game Warden engineers deploy your application into PRD. This is a live environment, accessible to your users. The Game Warden team can deploy applications to IL4+, using additional security controls for higher levels of access.

After Game Warden engineers deploy your application into PRD, our Site Reliability Engineers (SREs) perform Day 2 activities to include monitoring your site to ensure stability. There are also Day 2 customer interactions. SREs use tooling to capture logs, monitor your applications, and send alerts. As a customer, you get our 24-hour incident response and help desk support with continuous monitoring and alerting.

## Platform Security
To ensure the Game Warden platform remains secure, our team uses third parties to validate the security built into this environment. In addition, the government examines our platform from an accreditation standpoint, and we also have a third-party company that performs routine penetration testing of our Game Warden environment.