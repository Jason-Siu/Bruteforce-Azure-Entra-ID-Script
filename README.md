# Bruteforce-Azure-Entra-ID-Script

## Overview
This PowerShell script is designed to simulate a brute force attack against an Azure Entra ID (formerly known as Azure Active Directory) account. It intentionally tries 11 incorrect password attempts before submitting the correct password on the final attempt. The purpose of this script is to showcase an incident scenario in Azure and demonstrate successful login via PowerShell.

For privacy purposes, I will be marking out my tenant ID and password to the account. 

We can verify this by checking our custom made incidents inside of Micosoft Sentinel (SIEM).

## Features
 - Brute Force Simulation: The script performs a brute force attack by attempting multiple password combinations.
 - Smart Lockout Bypass: It bypasses Azure AD Smart Lockout, allowing for repeated login attempts without being blocked.
 - Ethical Hacking: Useful for ethical hacking scenarios where typical pentesting tools (e.g., Kali Linux) are unavailable.

## Implementation
I used an attacker virtual machine located in India. To create this, I simply just created a new VM from within Azure to use. The Attacker VM's IP address is 98.70.13.69, which will be shown inside of Microsoft Sentinel, which is our SIEM.

Upon running the script multiple times, we can observe the incidents occurred here:
![image](https://github.com/Jason-Siu/Bruteforce-Azure-Entra-ID-Script/assets/34889726/29953e80-384d-4db7-9ba1-c4b071541764)

Additionally, we can manually insert the KQL incident code into our workspace for details:
![image](https://github.com/Jason-Siu/Bruteforce-Azure-Entra-ID-Script/assets/34889726/c8b80a87-0dec-4ba8-b093-e892d8173f14)

As you can see in the image above, the only successful bruteforce attempts were done from our attacker VM and not any other entity. However, a lot more entities attempted to brute force, just none were successful.

## Threat Map
And our threat map would appear as:

![image](https://github.com/Jason-Siu/Bruteforce-Azure-Entra-ID-Script/assets/34889726/cdac1cb0-bc9e-4786-8926-dcebe4750a3b)

## Conclusion
In conclusion, this Azure AD Brute Force Script serves as a powerful demonstration of the security vulnerabilities that can exist within an organization’s authentication systems. By intentionally attempting incorrect passwords before successfully logging in, it highlights the importance of robust security measures and the need for continuous monitoring and improvement.

