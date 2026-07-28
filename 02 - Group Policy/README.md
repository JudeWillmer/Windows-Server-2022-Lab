# Group Policy

## Overview

This section covers the core **Group Policy** administration tasks I completed within the **Windows Server 2022** lab. I configured and managed **Group Policy** settings within the **Default Domain Policy** to enforce security and user configuration settings across the **Active Directory** domain. These tasks demonstrate how **Group Policy** enables centralised administration by allowing administrators to apply consistent configurations and security settings throughout a **Windows Server** environment.

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

I configured the **Desktop Wallpaper** policy within the **Default Domain Policy** using **Group Policy Management**. The policy specifies a centrally managed wallpaper stored in a **network-accessible shared folder** on the server using a **UNC path**, allowing the desktop wallpaper to be applied automatically to domain users when Group Policy is refreshed.

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

The **Desktop Wallpaper** policy was successfully configured within the **Default Domain Policy**, enabling a consistent desktop wallpaper to be applied to domain users from a centrally managed shared location through **Group Policy**.

---

## Screenshot

**Figure 3:** Configured the **Desktop Wallpaper** policy within the **Default Domain Policy** using a network-accessible shared folder.

<img width="1721" height="892" alt="03 – Configuring a Desktop Wallpaper Policy" src="https://github.com/user-attachments/assets/9ae62bd2-3167-43d7-ad67-40f8f5f36f67" />

# Task 4 - Applying and Verifying Group Policy

## Objective

Apply the latest **Group Policy** settings and verify that the configured policies have been successfully processed by **Windows Server 2022**.

---

## Implementation

I used the **Command Prompt** to manually refresh **Group Policy** settings after configuring the policies within **Group Policy Management**. I then verified that the policies had been successfully applied by reviewing the **Resultant Set of Policy (RSoP)** information using the **gpresult** command.

---

## Commands

```cmd
gpupdate /force

gpresult /r
```

---

## Outcome

The **Group Policy** settings were successfully refreshed and verified. The **gpresult** output confirmed that the expected **Group Policy Objects (GPOs)** had been applied to the server.

---

## Screenshot

**Figure 4:** Applying and verifying **Group Policy** settings using **gpupdate** and **gpresult**.

<img width="1356" height="911" alt="04 – Applying and Verifying Group Policy" src="https://github.com/user-attachments/assets/7fcb4244-4cfc-45ab-804e-2829ce23c412" />
