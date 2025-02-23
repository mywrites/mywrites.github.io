---
layout: default
title: "Harbor Overview"
category: "Cybersecurity"
---

The Game Warden team uses Harbor as its secure image registry. As an open source and feature-rich registry, Harbor manages the images you push into this environment. Our Continuous Integration/Continuous Deployment (CI/CD) pipelines move your images through the scanning and hardening processes. The Game Warden team uses Anchore Enterprise and Prisma Cloud to both scan/harden images and identify vulnerabilities.

The team also uses ClamAV for malware detection. As your images navigate the scanning and hardening processes, tags are appended to the end of your image names to designate the status of each.

You might use varying methods to push images into Harbor. This article focuses on pushing images manually and, more specifically, from a terminal using Docker commands.

Alternatively, if you are using an automated pipeline process, please contact our Customer Operations team. They can provide *robot credentials* to facilitate this process. Time-defined and commonly distributed for short-term use, robot credentials prevent Harbor session expiration. If you are not using an automated pipeline process, your Harbor session can expire. For example, if you access Harbor in the morning then attempt to push an image into this environment in the afternoon, a Harbor session *timeout* might occur. This scenario will *trigger a failure to authenticate* message in your terminal. If your Docker command login credentials (into Harbor) *fail to authenticate*, simply re-enter these credentials – accessing Harbor from a web browser.

**NOTE**
When you use unmodified Iron Bank images in your deployment, the Game Warden team will pull these images directly into our infrastructure (as opposed to you pushing them).

# Prerequisites
1.	Create a [Platform One (P1) Single Sign-On (SSO)](https://helpcenter.gamewarden.io/integrations-access/platform_one/) account.
1.	Ensure you have authorization to push images into Harbor on behalf of your company. You must provide our Customer Operations team with a list containing the **Username** and **Email Address** for each authorized user.
Harbor Access¶
1.	Navigate to [Harbor](https://registry.gamewarden.io/account/sign-in?redirect_url=%2Fharbor%2Fprojects).
1.	Click **Login via OICD Provider** then click **Login with P1 SSO**, entering your P1 SSO login credentials. <br/>
   The **Projects** page opens, displaying a table.
   ![Harbor](/img/harbor1.png)

1. Click to select your project. (Contact our Customer Operations team via Slack if your project is unavailable for selection.)
   A new page opens, defaulting to the **Repositories** tab.

   ![Harbor](/img/harbor2.png)

**NOTE** 
This page (middle right) displays **PUSH COMMAND**. Select this option to open a modal and view the required terminal syntax for Docker push commands. The information in this modal serves as a mere guide to assist you with syntax. You can use the **Tag an image for this project** and **Push an image to this project** syntax, copying each line from this modal for ease of use.

## Harbor Credentials
1. Select your P1 account name (top right of **Projects** page) and, from the drop-down list box, click **User Profile**.

   The **User Profile** modal opens, displaying several fields to include the last entry **CLI secret**. A **Copy** icon (overlapping squares) appears at the end of this field.

   ![Harbor](/img/harbor3.png)

1. Retrieve your **CLI secret** by clicking the **Copy** icon.

   A banner opens at the top of the **User Profile** modal and contains the text, copy success.
1. Record the text in the **Username** field, as you will need this information in a subsequent step.

   The copied **CLI secret** remains in your clipboard.
1. Click **CANCEL** to close the **User Profile** modal.




