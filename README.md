# 🌐 Azure Virtual Network Traffic Analysis — Portfolio Lab

## 📌 Overview
Hands-on lab to deploy **Windows + Ubuntu VMs in Azure**, capture traffic with **Wireshark**, and verify how **Network Security Group (NSG)** rules affect connectivity. Built to be **recruiter-friendly** and **evidence-driven**.

## 🎯 Objectives
- Deploy core Azure resources (RG, VNet/Subnet, VMs)
- Capture & analyze **ICMP, SSH, DHCP, DNS, RDP** traffic in Wireshark
- Prove how NSG firewall rules impact traffic flow
- Document reproducible steps and **evidence screenshots**

## 🛠️ Tools & Tech
- **Azure**: Resource Groups, VNets, Subnets, Network Security Groups (NSG), Network Watcher  
- **OS**: Windows 10 VM (Wireshark host), Ubuntu VM (target)  
- **Protocols**: ICMP, SSH, DHCP, DNS, RDP  
- **Access**: RDP (Windows), SSH (Linux)

---

## ✅ Lab Checklist
- [ ] Create Resource Group (RG)
- [ ] Create VNet + Subnet
- [ ] Deploy Windows 10 VM (Wireshark host)
- [ ] Deploy Ubuntu VM (target)
- [ ] Confirm both VMs share the same VNet/Subnet (Network Watcher)
- [ ] RDP into Windows VM
- [ ] Install Wireshark
- [ ] Observe **ICMP** traffic (allow → block via NSG → allow)
- [ ] Observe **SSH** traffic (Windows → Ubuntu)
- [ ] Observe **DHCP** DORA after `ipconfig /renew`
- [ ] Observe **DNS** lookups via `nslookup`
- [ ] Observe **RDP** continuous stream
- [ ] Cleanup: delete Resource Group

---

## 📷 Evidence / Screenshots (placeholders + guidance)

> Place images in `./screenshots/` and number them so the story flows in order.

### 01 — Resource Group Created
![RG Created](./screenshots/01-resource-group.png)  
**What to capture:** Azure Portal > Resource groups > summary.  
**Why:** Proves environment isolation and cleanup readiness.  

### 02 — VNet & Subnet Summary
![VNet Summary](./screenshots/02-vnet-subnet.png)  
**What to capture:** VNet address space + Subnet range.  
**Why:** Shows private IP design for VM-to-VM traffic.  

### 03 — Windows VM Deployed
![Windows VM](./screenshots/03-windows-vm.png)  
**What to capture:** VM overview (NIC, VNet/Subnet, private IP).  
**Why:** Confirms Wireshark host.  

### 04 — Ubuntu VM Deployed
![Ubuntu VM](./screenshots/04-ubuntu-vm.png)  
**What to capture:** VM overview.  
**Why:** Confirms ICMP/SSH target.  

### 05 — RDP Session
![RDP Session](./screenshots/05-rdp-session.png)  
**What to capture:** Windows VM desktop via RDP.  
**Why:** Evidence analysis happens inside VM.  

### 06 — Wireshark Installed
![Wireshark Installed](./screenshots/06-wireshark-installed.png)  
**What to capture:** Wireshark open/about screen.  
**Why:** Proof of tool readiness.  

### 07 — ICMP Allowed (Ping OK)
![ICMP Allowed](./screenshots/07-icmp-allow.png)  
**What to capture:** Wireshark ICMP filter + successful ping.  
**Why:** Baseline connectivity.  

### 08 — NSG Rule Blocking ICMP
![NSG Deny ICMP](./screenshots/08-nsg-deny-icmp.png)  
**What to capture:** NSG inbound rule (deny ICMP).  
**Why:** Shows applied firewall control.  

### 09 — ICMP Blocked
![ICMP Blocked](./screenshots/09-icmp-blocked.png)  
**What to capture:** Wireshark ICMP with requests only.  
**Why:** Evidence of traffic drop.  

### 10 — ICMP Restored
![ICMP Restored](./screenshots/10-icmp-restored.png)  
**What to capture:** Replies return after NSG rule removed.  
**Why:** Confirms rollback.  

### 11 — SSH Session
![SSH Session](./screenshots/11-ssh-session.png)  
**What to capture:** SSH into Ubuntu + Wireshark SSH traffic.  
**Why:** Validates east-west encrypted traffic.  

### 12 — DHCP Renewal
![DHCP DORA](./screenshots/12-dhcp-dora.png)  
**What to capture:** `ipconfig /renew` + Wireshark DHCP DORA sequence.  
**Why:** Confirms dynamic IP assignment.  

### 13 — DNS Queries
![DNS Queries](./screenshots/13-dns-queries.png)  
**What to capture:** nslookup google.com/disney.com + Wireshark DNS.  
**Why:** Shows name resolution.  

### 14 — RDP Stream
![RDP Stream](./screenshots/14-rdp-traffic.png)  
**What to capture:** Wireshark tcp.port==3389 traffic.  
**Why:** Explains constant stream behavior.  

### 15 — Cleanup Confirmation
![RG Deleted](./screenshots/15-cleanup.png)  
**What to capture:** Resource Group deletion complete.  
**Why:** Proves environment cleanup.  

---


## 🔗 Reproduction Steps
See **[IMPLEMENTATION.md](./IMPLEMENTATION.md)** for exact Azure CLI, PowerShell, and Wireshark filters.

## 🧠 Key Takeaways
- Safe cloud deployment + teardown  
- Captured & interpreted 5 protocols in Wireshark  
- Tested NSG firewall rules with evidence  
- Practiced troubleshooting: symptom → capture → fix


