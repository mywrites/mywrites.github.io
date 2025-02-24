---
layout: default
title: "General Requirements"
category: "Cybersecurity"
---
You must satisfy general requirements referenced in the table below. Ensure you comply with these specifications prior to contacting the Game Warden team.

| **Requirements**                            | **Details**                                        |
| ---------------------------------------------| --------------------------------------------------|
| **You must** [Create a P1 SSO account](https://helpcenter.gamewarden.io/integrations-access/goverment_access_cards/p1_sso/).            | Platform One (P1), a Department of Defense (DoD) analogue or counterpart to Game Warden, is a DevSecOps platform that delivers applications to the government. P1 contains DoD-approved tooling for software development. Game Warden integrates with P1 and, in so doing, has access to the P1 DoD-approved tooling for software development along with solutions available via P1, such as Big Bang and Iron Bank. | 
| **You must use Appgate SDP, conditionally**.     | Customers who do not access IL4+ via Non-classified Internet Protocol Router Network (NIPRNet) or NIPRNet VPN (such as Air Force Desktop Anywhere) must use Appgate SDP to access these environments. During this access, Appgate SDP must remain open and active. Provisioning a P1 SSO account is a mandatory prerequisite for Appgate Software-Defined Perimeter (SDP) use, as there is a dependency between Appgate SDP and P1 SSO. Appgate SDP is a DoD-approved authentication service. |
| **You must use a Windows or Mac machine when downloading your digital certificate via** [IdenTrust](https://www.identrust.com/digital-certificates/dod-eca-programs). | If you are using [IdenTrust](https://www.identrust.com/digital-certificates/dod-eca-programs) as your provider of digital certificates and managed PKI services – as opposed to using a CAC – you cannot use Linux/Ubuntu when attempting to download your digital certificate. These systems are not supported and might trigger compatibility issues. IdenTrust recommends MS Windows and Apple Mac machines. For Windows, IdenTrust recommends the MS Edge and Google Chrome browsers. For Macs, IdenTrust recommends Mozilla Firefox. You should also use the latest browser versions. For additional information, read [IdenTrust Certificate Compatibility](https://www.identrust.com/ca-certificate-compatibility). | 
| **To deploy to the IL4+ Staging (STG) and Production (PRD) environments, you must have a government contract**. | You must maintain an active DoD contract to deploy into IL4 or IL5 (CUI). Only CAC/ECA/PIV card holders may access Game Warden in sensitive data classifications. |
| **Applications will be associated with the .mil domain**. | All applications will deploy under the Game Warden afwerx.dso.mil domain. |

# Guidance
The Game Warden team will work with you to ensure your product aligns with these general requirements and, going forward, provide any necessary insight to help you. Contact us at [Growth](mailto:growth@secondfront.com) for additional information.

<style>
  table {
    width: 100%;
    border-collapse: collapse;
  }
  th, td {
    border: 1px solid black;
    padding: 8px;
    text-align: left;
  }
</style>
