# Proxmox_Docs

Proxmox HomeLab Docs


This repository documents my personal home lab, used for testing and learning. 

The Tech used includes Proxmox, pfSense, Ubuntu Server 26.04, VMs, K3s, Ansible, Grafana, Prometheus, Pi-hole, Portainer, and Uptime Kuma. 
It is used for system and networking experiments, and monitoring. 

Detailed Description:
---------------------

- 1° Headless Server: Lenovo ThinkCentre M910q 
   *	Proxmox hypervisor (Node 1), VMs, 
   *	Ubuntu Server 26.05 (CLI only) running 
   *	Kubernetes (node 1) handling 
   *	Containers (Grafana, PiHole, Podman, Tailscale, Nginx, Portainer) 

- 2° Headless Server: Lenovo ThinkCentre M710q: 
   *	Proxmox hypervisor (Node 2) with 
   *	Ubuntu Server 26 (CLI only) running 
   *	Kubernetes (node 2, for High Availability) handling 
   *	Containers and VMs

- 3° Headless Server: Lenovo ThinkCentre M910q: 
   *	Proxmox hypervisor (Node 3), with Containers & VMs
   *	Kubernetes (node 3, for High Availability)
 
- 4° Headless Server: Lenovo ThinkCentre M910q: 
   *	SOC / SIEM (Wazuh) monitoring pfSense, Proxmox, Linux, Kubernetes and Windows endpoints, with centralized security events, vulnerability detection and alerting.

- 5° Headless Router/Firewall Server: HP EliteDesk 800 mini:  
   *	Router and firewall on pfSense 

- 6° Headless NAS Server: UGREEN   
   *	Currently on UGREEN proprietary SW (UGOS Pro), handling the NAS Storage.
   *	Next steps will be to replace Ugreen SW with TrueNAS
     
Hardware
--------

- 1° Headless Server: Lenovo ThinkCentre M910q: Intel i7, 16 GB RAM, 256 GB SSD
- 2° Headless Server: Lenovo ThinkCentre M710q: Intel i5, 16 GB RAM, 240 GB SSD
- 3° Headless Server: Lenovo ThinkCentre M910q: Intel i7, 8 GB RAM, 240 GB SSD
- 3° Headless Server: Lenovo ThinkCentre M910q: Intel i7, 16 GB RAM, 256 GB SSD
- 5° Headless Router/Firewall Server: HP EliteDesk 800 mini: Intel i5, 8 GB RAM, 240 GB SSD
- 6° Headless NAS Server: UGREEN NASync DH2300: ARM proc. with 8 cores, 2.2 GHz, 4 GB RAM, 32 GB eMMC System storage, 2x SATA bays, 1x 1GbE port, USB-C
- NAS Storage: RAID 1 with 2x 4 TB HDDs
- Primary managed switch: 2.5Gb/s + 10 Gb/s SPF, provides VLAN segmentation, PoE, and Link Aggregation (LAG) for increased bandwidth and redundancy.
- Secondary unmanaged switch: additional network ports for standard devices (no VLAN or aggregation) 
- Dedicated wireless Access Point with multiple SSIDs mapped to separate VLANs & subnets.
- Patch panel: For structured Ethernet cabling
- Two PDUs: Redundant power management and protection
- KVM: for shared monitor, mouse and keyboard across all the servers when directly connected

Software
--------

- Proxmox VE: 3-node cluster across 3 physical hosts with High Availability (HA), quorum management and split-brain  prevention
- Multiple VMs: Ubuntu Server (CLI only), Win Server 2025, Mint Client, SUSE Server & Client, Fortinet Firewall (for tests), OPNsense (for tests)
- Multiple Containers on Docker and Kubernetes with Portainer
- Network: Pi-hole (local DNS), Nginx (Reverse Proxy)
- Monitoring software: Grafana + Prometheus, Uptime Kuma
- Firewall and router OS: pfSense ver 2.9


Also, see the included network diagram for the current setup. 



NB: This is a living project and will evolve over time.



 -- 24 Sept 2026 --
