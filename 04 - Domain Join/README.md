# Domain Join

## Overview

This section covers the core **Active Directory** domain administration tasks completed within the **Windows Server 2022** lab. A **Windows 10** client was joined to the **lab.local** domain, authentication was verified using a **domain user account**, and a **mapped network drive** was configured and accessed through **Active Directory**. These tasks demonstrate how **domain-joined computers** provide **centralised authentication** and **secure access** to shared network resources within a **Windows Server** environment.

---

# Task 1 - Joining a Windows 10 Client to the Domain

## Objective

Join a Windows 10 client to the **lab.local** Active Directory domain by renaming the computer, joining it to the domain, and verifying that the computer account is successfully created in Active Directory.

---

## Implementation

1. Open **This PC** and select **Properties**.
2. Select **Rename this PC (Advanced)**.
3. Rename the computer to **CLIENT01** and restart the device.
4. Open **System Properties**, select **Change**, then choose **Domain**.
5. Enter **lab.local** as the domain name.
6. Authenticate using a Domain Administrator account when prompted.
7. Restart the computer to complete the domain join.
8. Open **Active Directory Users and Computers** and verify that **CLIENT01** appears in the **Computers** container.

---

## Navigation

```text
This PC
→ Properties
→ Rename this PC (Advanced)
→ Change
→ Domain
→ Enter "lab.local"
→ Restart
```

---

## Outcome

The Windows 10 client was successfully joined to the **lab.local** Active Directory domain. After restarting, the computer account appeared in **Active Directory Users and Computers**, confirming the domain join was successful.

---

## Screenshot

**Figure 1:** **CLIENT01** successfully joined to the **lab.local** domain and displayed in the **Computers** container within **Active Directory Users and Computers**.

<img width="1212" height="892" alt="01 – Joining a Windows 10 Client to the Domain" src="https://github.com/user-attachments/assets/419c36c1-4626-4964-9f4f-05115baf5e76" />

# Task 2 - Signing in with a Domain User Account

## Objective

Sign in to the Windows 10 client using a domain user account and verify that the configured Group Policy password and account lockout policies have been successfully applied.

---

## Implementation

1. Sign out of the local Windows account.
2. Sign in using the **LAB\katoch.m** domain account.
3. Open **Command Prompt**.
4. Run the following command:

```cmd
net accounts
```

5. Review the output to verify that the configured password and account lockout policies have been applied.

---

## Navigation

```text
Start
→ User Account
→ Sign out

Sign in
→ LAB\katoch.m

Start
→ Command Prompt
→ net accounts
```

---

## Outcome

The Windows 10 client successfully authenticated using the **LAB\katoch.m** domain account. The `net accounts` command confirmed that the Group Policy password and account lockout settings configured earlier in the lab were successfully applied.

---

## Screenshot

**Figure 2:** Output of the `net accounts` command confirming that the Group Policy password and account lockout settings were successfully applied to the Windows 10 client.

<img width="1568" height="890" alt="02 – Signing in with a Domain User Account" src="https://github.com/user-attachments/assets/62c17df4-bc39-477e-8216-c83262048fbb" />

# Task 3 - Configuring and Verifying a Mapped Network Drive

## Objective

Configure a mapped network drive for a domain user through Active Directory and verify that the Sales department shared folder is automatically available after signing in.

---

## Implementation

1. Open **Active Directory Users and Computers**.
2. Navigate to **JayTech → Sales**.
3. Right-click **Mario Katoch** and select **Properties**.
4. Open the **Profile** tab.
5. Under **Home folder**, select **Connect** and choose drive letter **Z:**.
6. Open **File Explorer** and navigate to the **Sales** shared folder.
7. Right-click the **Sales** folder and select **Properties**.
8. Open the **Sharing** tab and copy the **Network Path**.
9. Return to the **Profile** tab for **Mario Katoch**.
10. Paste the network path into the **To:** field.
11. Select **Apply**, then **OK** to save the configuration.
12. Sign in to the Windows 10 client using the **LAB\katoch.m** domain account.
13. Open **This PC** and verify that the **Sales (Z:)** mapped network drive is automatically available.
14. Open the mapped drive to confirm that the Sales department shared folder is accessible.

---

## Navigation

```text
Active Directory Users and Computers
→ JayTech
→ Sales
→ Mario Katoch
→ Right-click
→ Properties
→ Profile
→ Connect
→ Z:

File Explorer
→ This PC
→ Local Disk (C:)
→ JayTech
→ Sales
→ Right-click
→ Properties
→ Sharing
→ Copy Network Path

Active Directory Users and Computers
→ Paste Network Path
→ Apply
→ OK

Windows 10
→ Sign in
→ LAB\katoch.m

File Explorer
→ This PC
→ Sales (Z:)
```

---

## Outcome

The Sales department shared folder was successfully assigned as a mapped **Z:** drive for the **LAB\katoch.m** domain account. After signing in, the Windows 10 client automatically mapped the network drive and successfully accessed the Sales department shared folder.

---

## Screenshot

**Figure 3:** The **Sales (Z:)** mapped network drive successfully connected and accessible from the Windows 10 client.

<img width="1918" height="915" alt="03 – Configuring and Verifying a Mapped Network Drive" src="https://github.com/user-attachments/assets/47e355bf-dbd0-454e-b19d-13ddf0c7038d" />
