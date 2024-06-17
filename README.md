# Windows Defender & Windows Defender Firewall 
## Project Goal: 
Understanding and Adjusting the Windows Defender Virus scans and Firewall 
## Scenario 
Configure the Firewall to Block Windows Remote Management on the Public Network

# Setup information 
To access the Windows Defender Anti-Virus and Firewall settings we must: 

1. Open Settings: Start menu > Settings (gear icon) or press Win + I.

2. Navigate to Privacy & Security: Click on " Virus & Threat Protection" for Windows Defender Anti-Virus OR click on Firewall & Network Protection for Windows Defender Firewall
   
# Windows Defender Anti-Virus

It is vital to make sure everything is up-to-date and to regularly scan your computer for potential compromises. 

Updating the Virus & Threat Protection allows Windows Defender to have up-to-date information on Virus Definitions, thus allowing it to detect any of the known definitions. 

![Screenshot 2024-06-06 at 5 27 02 PM](https://github.com/SteveSunny46/Windows-Defender-Firewall/assets/171859383/b3e540f1-9fa2-4c0b-9118-b8f5e84c4f1d)

Additionally, you can perform different types of scans:

- Quick Scans: Quickly check the most vulnerable areas of your computer.
- Full Scans: Thoroughly scan the entire computer for threats.
- Custom Scans: Scan specific sections or folders of the computer as needed.

In the screenshot below, we demonstrate how a custom scan works. We chose to scan all programs and files located on the desktop. Since this virtual machine contains few folders, the scan quickly completed and confirmed that no threats were found in this section.
![Screenshot 2024-06-06 at 5 31 49 PM](https://github.com/SteveSunny46/Windows-Defender-Firewall/assets/171859383/6f239fe5-785c-4250-b1cb-deea9d019c5b)


# Windows Defender Firewall 

Over here we can see the network profiles (Domain, Private, Public)

### •  Public Network Setting: 

Typically used in places like coffee shops or libraries where many people connect. Devices on a public network are isolated from each other for security reasons. This means devices cannot communicate or see each other directly, which helps protect individual users' privacy and security.

### • Private Network Setting: 

Commonly used in home environments. All devices connected to the same private network (e.g., home Wi-Fi) can communicate with each other freely. This setup allows the sharing of resources such as printers, files, and media among devices within the network.

### •  Domain Network Setting: 

Found in workplace environments managed by IT departments. Computers in a domain network are centrally managed and configured to be part of a domain, which allows seamless communication and access to shared resources like printers, files, and servers within the domain. This setup provides enhanced security, organization, and administrative control over network resources in a professional setting.

![image](https://github.com/SteveSunny46/Windows-Defender-Firewall/assets/171859383/e1fd720f-23ef-427f-ba21-5c7ecf73f40a)

## Step 1: Adjusting the Public Network Setting
For this scenario, we must move to the advanced settings within the Public Network 

<img width="468" alt="firewall pic" src="https://github.com/SteveSunny46/Windows-Defender-Firewall/assets/171859383/72195ea7-d31b-4314-8e5f-b13da3c11f1e">


Here we will see many advanced inbound and outbound rules for this specified setting and find the Windows Remote Management rule

•	Inbound rules: Inbound rules determine what traffic is allowed to the computer.

•	Outbound rules: Outbound rules determine what traffic is allowed to leave the computer. 

<img width="412" alt="image" src="https://github.com/SteveSunny46/Windows-Defender-Firewall/assets/171859383/cc3021df-7c4a-4d39-b445-6bc3584783f9">

## Step 2: Find and configure the Firewall Rule

Since we do not want Windows Remote Management to our computer we will look for "Windows Remote Management" within the Inbound rules and double click it and block the connection. 

<img width="412" alt="Picture1" src="https://github.com/SteveSunny46/Windows-Defender-Firewall/assets/171859383/e5c56136-e689-4646-bb40-664964af665a">

It is important to make sure we are on the Public network settings. To do this we will click on advanced and confirm only Public is checked. 

Once we are set, we can confirm and apply this rule. 

![2](https://github.com/SteveSunny46/Windows-Defender-Firewall/assets/171859383/94bd1b8f-0961-458d-ae3f-ec072603389a)

## Step 3: Confirmation 

We will now see a block symbol beside the Public network setting profile we just adjusted. 

If there is no block symbol after configuring this rule, we just have to press the button located above cut on the right saying "Enable". Now the task is complete!
(In the picture it says "Disable" as the rule is already active)

<img width="412" alt="image" src="https://github.com/SteveSunny46/Windows-Defender-Firewall/assets/171859383/759ece90-902c-4f78-bfd2-1f8ce2e6549b">









