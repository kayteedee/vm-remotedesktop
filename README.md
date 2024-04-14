

<h1>Azure Virtual Machines with Remote Desktop</h1>
This tutorial outlines how to create a Resource Group and Virtual Machine using Microsoft Azure and then accessing our Virtual Machine virtually using Remote Desktop. By following these steps, you can successfully deploy and access a virtual machine in Azure using Remote Desktop Connection, which provides a graphical interface to manage your VM remotely. This process requires careful setup of both network security settings and operating system configurations to ensure accessibility and security.


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Active Azure Tenant and Subscription
- Remote Desktop Connection Software
- Basic Knowledge of Operating Systems
  

<h2>Steps to Deploy</h2>

<img src="https://i.imgur.com/T37u1BG.png"/>
<img src="https://i.imgur.com/LX4PslP.png"/>

You can use the Azure Portal to create a Virtual Machine. Once inside of the portal, you'll navigate to "Virtual machines" and select "Add" to start the creation process. 
The first thing we are going to do is actually go ahead and "create new" resource group. You can name this anything but for the sake of this project I chose to name mine RG-Portfolio. Then I went ahead and choose the name VM-Portfolio for my VM name. Now its time to do some configuration. 

<img src="https://i.imgur.com/DYbQNqw.png"/>
<img src="https://i.imgur.com/vkXDFao.png"/>
<img src="https://i.imgur.com/1W2Rtai.png"/>

There are several different settings that need to be configured. Some of those will include: Region for locating the VM geographically,
availability options if high availability is needed, size of the VM (select based on CPU, RAM, and other needs) and choosing your operating system (Choose from available images like Windows Server or various Linux distributions). Then youll need to set up your administrator account by creating a username and password or SSH key for Linux VMs, as well as opting in for the inbound ports since you will need an open TCP port 3389 to enable Remote Desktop access. And then to finish up with this page, make sure you check the Licensing box.

<img src="https://i.imgur.com/HOuTZzq.png"/>
<img src="https://i.imgur.com/yugF1Sh.png"/>

You can go ahead and click "next" for disc and then "next" again for Networking. Here you will see that it automatically creates us our virtual Network, subnet, and Public IP address. A virtual network (VNet) and a subnet within Azure to ensure that the VM can communicate securely with other resources or the internet, if necessary. As for the public IP address, although it is not mandatory, it is needed if you want to access the VM from the internet via Remote Desktop Connection. Then you are able to make any needed changes or updates to the Network Security Group(NSGs). An NSG to define security rules that allow or deny network traffic to the VM. As I stated above, you'll need to allow inbound traffic on TCP port 3389 for remote desktop connection. Go ahead and click "review and create".

<img src="https://i.imgur.com/yugF1Sh.png"/>
<img src="https://i.imgur.com/X5XDROq.png"/>

Assumming that everything looks good, you will see a message display letting you know "Validation Passed". You can now proceed to click "create" and your virtual machine deployment process will begin. This should only take a few minutes for our resource group, VM, and other reasources to be created. Once its finished and ready to go we will copy the Virtual Machines public IP address and head on over to the Remote Desktop Connection Client. On Windows, you can search for "Remote Desktop Connection" in the Start menu.

<img src="https://i.imgur.com/f2nzmYx.png"/>
<img src="https://i.imgur.com/i6vbPs5.png"/>

Once you open the Remote Desktop Client, you will click "add pc". Now you can go ahead and enter the public IP address of the VM that you created. Then you will need to specify the username and password that was set up during the virtual machine configuration. You will most likely get a pop up warning you that the certificate cannot be verified. It will then ask you if you would like to proceed anyway. This is totally normal, you can go ahead and click "connect".

<img src="https://i.imgur.com/BM4ys7I.png"/>

If you made it to this screen, CONGRATULATIONS! You have successfully implented all the necessary steps required to create and configure a virtual machine in Azure and access it remotely.




