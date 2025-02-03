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
  - Go under properties with  internet protocol version 4
  - Change your ip address and DNS

    ![image](https://github.com/user-attachments/assets/65d89d35-e976-413f-a598-5c78a3aca12b)

  - Click on add roles and features under the server manager dashboard

    ![image](https://github.com/user-attachments/assets/63805f82-0ac4-4005-8f22-52363e12383f)

  - Click next then selecto your server
  - After that make sure to select Active Directory Domain Services

    ![image](https://github.com/user-attachments/assets/eb8d8216-2bd9-4a93-8c0f-9f4e62453854)

  - Finish the installation
  - Once done click the notafications and click on promote this server as domain controller
  - Name your domain set a password click next until you get to the prerequisites check window
  - Then install
  - Once installed you are all set to make your Organizational Units and play around with your brand new Active Directory!
 
  - Now that we have that set up i will start making an admin account
  - I have created a new folder named admins a created a new user under active directory users and computers

    ![image](https://github.com/user-attachments/assets/39ab0cd1-9dc3-45ee-bc4a-d14bb3b90b0a)

  - Then i will go under properties and change my permissions to admin permissions
  - Go to the member of catagory and add a domain admin service folder

    ![image](https://github.com/user-attachments/assets/02693563-505e-42ee-80b3-48243ff116ec)

  - Click check names and then click apply and ok
  - Once done sign out and then sign back in as your admin
  - Next we will be installing Ras/Nat for external access to the internet through the domain controller
  - Click on add roles and features once you are back in the server manager
  - Then once on Server Roles you will select Remote Access
    

    ![image](https://github.com/user-attachments/assets/dd62cd49-1f9a-457a-a49d-f3615fab1971)

  - Under Role Service you will select Routing and add this feature
  - Then install
  - After installation go to Routing and Remote access

    ![image](https://github.com/user-attachments/assets/13abf3ef-8309-4ce7-95f1-05b5fffc392a)

  - Right click on your server

     ![image](https://github.com/user-attachments/assets/0845dfb0-c0ac-4c65-8d60-2b110016790f)

  - Left click on configure and enable routing and remote access
  - Make sure to click Network Access Translation (NAT)

    ![image](https://github.com/user-attachments/assets/47a6257a-c456-4616-b0fe-8660a43e2a0b)

  - You may need to close you window and redo this process if you are having issuses with your internet options not appreaing in the configuration settings
  - Make sure to click the outgoing internet connection not the internal network

    ![image](https://github.com/user-attachments/assets/ca653058-2a90-4397-a939-7f0a195a919a)

  - Next we will add a DHCP role just like we did with our routing and remote access role
 
    ![image](https://github.com/user-attachments/assets/f3629fa8-e56d-4e28-9ae5-78ac0440d7da)

    ![image](https://github.com/user-attachments/assets/ce984d56-13e0-420c-9351-cd1d348022e5)

    
    ![image](https://github.com/user-attachments/assets/90e37430-55e3-4f67-87e2-773895c83a58)


    ![image](https://github.com/user-attachments/assets/e76136dc-61be-4615-9f43-1259c666474f)


  - Once installed go to tools DHCP and set up your IP address scope
  - Right click your IPv4 then click on the new scope option

    ![image](https://github.com/user-attachments/assets/49814cf8-584e-4a46-ab11-ac93c2e386cf)

  - With new scope selected set your IP address range under the name tag like so

    ![image](https://github.com/user-attachments/assets/eba6ef9d-964d-4d22-8e95-d5156b56031b)

  - Set your actual IP addresses it should look like this when you are done

    ![image](https://github.com/user-attachments/assets/3cf3c4dc-3f96-4f4c-889a-e97ab5aecc75)


  - No exclusions are needed right now
 
    ![image](https://github.com/user-attachments/assets/07d6c2ac-eaef-4878-9c78-4f4d7272b299)

  - Leaving the expiration time as 8 days

    ![image](https://github.com/user-attachments/assets/2d84b50a-ec78-4988-a355-9a23ecc3fd13)

  - Yes to configuration

    ![image](https://github.com/user-attachments/assets/75603c82-38f8-475e-b8da-aef163af3d5b)

  - Make sure to add you domains IP address in this window and click add
  - I ran ipconfig to ensure i selected the correct IP address just incase i need to com back and change anything in the future
 
    ![image](https://github.com/user-attachments/assets/d137b494-d948-4f06-801f-f67b1dd49125)

  - Server is already added so hit next

    ![image](https://github.com/user-attachments/assets/c001878d-914a-4f2b-bbb5-f84f2298f6ec)

  - Skip wins server so hit next

    ![image](https://github.com/user-attachments/assets/5755c21c-a34d-4c5f-a98a-131dc88cc1e7)
    
  - Select yes to activate and click next 

    ![image](https://github.com/user-attachments/assets/c2af716c-b882-422f-b907-0d2297f710fb)

  - Make sure to right click on your server and authorize
 
    ![image](https://github.com/user-attachments/assets/1da563a7-4cce-4c83-89bd-fd251dc52c07)

  - Then click refresh and your servers should be green indicating that everything is running smooth
 
    ![image](https://github.com/user-attachments/assets/b6628684-41ce-4c11-aff1-51fc33246fe3)

  - Next we will be adding users using a powershell script i found on github
 
  - So I have clicked the start menu
  - Clicked on powershell
  - Then right clicked and chose open as administrator
  - Once powershell has opened i clicked open script in the top right corner

    ![image](https://github.com/user-attachments/assets/664038d8-fdf5-47b2-a7a9-3ebc4aacbffd)

  - Then i found my file with the downloaded script and opened this file
 
    ![image](https://github.com/user-attachments/assets/6a032a12-e8d1-4c8e-981f-4fd2300b566d)

  - We have to allow this script to be unrestriced so I ran this command: Set-ExecutionPolicy Unrestricted

    ![image](https://github.com/user-attachments/assets/18b64ef1-53cf-4d57-a937-9e9e656ccda9)

  - In the pop up window make sure to click yes to all
  - Changed my directory to the one with the needed file
  - Make sure to ls and check if you are in the correct directory

    ![image](https://github.com/user-attachments/assets/e083f142-bfcc-4b4e-8d2a-14c582ea852a)

  - Click play and then run once to start the generation process
 
    ![image](https://github.com/user-attachments/assets/e6982b02-552f-4309-b117-a1d6c655ea0c)

  - The blue txt is the creation in progress
  - If you look in the bottom left corner you will find 1053 users where created

    ![image](https://github.com/user-attachments/assets/dda9346b-e734-4b95-b943-56aeceacdc6c)

  - Next i will be adding a Windows VM directly ot my windows server as a client



    

    












    

    


    



    



    
    




