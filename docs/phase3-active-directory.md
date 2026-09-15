# Phase 3 — Active Directory & Domain

**Goal:** install Active Directory on the server, promote it to a Domain
Controller, and join the target machine to the new domain.

First confirm connectivity between machines (`ping 192.168.10.10`).

## Promote the server to a Domain Controller (ADDC01)

1. **Server Manager → Manage → Add Roles and Features** → Role-based install →
   select **Active Directory Domain Services** → add features → install.
2. Click the notification flag → **Promote this server to a domain controller**.
3. Choose **Add a new forest**, root domain name **`sujal.local`**, set a
   Directory Services Restore Mode password, and finish. The server reboots.

## Create OUs and users

**Server Manager → Tools → Active Directory Users and Computers**, expand the
domain:

- Create an OU named **IT** → new user:
  Jenny Smith, login `jsmith`. Set a password and uncheck *"user must change
  password at next logon"*.
- Create an OU named **HR** → new user:
  Terry Smith, login `tsmith`. Same password options.

Active Directory is now set up and the server is a Domain Controller.

## Join the target machine to the domain

1. On the target: **This PC → Properties → Advanced system settings →
   Computer Name → Change** → select **Domain** → enter `sujal.local`.
   *(An error is expected here — leave the window open.)*
2. Fix DNS: **Network adapter → Open Network & Internet settings → Change adapter
   options → Ethernet → Properties → IPv4** → set DNS to **192.168.10.7**
   (the DC).
3. Verify with:
   ```cmd
   ipconfig /all
   ```
4. Retry the domain join, authenticate with the server's **administrator**
   account, and reboot.
5. At the login screen, choose **Other user**, ensure *Sign in to* is
   `sujal.local`, and log in as **jsmith**.

The machine is now joined to the `sujal.local` domain and can log in as a
domain user.

---
➡️ Continue to [Phase 4 — Attack & Detection](phase4-attack-and-detection.md)
