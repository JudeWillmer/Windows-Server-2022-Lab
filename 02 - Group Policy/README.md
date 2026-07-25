# Group Policy

## Overview

This section covers the core **Group Policy** administration tasks I completed within the **Windows Server 2022** lab. I created and managed **Group Policy Objects (GPOs)** to configure and enforce settings across the **Active Directory** domain. These tasks demonstrate how **Group Policy** simplifies centralised administration by allowing administrators to apply consistent configurations, security settings, and user policies throughout a **Windows Server** environment.

---

# Task 1 - Configuring Password Policy Settings

## Objective

Configure **Password Policy** settings within the **Default Domain Policy** to enforce secure password requirements across the **Active Directory** domain.

---

## Implementation

I configured the **Password Policy** settings within the **Default Domain Policy** using **Group Policy Management**. These settings define password requirements such as password length, complexity, history, and password age, helping organisations enforce stronger authentication and improve domain security.

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

The **Password Policy** settings were successfully configured within the **Default Domain Policy**, providing a centralised method of enforcing consistent password requirements across the **Active Directory** domain.

---

## Screenshot

**Figure 1:** Configured **Password Policy** settings within the **Default Domain Policy** using **Group Policy Management**.

<img width="1517" height="887" alt="01 – Configuring Password Policy Settings" src="https://github.com/user-attachments/assets/d873a6e5-06fe-4be6-8fa2-b684a98e1c0c" />
