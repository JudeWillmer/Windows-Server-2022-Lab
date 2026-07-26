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

# Task 2 - Configuring Account Lockout Policy Settings

## Objective

Configure **Account Lockout Policy** settings within the **Default Domain Policy** to help protect the **Active Directory** domain against repeated failed sign-in attempts.

---

## Implementation

I configured the **Account Lockout Policy** settings within the **Default Domain Policy** using **Group Policy Management**. These settings determine how many failed sign-in attempts are permitted before an account is locked, how long the account remains locked, and when the failed sign-in counter is reset. This helps reduce the risk of brute-force password attacks while improving domain security.

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
→ Account Lockout Policy
```

---

## Outcome

The **Account Lockout Policy** settings were successfully configured within the **Default Domain Policy**, helping to protect user accounts by automatically locking them after multiple failed sign-in attempts.

---

## Screenshot

**Figure 2:** Configured **Account Lockout Policy** settings within the **Default Domain Policy** using **Group Policy Management**.

<img width="1342" height="888" alt="02 – Configuring Account Lockout Policy Settings" src="https://github.com/user-attachments/assets/1b1890ad-a2cf-4b2e-b98e-d585a107b92f" />

# Task 3 - Configuring a Desktop Wallpaper Policy

## Objective

Configure a **Group Policy** setting to apply a standard desktop wallpaper for domain users, demonstrating centralised desktop configuration using **Group Policy Management**.

---

## Implementation

I configured the **Desktop Wallpaper** policy within the **Default Domain Policy** using **Group Policy Management**. The policy specifies a centrally managed wallpaper stored on the server and applies it automatically to users when the policy is updated, helping maintain a consistent desktop appearance across the organisation.

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
→ User Configuration
→ Policies
→ Administrative Templates
→ Desktop
→ Desktop
→ Desktop Wallpaper
```

---

## Outcome

The **Desktop Wallpaper** policy was successfully configured within the **Default Domain Policy**, allowing a consistent desktop wallpaper to be applied to domain users through **Group Policy**.

---

## Screenshot

**Figure 3:** Configured the **Desktop Wallpaper** policy within the **Default Domain Policy** using **Group Policy Management**.

<img width="1705" height="892" alt="03 – Configuring a Desktop Wallpaper Policy" src="https://github.com/user-attachments/assets/e3568077-6bb0-494b-9963-ec05a47f459f" />
