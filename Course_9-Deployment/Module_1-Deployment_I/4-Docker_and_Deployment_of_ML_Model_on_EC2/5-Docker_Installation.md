# Docker Installation

In the previous segment, you learned about Docker Container and Docker Image. In this segment, you will learn how to install Docker.
  
You can refer to the link below to download and install Docker based on your OS.

[**Download Docker**](https://docs.docker.com/get-docker/)

Note that you will face many issues and errors while starting the Docker application. Do consider following the steps below:

Before installing any Linux distributions on Windows, ensure you have enabled the Windows Subsystem for Linux and are using Windows Build version 18362 or higher. To enable WSL, run the following command in a PowerShell prompt with admin privileges:

`Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux`

You need to enable Hyper-V by running the following command in a PowerShell prompt with admin privileges:

`Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V -All`

If you are using Windows, you need to download and install the WSL Linux kernel. The link for the WSL Linux kernel is provided below.  
[Download WSL Linus Kernel](https://docs.microsoft.com/en-us/windows/wsl/wsl2-kernel)  

**Note**: If you get the following error while starting the Docker file, go to your system’s **BIOS Setup**, press the right arrow key on the **Advanced** tab, select **Virtualization Technology**, and then press the Enter key. Select **Enabled** and press the **Enter** key. 

![Cannot enable Hyper-V](https://i.ibb.co/VWV971R/Cannot-enable-Hyper-V.png)

Depending on your PC, you can use the steps mentioned in this [link](https://www.isunshare.com/computer/how-to-boot-to-bios-in-different-computers.html) to go to your BIOS.  
After you have installed both, you need to open your command prompt and run the following command:

`wsl -l -v`

Now open your command prompt as an administrator and run the following command:

`.\wslconfig.exe /u docker-desktop`

Now, restart Docker as an administrator.  
After completing the above-mentioned steps, let’s watch the next video and run some commands on the command prompt.

**VIDEO**

After downloading and installing Docker on your local system, you can run the following commands:

`docker`
`docker version`

After ensuring Docker is working correctly on your system, in the next segment, you will try to dockerize a simple Flask application.  
 
If you get any error about starting the Docker application, please refer to the following links:

[Docker running guide - I](https://docs.microsoft.com/en-us/windows/wsl/wsl2-kernel)

[Docker running guide - II](https://docs.microsoft.com/en-us/windows/wsl/install-win10)

[Docker running guide - III](https://docs.microsoft.com/en-us/virtualization/hyper-v-on-windows/quick-start/enable-hyper-v#:~:text=DISM%20Technical%20Reference.-,Enable%20the%20Hyper%2DV%20role%20through%20Settings,Hyper%2DV%20and%20click%20OK.)