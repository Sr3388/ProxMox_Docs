# Proxmox_Docs

Proxmox HomeLab Docs


This repository documents my personal home lab, used for testing and learning. 

The Tech used includes Proxmox, pfSense, Ubuntu Server 26.04, VMs, Kubernetes (K3s), Ansible, Grafana, Prometheus, Portainer, Uptime Kuma, Pi-hole (local DNS) and Nginx (reverse proxy). 
It is used for system and networking experiments, and monitoring. 

Detailed Description:
---------------------

- 1° Headless Router/Firewall Server: 
   *	Router and firewall on pfSense 

- 2° Load Balancers: EliteDesk 800 G1 Mini
   *  HAProxy deployed across 2 VMs simulating 2 independent Load Balancers for High Availability and redundancy.

- 3° Headless Server: Lenovo ThinkCentre M710:
   *	Proxmox hypervisor (Node 1), VMs, 
   *	Ubuntu Server 26.05 (CLI only) running 
   *	Kubernetes (node 1) handling 
   *	Containers (Grafana, PiHole, Podman, Tailscale, Nginx, Portainer) 

- 4° Headless Server: Lenovo ThinkCentre M710: 
   *	Proxmox hypervisor (Node 2) with 
   *	Ubuntu Server 26 (CLI only) running 
   *	Kubernetes (node 2, for High Availability) handling 
   *	Containers and VMs

- 5° Headless Server: Lenovo ThinkCentre M910q: 
   *	Proxmox hypervisor (Node 3), with Containers & VMs
   *	Kubernetes (node 3, for High Availability)
 
- 6° Headless Server: Lenovo ThinkCentre M910q: 
   *	SOC / SIEM (Wazuh) monitoring pfSense and Proxmox.
   *	Next step will be to also monitor all Linux VMs, Kubernetes and Windows endpoints, with centralized security events, vulnerability detection and alerting.

- 7° Headless Server: HP EliteDesk 800 mini:  
   *	Jump host - Minimal Debian OS (Bookworm Security), hardened SSH, used to manage Proxmox, Kubernetes, managed switch and NAS.
     
- 8° Headless NAS Server: UGREEN   
   *	Currently on UGREEN proprietary SW (UGOS Pro), handling the NAS Storage.
   *	Next steps will be to replace Ugreen SW with TrueNAS
   *	This NAS is also used as a backup solution for my LXCs, VMs, and server data.

     
Hardware
--------

- 1° Fanless Headless 6 Gig, 6 port Ethernet Router/Firewall running pfSense  
- 2° Load Balancer: HP EliteDesk 800 G1 Mini: Intel i5, 8 GB RAM, 240 GB SSD   
- 3° Headless Server: Lenovo ThinkCentre M710: Intel i7, 16 GB RAM, 256 GB SSD
- 4° Headless Server: Lenovo ThinkCentre M710: Intel i7, 16 GB RAM, 256 GB SSD
- 5° Headless Server: Lenovo ThinkCentre M910q: Intel i7, 8 GB RAM, 240 GB SSD
- 6° Headless Server: Lenovo ThinkCentre M910q: Intel i7, 16 GB RAM, 512 GB SSD
- 7° Headless Server: HP EliteDesk 800 mini: Intel i5, 8 GB RAM, 240 GB SSD   
- 8° Headless NAS Server: UGREEN NASync DH2300: ARM proc. with 8 cores, 2.2 GHz, 4 GB RAM, 32 GB eMMC System storage, 2x SATA bays, 1x 1GbE port, USB-C
  
- Access Point: TP-Link TL-WA3001 AS3000Mbps (with multiple SSIDs mapped to separate VLANs & subnets)
- Primary managed switch: KeepLiNK 2.5Gb/s + 10 Gb/s SPF, provides VLAN segmentation, PoE, and Link Aggregation (LAG) for increased bandwidth and redundancy
- Secondary unmanaged switch: NICGIGA 8x 2.5G + 2x 10G SFP+ - Additional network ports for standard devices (no VLAN or aggregation) 
- NAS Storage: RAID 1 with 2x 4 TB HDDs
- Patch panel: For structured Ethernet cabling
- Two PDUs: Redundant power management and protection
- KVM: for shared monitor, mouse and keyboard across all the servers when directly connected

Software
--------

- Firewall and router OS: pfSense ver 2.9
- Load Balancers: HAProxy ver 3.4
- Proxmox VE: 3-node cluster across 3 physical hosts with High Availability (HA), quorum management and split-brain  prevention
- Multiple VMs: Ubuntu Server (CLI only), Win Server 2025, Mint Client, SUSE Server & Client, Fortinet Firewall (for tests), OPNsense (for tests)
- Multiple Containers on Docker and Kubernetes with Portainer
- Jump host: Debian Bookworm Security, no GUI, CLI only, with minimal install, SSH-hardened
- Network: Pi-hole (local DNS), Nginx (Reverse Proxy)
- Monitoring software: Grafana + Prometheus, Uptime Kuma



Also, see the included network diagram for the current setup. 



NB: This is a living project and will evolve over time.



 -- 26 Sept 2026 --
