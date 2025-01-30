# Active-Directory
My process of setting up an active directory for my VM home lab

# Objectives
- Setting up a concept diagram of my network
  
 ![image](https://github.com/user-attachments/assets/992458d8-4dfa-45fd-b273-a6772e94489d)

  
- setting up active directory for my VM's
- gaining a deeper understanding of how active directory work in general
  
# tools
- Windows server 2022
- Kali linux
- Ubuntu Server
- Windows 10

# steps
- To begin I went to the windows page and downloaded windoes server 2022
- Settup my iso in virtual box
- be sure to set up you server with the desktop experiance version to make it a little more begin friendly

  ![image](https://github.com/user-attachments/assets/212fa8ed-36b2-4be4-9f47-aeac76325775)


- Server is up and running
- I enabled a second network adapter so I could have an internal network as well as an external network

  ![image](https://github.com/user-attachments/assets/39df3b52-508a-4db9-9491-77f21849e1ca)


  ![image](https://github.com/user-attachments/assets/bafe9e00-e6de-4f3e-86e3-276df6f070c6)

  - Once added start you AD server and enable a static IP address for you internal network
  - Identify which enternet is your external and internal you can tell by the ip address
  - you internal will be an ip addres not effected by DHCP so these IP addresses are typically anything between (169.254.0.0 - 169.254.255.255)
 
    ![image](https://github.com/user-attachments/assets/00101d3a-b8c6-4e53-83ba-19b53b3b558f)


    ![image](https://github.com/user-attachments/assets/5db60a14-e9a4-4d3c-94da-4e0bd464f779)
    




