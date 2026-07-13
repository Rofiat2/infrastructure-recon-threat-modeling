Project Overview

This project is a documented walkthrough of an external security assessment. The goal was to safely map out an organization's public footprint, analyze open network services and build a Data Flow Diagram to find architectural risks. To protect data privacy, all real company names, domains, and IP addresses have been replaced with generic placeholders.
Step 1: Passive Reconnaissance
I used open source intelligence tools like theHarvester and assetfinder to collect public subdomains. This allowed me to map out the target's public facing attack surface without interacting directly with their servers.
Step 2: Active Scanning
After identifying the core hosting infrastructure, I used Nmap to run a service and version detection scan. This revealed an open HTTP/HTTPS gateway running an Nginx web server acting as a reverse proxy.
Step 3: Threat Modeling
Using the gathered data, I created a Data Flow Diagram to show how traffic travels from the public internet through the Nginx gateway into internal staging and payment environments.
Security Recommendations
1. Network Segmentation: Lock down staging and development environments so they are not accessible to the public internet.
2. Patch Management: Keep the Nginx gateway updated to the latest stable version to prevent known exploits.
3. Disable Server Tokens: Configure the web server to hide its exact version numbers from public view
