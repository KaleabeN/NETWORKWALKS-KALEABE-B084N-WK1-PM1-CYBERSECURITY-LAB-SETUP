# NETWORKWALKS-KALEABE-B084N-WK1-PM1-CYBERSECURITY-LAB-SETUP

# Cybersecurity Testing Lab Environment Setup (Week 1)

## Overview
This repository documents the step-by-step setup and configuration of a virtualized cybersecurity testing lab. The primary objective for Week 1 was to establish a isolated virtual environment and deploy **Kali Linux** as the primary attacking/penetration testing node.

---

## Technical Specifications & Architecture

* **Host System**: Windows 11 Pro
* **Hypervisor**: VMware Workstation Pro *(Migrated from Oracle VM VirtualBox)*
* **Guest OS**: Kali Linux
* **Network Type**: Custom NAT Network
* **Subnet**: `10.0.0.0/24`
* **Kali Linux IP Configuration**: Static IP `10.0.0.2/24`

---

## Lab Setup & Migration Notes

> **Hypervisor Migration Note**: 
> While Oracle VM VirtualBox was initially specified as the target base hypervisor, compatibility and performance issues encountered on **Windows 11 Pro** necessitated a migration to **VMware Workstation Pro (Latest Version)**. VMware Pro provides enhanced hardware virtualization support and improved stability for the Kali Linux virtual guest on this Windows 11 host.

---

## Step-by-Step Implementation

### Step 1: System Prerequisite Check
* Verified pre-installed utilities, including file archive management (**7-Zip**), on the host machine.

### Step 2: Hypervisor Installation
* Selected and deployed **VMware Workstation Pro** as the core virtualization software on Windows 11 Pro.

### Step 3: Virtual Network Configuration
* Configured a custom Virtual NAT Network within VMware with the target CIDR block:
  * **Network Subnet**: `10.0.0.0/24`
  * Configured isolated network parameters to allow proper NAT traversal for lab tasks while maintaining host safety.
![IP Configuration and NAT Network](<IP config and NAT Network.png>)
### Step 4: Kali Linux Deployment & Configuration
* Imported and set up the **Kali Linux** virtual appliance.
* Adjustments made to network adapters to align with the `10.0.0.0/24` NAT subnet.
* Configured static IP address for the Kali Linux instance:
  * **IP Address**: `10.0.0.2`
  * **Subnet Mask**: `255.255.255.0` (`/24`)

### Step 5: Testing & State Persistence
* Verified network connectivity and functionality of the Kali environment.
* Created initial VM **snapshots** within VMware to establish a clean restore baseline for future offensive and defensive testing modules.

* Configured snapshots to ensure clean restore baselines for future testing modules.

![VMware Snapshot Menu](<vm-ware snapshot.png>)

![VMware Snapshot Manager](<Snapshot manager.png>)

---

## Verification
- [x] Hypervisor functional on Windows 11 Pro.
- [x] NAT network subnet (`10.0.0.0/24`) established.
- [x] Kali Linux guest operational with IP `10.0.0.2/24`.
- [x] Baseline snapshot generated for system state recovery.
