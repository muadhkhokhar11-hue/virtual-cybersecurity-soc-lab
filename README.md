# Wazuh-SIEM-Active-Directory-SOC-Lab
A hands-on, work-in-progress cybersecurity laboratory hosted in VMware Workstation Pro. Features an enterprise Wazuh SIEM deployment for real-time log ingestion and a Kali Linux node for isolated attack simulations.
## ⚠️ Project Status: WORK IN PROGRESS (Active Deployment)
This repository tracks the real-time development, configuration, and architectural implementation of my home cybersecurity laboratory. The project is being deployed in phased milestones to bridge theoretical network security with hands-on systems engineering.
## 🛠️ What I Have Completed So Far (Current Milestones)

1. Setting Up the Virtual Machines
Using VMware: I set up a virtual lab environment on my laptop using VMware Workstation Pro to act like a real corporate network.

The Machines: I created and booted up three different virtual machines:

A Wazuh Server running on Linux to act as my central security manager.

A Windows Server 2022 machine to act as my main domain controller.

A Kali Linux machine that I will use later to run fake cyber attacks.

2. Getting the SIEM Dashboard Online
Wazuh Installed: I successfully got the main Wazuh security platform up and running.

Web UI Working: I fixed the network settings so I can actually open my web browser on my regular computer, type in the server's IP address (192.168.1.11), and log into the security dashboard.

3. Fixing the Network Connections
Bridged Network: I switched the virtual machines over to a "Bridged" network connection. This makes them talk directly to my home router so they can get their own IP addresses automatically.

Testing Pings: I tested the connection in the Windows command line, and the machines are successfully talking to each other with a 100% perfect ping and no lost data.

## ⚠️ Challenges I Faced & Current Problems I'm Stuck On
Building a lab from scratch means breaking a lot of things. Here are the issues I've run into and how I'm trying to fix them:

1. The Capital Letter Bug (Linux Command Error)
The Problem: While trying to restart my Linux network card from the terminal, I accidentally added an extra capital letter to the command (typing networkingS.service instead of the right name).

What I Learned: Linux completely broke and threw an error. It taught me that Linux is super picky about exact spelling and lowercase letters, so I had to learn how to use visual network tools like nmtui instead.

2. The Unreachable Website Mess
The Problem: I tried switching the lab over to a private "Host-Only" network to isolate it, but the Wazuh server immediately lost its identity. The whole website crashed, and my browser couldn't load the security page anymore.

How I Fixed It: I changed the settings back to a Bridged network, which immediately brought the website back to life.

3. Where I am Currently Stuck: No Internet on Windows Server
The Current Problem: This is what I am actively troubleshooting right now. Even though my Windows Server machine can ping my Wazuh server perfectly, it has completely lost its connection to the outside internet.

Why this blocks me: Because Windows can't reach the internet, when I paste the PowerShell command to download the Wazuh monitoring agent, it fails and says:

The remote name could not be resolved: 'packages.wazuh.com'

My Next Steps: I am currently trying to reset the Windows virtual network card using commands like ipconfig /release and ipconfig /renew so it grabs internet access from my router without losing its connection to my security manager.
