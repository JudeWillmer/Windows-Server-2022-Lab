# Troubleshooting

## Overview

This section covers the common troubleshooting tasks I completed within the **Windows Server 2022** lab. I diagnosed and resolved common **Active Directory**, **Group Policy**, **Shared Folder**, and **DNS** issues using built-in **Windows** administrative tools and command-line utilities. These tasks demonstrate practical troubleshooting techniques used to identify, investigate, and resolve common issues within a **Windows Server** environment.

---

# Task 1 - Unlocking a Locked Domain Account

## Objective

Simulate an **Active Directory** account lockout by entering an incorrect password multiple times, then restore access by unlocking the **domain user account** in **Active Directory Users and Computers**.

---

## Implementation

I entered an incorrect password multiple times while signing in as **LAB\katoch.m**, causing the configured **Account Lockout Policy** to lock the domain user account. I then opened **Active Directory Users and Computers**, located the **Mario Katoch** user account, and unlocked it from the **Account** tab within the user properties. After applying the changes, I signed in using the correct password and verified the successful domain authentication using the `whoami` command.

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

The locked **Active Directory** user account was successfully unlocked, restoring access to the **lab.local** domain. Successful authentication was verified by signing in with the **LAB\katoch.m** domain account and confirming the logged-in user using the `whoami` command.

---

## Scenario

A user contacts the IT Help Desk after being unable to sign in to their **domain account**. The account was automatically locked after multiple incorrect password attempts triggered the configured **Account Lockout Policy**. I investigated the issue by opening **Active Directory Users and Computers**, locating the affected user account, and confirming that the account was locked. I restored access by unlocking the account and then verified that the user could successfully authenticate to the **lab.local** domain using the correct credentials.

Account lockouts are one of the most common support requests within **Active Directory** environments. Understanding how to identify, resolve, and verify these issues enables IT Support professionals to restore user access quickly while maintaining the security controls enforced through **Group Policy**.

---

## Screenshot

**Figure 1:** Domain user account locked after multiple incorrect password attempts.

<img width="1917" height="952" alt="01 – Unlocking a Locked Domain Account" src="https://github.com/user-attachments/assets/e21d9148-69ef-476a-8797-11c9a8adde2f" />

**Figure 2:** Unlocking the locked domain user account in **Active Directory Users and Computers**.

<img width="1420" height="888" alt="02 – Unlocking a Locked Domain Account" src="https://github.com/user-attachments/assets/ee252108-8d3d-4f02-8e63-b1c0d44dcf08" />

**Figure 3:** Successful domain sign-in verified using the `whoami` command.

<img width="1231" height="911" alt="03 – Unlocking a Locked Domain Account" src="https://github.com/user-attachments/assets/3dbb9c8d-f800-4ca4-8411-2b37c5dee75a" />
