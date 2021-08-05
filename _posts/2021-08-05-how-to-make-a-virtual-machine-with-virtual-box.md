---
layout: post
title: "How to make a virtual machine with VirtualBox"
thumbnail-img: /assets/img/virtualbox/coverImg-2.png
date: 2021-08-05
#last-updated: 2021-07-23
tags: linux virtualbox
---

So you want to create a virtual machine, but you don't know how? Well, let me tell you that it's actually not that difficult to do. Whether it is to try a new OS, test software on another OS, or run games on another OS (ok, maybe don't do this one), a virtual machine will come in handy. There are various virtualization software that we can choose from, but for this tutorial, we will be using Oracle's VirtualBox. 

## Before you start...

Make sure your device supports virtualization. Most recent computers/laptops support virtualization, so you won't really have to worry about this. However, if you are running an older computer, check to see if your computer supports virtualization.

Additionally, make sure your computer meets the following: 

- At least 4 GB of RAM
- A CPU with at least 4 cores
- Decent Graphics Card

Keep in mind that these requirements will help you run a (sort of) sluggish VM. These are not hard requirements and you will still be able to run a virtual machine with a less powerful computer, however, you will probably have a very sluggish and unpleasant experience.

To have the VM running smoothly, it would be best if you have:

- At least 8 GB of RAM
- A recent CPU with at least 8 cores
- A high end graphics card
- An SSD instead of a HDD

## Step 1: Download VirtualBox from the official website

Go to <a href="https://www.virtualbox.org/" target="_blank">https://www.virtualbox.org/</a> and click on the big blue button that says "Download VirtualBox" in the middle of the page.

Under "Virtual box platform packages", click on the operating system that you are running to download the appropriate file. After the file is downloaded, run it and follow the steps on the screen.

**Note: If you are running Linux,** you will have to go through an extra step. Once you click on the "Linux distributions" option, you will be taken to a page titled "Download VirtualBox for Linux Hosts". Once there, under "VirtualBox for Linux", click on the Linux distribution that you are running. If you don't see your specific Linux distribution on the list, click on the Linux distribution that your distribution is based on. So if your Linux distribution is Linux Mint 20, click on the "Ubuntu 19.10 / 20.04 / 20.10 / 21.04" option (since Linux mint is based on Ubuntu). If neither is on the list (as is the case with Arch based distributions), try looking for VirtualBox in your distribution's package manager. 

## Step 2: Create a new virtual machine

Once Virtualbox is installed on your system, open the application. To create a new virtual machine, click on the "New" button at the top of the screen.

![New button](/assets/img/virtualbox/vbox-app-1.png)

You should see a dialog box that looks like this:

![New dialog](/assets/img/virtualbox/vbox-new-os.png)

In the "Name" input field, give a name to your virtual machine. If the name is similar to the name of an OS (such as Windows 10), VirtualBox will automatically adjust the virtual machine type. 

After you have given the virtual machine a name, select where you would like to store the virtual machine. You can either type the path manually or click on the downwards pointing arrow to the right of the folder path input field and click on the "Other" option in the dropdown menu. A file explorer dialog box will appear in which you can select where you would like to store your virtual machine. 

Next, select the OS type in the drop down menu next to "Type" and select the OS version in the drop down menu next to "Version". Click on the "Next" button on the bottom right corner once you are done.

After that, you will need to select the amount of RAM you would like to allocate to your virtual machine. You can stick with the recommended amount for now. Note that the amount of RAM you are allocating will be unavailable to your host OS *only when the virtual machine is running*.

![RAM selection dialog](/assets/img/virtualbox/vbox-ram.png)

Next, you will create a Virtual hard disk file. You can either choose an existing file, create a new disk file or decide to not create one at all. Select the "Create a virtual hard disk now" option and click on "Create". A dialog will appear asking you to select a file type. For now, select the "VDI (VirtualBox Disk Image)" option. Click "Next" and choose whether you would like the virtual hard disk to be dynamically allocated or have a fixed size. The dialog gives you more information about each option. If you don't know which one to choose, just leave it at it's default and click "Next". 

Now you will need to choose the location and the size of the disk file. For the storage location, you can leave it as is or change it. To change the location, you can either type in the path manually or click on the button to the right of file path input field and search for the location you would like to store it in. 

![Disk file size](/assets/img/virtualbox/vbox-disk-size.png)

To choose the size of the virtual hard disk, you can either move the slider or type the size (in GB or MB) manually in the input field next the the slider. After you are happy with the amount, click on "Create".

Congratulations! You have created a virtual machine. It should now appear on the left of the home page below "Tools".

![Virtual machine list](/assets/img/virtualbox/vbox-machine-list.png)

## Step 3: Download the ISO file for the OS you would like to download and attach it to your virtual machine

In order to continue, you will need to find and download the appropriate ISO and attach it to your virtual machine. The ISO file you download will depend on the OS you would like to install. So if you would like to install Windows 10 on your virtual machine, then you would need to download the appropriate Windows ISO file from Microsoft's website. Please remember to be careful when downloading ISO files, as you don't want to use a pirated or compromised file. Make sure you are downloading the file from the correct site and make sure to check the file's integrity before you use it. If you don't know how to do this, <a href="https://linuxconfig.org/how-to-verify-the-integrity-of-a-linux-distribution-iso-image/" target="_blank">here is a useful resource that could help</a>.

Once you downloaded the ISO file and verified it's signature, you may now attach the file to your virtual machine's storage device. To do that, you will need to go to click on the "Settings" next to the "New" button you clicked earlier. 

![Settings button](/assets/img/virtualbox/vbox-app-2.png)

In the dialog that comes up, click on the "Storage" tab on the left. Here, under "Storage devices", select the slot with a disk icon named "Empty". Once selected, under the "Attributes" section to the right, click on the icon that looks like a disk with a downwards pointing arrow. Click on the "Choose/Create a Virtual Optical Disk" option in the dropdown menu that comes up. 

In the dialog that comes up, if you don't see the ISO image you downloaded, then click on the "Add" button at the top left and search for the ISO file using the file navigation menu that comes up. 

![Optical disk selector](/assets/img/virtualbox/vbox-disk-selector.png)

Once the file is added to the menu, select the file in the menu and click on "Choose" at the bottom right. The option that used to be "Empty" should now have the ISO file you selected.

![ISO file attached](/assets/img/virtualbox/vbox-iso-attached.png)

Click "Ok" at the bottom right of the dialog to save your adjustments.

## Step 4: Adjust settings if necessary

To adjust the settings of your virtual machine and change the amount of resources allocated to it, click on the "Settings" button. To change the amount of memory and CPU's allocated to your virtual machine, go to the "System" tab on the left. There, you will have 3 tabs, the Motherboard, Processor, and Acceleration. 

![System tab in settings](/assets/img/virtualbox/vbox-settings-1.png)

Since you already selected the amount of RAM you where going to allocate earlier, we can ignore this section for now. Go to the Processor section to change the amount of CPU's allocated to the virtual machine. The default is 1 CPU, which is probably not ideal since that will make your virtual machine quite sluggish. It's best to change it to 2 or more CPU's, if your computer has that many. 

Use the slider next to "Processor(s)" to choose the amount of CPU's you would like to allocate. Please remember not to select more CPU's than your computer has. You will get a warning at the bottom of the screen if you do.

Next, click on the "Audio" tab to the left and make sure the box next to "Enable Audio" is checked. Well, you don't have to have this option enabled, but I assume you probably want to hear some audio coming from the virtual machine.

![Audio settings](/assets/img/virtualbox/vbox-settings-2.png)

If you would like your virtual machine to have the ability to record audio input (as is the case with screen and audio recording), then check the "Enable Audio Input" option next to "Extended Features".

Finally, go to the "Network" tab and make sure the option "Enable Network Adapter" is checked, or else you won't be able to access the internet.

![Network settings](/assets/img/virtualbox/vbox-settings-3.png)

To save your adjustments, click on "Ok" at the bottom right.

For now, these should be the only settings you need to change to get started. As you get more advanced, you may want to learn more about all the other settings that I did not cover in this section.

## Step 5: Start your virtual machine

Now that we went through all the work to set up our virtual machine, we may now start running it! To start a virtual machine, make sure it is selected on the left menu and click on the "Start" button next to the "Settings" button.

![Clicking Start in VirtualBox](/assets/img/virtualbox/vbox-app-3.png)

A dialog may appear that asks you to choose a disk file. If the appropriate disk file is selected in the box located at the middle of the screen, then click on "Start" at the bottom right. If the appropriate disk file is not selected in the box at the bottom of the dialog, click on it to use the drop down menu in order to select the appropriate ISO file from the list. If the ISO file is not there, you can click on the button that looks like a folder with a downwards pointing arrow to bring up the file navigator. Once the appropriate ISO is selected, click on "Start".

## Step 6: Go through the installation process

Now that you have started the virtual machine, all you have to do now is go through the installation process as if you installed the OS on a new computer.

I hope this article helped! Make sure to share this article with someone who might find it useful. If you find an error or typo in one of my articles, please let me know.

**NOTE: I AM NOT LIABLE FOR ANY DAMAGES THAT HAPPEN BECAUSE OF YOU FOLLOWING ONE OF MY ARTICLES. This is not to say the information here is incorrect. Please be careful.**