# GPO-Management-Lab

Description

This project demonstrates the end-to-end implementation of a Windows Server 2022 Active Directory Domain Services (AD DS) environment. The primary objective was to architect a scalable organizational structure and deploy a suite of Group Policy Objects (GPOs) to enforce security, automate workflows, and standardize the user environment across an enterprise network.

### Core Implementation Phases
1. **Infrastructure Foundation:** Configured static IP addressing and internal DNS to ensure reliable domain communication.
2. **Domain Architecture:** Installed and promoted the Domain Controller role, establishing the `mydomain.com` namespace.
3. **Organizational Design:** Engineered a custom OU hierarchy to segment users and computers logically, allowing for granular policy targeting.
4. **Security & Automation Suite:** Developed and linked five critical GPOs:
    * **Password Policy:** Enforce complexity and rotation requirements.
    * **Drive Mapping:** Automate connection to shared department folders.
    * **Desktop Wallpaper:** Deploy standardized corporate branding.
    * **Restrict Control Panel:** Prevent unauthorized system configuration changes.
    * **Disable USB Storage:** Mitigate data exfiltration and malware risks.

### Technical Skills Demonstrated
* **Systems Administration:** Windows Server 2022, AD DS, DNS.
* **Security Engineering:** GPO Hardening, Least Privilege Access.
* **Network Management:** IPv4 Subnetting, Internal Routing.

* ### Infrastructure Visualization
#### GPO Hierarchy & Linking (Screenshot 03)
![GPO Hierarchy](03_GPO_Hierarchy.jpg)

#### User Targeting (Screenshot 04)
![User Targeting](04_User_Targeting.jpg)
