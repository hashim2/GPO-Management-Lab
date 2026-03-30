# 🖥️ GPO Management Lab

## Overview

End-to-end implementation of a Windows Server 2022 Active Directory Domain
Services (AD DS) environment. Focused on building a scalable OU structure
and deploying Group Policy Objects (GPOs) to enforce security, automate
workflows, and standardize the user environment.

---

## 🧰 Lab Environment

| Field | Value |
|---|---|
| **OS** | Windows Server 2022 |
| **Domain** | mydomain.com |
| **Role** | Domain Controller (AD DS, DNS) |
| **Certifications** | CompTIA A+ |

---

## 🔧 Implementation Phases

**1. Infrastructure Foundation**
Configured static IP addressing and internal DNS to ensure reliable domain
communication.

**2. Domain Architecture**
Installed and promoted the Domain Controller role, establishing the
`mydomain.com` namespace.

**3. Organizational Design**
Built a custom OU hierarchy to segment users and computers logically,
enabling granular policy targeting.

**4. GPO Deployment**
Developed and linked five Group Policy Objects:

| GPO | Purpose |
|---|---|
| Password Policy | Enforce complexity and rotation requirements |
| Drive Mapping | Automate connection to shared department folders |
| Desktop Wallpaper | Deploy standardized corporate branding |
| Restrict Control Panel | Prevent unauthorized system configuration changes |
| Disable USB Storage | Mitigate data exfiltration and malware risks |

---

## 📸 Lab Walkthrough

### 1. GPO Infrastructure & OU Hierarchy

<img width="1021" alt="Active Directory Hierarchy and GPO Linking" src="https://github.com/user-attachments/assets/91b751a4-00c5-47d3-ae63-267c8c283de6" />

Designed a custom OU hierarchy separating `_ADMINS`, `_USERS`, and
policy-specific containers. Five GPOs were created and linked to their
respective OUs, ensuring settings apply only to targeted groups through
GPO inheritance.

---

### 2. User Targeting via Security Filtering

<img width="1030" alt="GPO Security Filtering" src="https://github.com/user-attachments/assets/793aacbc-95e2-43fb-a12c-e2a14e49b067" />

Used Security Filtering in GPMC to scope the Password Policy GPO to a
specific user (`MYDOMAIN\hsufi`). This reflects real-world practice of
testing policies on pilot users before domain-wide rollout.

---

### 3. GPO Validation via gpresult

<img width="1026" alt="Applied GPO Proof" src="https://github.com/user-attachments/assets/9224e3b8-89fa-41b9-baee-8edcd9030039" />

Ran `gpresult /r` on the Client VM to confirm successful policy propagation.
Output confirmed that Desktop Wallpaper, Drive Mapping, and Restrict Control
Panel GPOs were all applied under the client's user context.

---

### 4. Functional Verification — Control Panel Lockdown

<img width="1021" alt="Restrict Control Panel GPO Proof" src="https://github.com/user-attachments/assets/69e98d61-3f05-4391-beaf-df8bad0335ff" />

Attempted to access system settings on the Client VM as a standard user.
The OS blocked the request with a Restrictions dialogue, confirming the
GPO is active. The black desktop indicates a UNC pathing issue for the
wallpaper — in production this would be resolved by verifying NTFS
permissions on the shared folder.

---

## 🛠️ Skills Demonstrated

- Windows Server 2022 administration (AD DS, DNS)
- GPO creation, linking, and inheritance management
- Security filtering for granular policy targeting
- IPv4 subnetting and internal network routing
- Policy validation using `gpresult`
- Troubleshooting real-world GPO deployment issues

