# Phase 1 — Building the Lab

**Goal:** provision the four virtual machines that make up the lab.

## Steps

1. Install **VirtualBox**.
2. Download and configure **Windows 10 (22H2)** as a VM — this becomes the target endpoint.
3. Download the **Kali Linux** prebuilt VM, extract it, and double-click the `.vbox` file to import it automatically.
4. Download the **Windows Server 2022** ISO (64-bit) and install it — this becomes the domain controller.
5. Install **Ubuntu Server** as a VM — this hosts Splunk.

At the end of this phase all four VMs exist but are not yet networked together. That happens in Phase 2.

---
➡️ Continue to [Phase 2 — Splunk & Sysmon](phase2-splunk-sysmon.md)
