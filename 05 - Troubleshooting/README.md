# Troubleshooting

## Overview

This section covers the common troubleshooting tasks I completed within the **Windows Server 2022** lab. I diagnosed and resolved common **Active Directory**, **Group Policy**, **Shared Folder**, and **DNS** issues using built-in **Windows** administrative tools and command-line utilities. These tasks demonstrate practical troubleshooting techniques used to identify, investigate, and resolve common issues within a **Windows Server** environment.

# Task 1 - Unlocking a Locked Domain Account

## Objective

Simulate an **Active Directory** account lockout by entering an incorrect password multiple times, then restore access by unlocking the **domain user account** in **Active Directory Users and Computers**.

---

## Implementation

I intentionally entered an incorrect password multiple times while signing in as **LAB\katoch.m** until the configured **Account Lockout Policy** locked the account. I then opened **Active Directory Users and Computers**, located the **Mario Katoch** user account, and unlocked it from the **Account** tab within the user properties. Finally, I verified that the user could successfully sign in to the **lab.local** domain using the correct password.

---

## Navigation

```text
Server Manager
→ Tools
→ Active Directory Users and Computers
→ lab.local
→ Users
→ Mario Katoch
→ Properties
→ Account
→ Unlock account
→ Apply
→ OK
```

---

## Outcome

The locked **Active Directory** user account was successfully unlocked, restoring access to the **lab.local** domain. This demonstrates a common **Help Desk** troubleshooting procedure for resolving user account lockouts.

---

## Screenshot

**Figure 1:** Domain user account locked after multiple incorrect password attempts.

![Figure 1](Images/Task1-Figure1.png)

**Figure 2:** Unlocking the domain user account in **Active Directory Users and Computers**.

![Figure 2](Images/Task1-Figure2.png)

**Figure 3:** Successful domain sign-in after unlocking the user account.

![Figure 3](Images/Task1-Figure3.png)
