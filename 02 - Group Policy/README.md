# Group Policy

## Overview

This section covers the core **Group Policy** administration tasks I completed within the **Windows Server 2022** lab. I created and managed **Group Policy Objects (GPOs)** to configure and enforce settings across the **Active Directory** domain. These tasks demonstrate how **Group Policy** simplifies centralised administration by allowing administrators to apply consistent configurations, security settings, and user policies throughout a **Windows Server** environment.

---

# Task 1 - Configuring a Password Policy

## Objective

Configure a **Password Policy** using **Group Policy** to enforce secure password requirements across the **Active Directory** domain.

---

## Implementation

I configured the **Default Domain Policy** within **Group Policy Management** to enforce password requirements for all domain users. Password policies help strengthen account security by defining settings such as password length, complexity, and password age, reducing the risk of weak or compromised credentials.

---

## Navigation

```text
Server Manager
→ Tools
→ Group Policy Management
→ Forest: lab.local
→ Domains
→ lab.local
→ Default Domain Policy
→ Edit
→ Computer Configuration
→ Policies
→ Windows Settings
→ Security Settings
→ Account Policies
→ Password Policy
```

---

## Outcome

The **Password Policy** was successfully configured within the **Default Domain Policy**, providing a centralised method of enforcing consistent password requirements across the **Active Directory** domain.

---

## Screenshot

**Figure 1:** Configuring the **Password Policy** within the **Default Domain Policy** using **Group Policy Management**.

![Figure 1](Images/Figure1-Password-Policy.png)
