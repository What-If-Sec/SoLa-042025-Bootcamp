## Activity Objective

By the end of these activities, students will be able to:

1. Identify the different types of Linux distributions and their purpose.
2. Utilize VirtualBox or VMWare virtualization software to create a virtual machine (VM), including configuring hardware settings such as CPU, RAM, storage, and networking, and installing an operating system (OS) within the VM environment.

Through these exercises students will gain an understanding virtualization concepts and the Linux landscape.



## Assignment Instructions

>   Take screenshots of your installation process, as this will be needed for your submission.

Follow the instructions below <b>for Windows & Mac Intel Chip Users</b>:

1. Download Ubuntu Desktop by visiting the official Ubuntu website and download the latest LTS (Long Term Support) version of Ubuntu Desktop. Ensure that you select the appropriate architecture (32-bit or 64-bit) based on your system requirements.
2. Within VirtualBox create a New Virtual Machine by clicking on the "New" button to create a new virtual machine.
3. Follow the wizard to set up the virtual machine, including specifying the name, type, and version (select "Linux" and "Ubuntu" respectively).  Also, check "skip unattended installation" then click next.
4. Allocate the appropriate hardware resources such as RAM and number of processors for the virtual machine, then click next. (Recommended: at least 8GB of RAM and 2 CPUs).
5. Allocate the appropriate virtual hard disk size, then click next. (Recommended 40-60GBs).
6. Review your VM's configuration settings, and then click finish.
7. Select the newly created virtual machine from the panel and click on the "Settings" button. Adjust additional settings as needed, including network configuration, display settings, and any advanced options. (Recommended 32 MBs of video memory and a bridged adapter for Network Adapter 1).
8. Start the virtual machine by clicking on the "Start" button. Follow the Ubuntu installation wizard within the virtual machine, selecting language, keyboard layout, and installation options as required.
9. Choose "extended selection" when asked "What apps would you like to start with", then click next.
10. Select install 3rd party software for graphics and Wi-Fi hardware, as well as download and install support for additional media formats, then click next.
11. Choose the "Erase disk and install Ubuntu" option to perform a clean installation, then click next.
12. Provide the name "admin" as your name, provide the name "ubuntu" as your computer's name, provide "admin" as the username, and then create a password and confirm it. Once done, click next to continue.
13. Once Ubuntu is installed, log in to the virtual machine and explore the Ubuntu desktop environment. Familiarize yourself with basic navigation, applications, and system settings within Ubuntu.
14. Open Firefox on your VM  and login to EducateMe as well as install and login to Slack. This will help you with completing future assignments and collaborating with your fellow students.

Follow the instructions below <b>for Mac Arm Chip (M1, M2, etc.) Users</b>:

1. Within your documents folder on your Mac create a folder named "SOLA-Bootcamp".
2. For Mac ARM Chip Users download Ubuntu Server by the official Ubuntu website and download the Ubuntu Server for ARM image.
3. Within VMWare create a New Virtual Machine by going to File -> New, and then select "install from disc or image", then click continue.
4. Choose an operating system for your new VM, selecting the Ubuntu server iso file, then click continue.
5. Select customize settings, and provide the name "BoootcampVM" for your VM. Afterwards, save your VM to the "SOLA-Bootcamp" folder you previously created.
6. Select and configure the network adapter settings, and select "autodetect" under the bridged networking section, then click "show all" to go back to the main VM settings screen.
7. Select and configure the hard disk settings, and allocate the appropriate virtual hard disk size, then select apply (Recommended 60GBs). Once completed, click "show all" to navigate back to the main VM settings screen.
8. Once your VM's settings have been configured, close the settings dialog box.
9. Start the virtual machine and follow the Ubuntu installation wizard within the virtual machine, select the desired keyboard language and press enter to continue.
10. Confirm your keyboard language settings, and press enter to continue.
11. Ensure that "Ubuntu Server" is selected as the base for the installation, and press enter to continue.
12. Next, keep the default network configuration, and press enter to continue.
13. Do not provide a proxy address, and press enter to continue
14. Wait for the mirror location to pass the tests, and once completed press enter to continue.
15. Keep the default guided storage configuration settings, and use your arrow keys to navigate down to "done", and press enter to continue.
16. Confirm the default storage configuration for your Ubuntu server VM and press enter to continue.
17. Confirm that you want to continue, by selecting "continue" and pressing enter.
18. Provide the name "admin" as your name, provide the name "ubuntu" as your server's name, provide "admin" as the username, and then create a password and confirm it. Afterwards, navigate to "done" and press enter to continue.
19. Once completed use the arrow keys to select "done" and press enter to continue.
20. Do not enable ubuntu pro, and press enter to continue.
21. Do not install the OpenSSH server, and use the arrow keys to select "done" and press enter to continue.
22. Do not install any popular snaps to your server environment and use the arrow keys to select "done" and press enter to continue.
23. Once installation is complete, use the arrow keys to navigate to "Reboot Now" and press enter to continue.
24. Ignore any error messaging (if it appears), and press enter to continue.
25. Once Ubuntu is installed, log in to the virtual machine; by default, your Ubuntu Server is a headless server (meaning it does not have a Desktop GUI). Note: On the login screen your password is hidden, meaning it will  not show as you type.
26. Once you've gained access to your VM, type the following commands into your VM's terminal shell, ```sudo apt update -y && sudo apt full-upgrade -y```. Note: You will need to provide your password for these commands to execute successfully. Like when you login to your VM, your password will be hidden.
27. Once the update and upgrade is completed, type the command ```sudo reboot``` into your VM's terminal shell.
28. Login to your VM, and type the following command ```sudo apt install ubuntu-desktop -y```.
29. Once the Ubuntu desktop GUI is installed, type the following command into your VM's terminal shell, ```sudo reboot```.
30. Login to your VM and explore the Ubuntu desktop environment. Familiarize yourself with basic navigation, applications, and system settings within Ubuntu.
31. Open Firefox on your VM  and login to EducateMe as well as install and login to Slack. This will help you with completing future assignments and collaborating with your fellow students.

### Submission:
1. Take screenshots throughout the process, including the VirtualBox setup, Ubuntu installation steps, and the final Ubuntu desktop.
2. Compile the screenshots into a document or presentation.
3. Write a brief reflection on your experience, highlighting any challenges faced and lessons learned during the deployment process.
1. Take screenshots throughout the process, including the VirtualBox setup, Ubuntu installation steps, and the final Ubuntu desktop.
2. Compile the screenshots into a document or presentation.
3. Write a brief reflection on your experience, highlighting any challenges faced and lessons learned during the deployment process.
