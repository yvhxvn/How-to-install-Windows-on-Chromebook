**In this guide, I will describe how I changed the operating system of my Lenovo 14e Chromebook from Chrome OC to Windows 10**

>**Warning** *all that is described is an example that may NOT be suitable for you due to different models of Chrombook and different components, be careful.*

>**Warning** *before you start changing the operating system, make a backup copy of all files, as they can be erased in the process, be careful.*

>**Warning** *One part of the guide involves handling your device mechanically and using a screwdriver to make physical contact with the device. Be careful when handling an exposed device, as you may injure yourself.*

You need to bring: a screwdriver, two USB Flash drives of at least 8 GB, a charging cable.

*Optionally have an external keyboard and mouse.*

# Stage one: Preparing for Windows installation

You need to find out the model and hardware of your Chromebook to make sure that it is possible to run Windows 10/11 on it at all.

*If your Сhromebook does not have your model number on the back, read the description below.*

1. Click on the search icon on your Chromebook
2. Type `chrome://system`
3. Scroll down to **vpd\_2.0**
4. Click on **Expand...** to check the model of Chromebook
![1](https://github.com/user-attachments/assets/7b4fdede-cfef-4eb3-94ad-a823a0e5cd97)
![2](https://github.com/user-attachments/assets/6c450793-c87d-471b-a04a-869c2909418f)
Once you know the model of your chromebook, you should also find information about the **hardware** of your model.

*Whether it is possible to run Windows 10/11 on your Chromebook depends on the hardware in it.*

1. Open your internet browser
2. In the search write `[model of your chromebook] specs`
3. Open the first website where you can see the official specifications of your Сhromebook
4. Write down the name of the processor your Сhromebook uses.

**After you have all the necessary information about your Сhromebook, we can find out if it is possible to run Windows 10/11 on it.**

1. Go to website [CoolStar](https://coolstar.org/)
2. Click on **Chromebooks**
3. In the *Instal* *Windows 10 or 11* coloumn, click **Instal**
4. In the opened window select **all your hardware** to get the result

**If you did everything right, you should get one of these results:**

![2025-05-12_112638](https://github.com/user-attachments/assets/2eb224df-6b63-429a-b8ec-dc587113d5de)

[If you see this message, you can safely install Windows 10]

![2025-05-12_112728](https://github.com/user-attachments/assets/22f70d26-6432-44d8-971b-4a5503d19c30)

[If you see this message, you are still able to install Windows 10, you will need to install the «stripped down version»‎, more on this later in the guide]

![2025-05-12_112845](https://github.com/user-attachments/assets/ee39ec03-7cea-459b-a018-3ea819e0d1fe)

[If you see this message, I do not recommend installing Windows 10]

**Once you have received the answer to whether it is possible to install Windows 10 on your Chromebook, you can also read the list of drivers that will be required for the system to work correctly, this is a very important point, so be careful.**

# Stage two: Developer Mode

Now we will start working with your chromebook to prepare it for the installation of the new operating system.

**First, you need to run your Chomebook in** ***Developer mode***

Your Chromebook should be turned off.

![2025-05-12_114426](https://github.com/user-attachments/assets/d6a3efd2-ed75-40fc-89e5-a2c62937b150)

[Instructions on how to get into Developer Mode]

You should see this message:

![f6c178ff-9815-458d-a028-883737b60af7](https://github.com/user-attachments/assets/842a8d38-8652-428a-ba22-e29fd20f1441)

**Press** ***Ctrl+D*** **and after** **to turn OS verification OFF, press** ***Enter***

![6cEgdZJL19-3NPmuBHvBlyDyQJtwg6IP5A](https://github.com/user-attachments/assets/ab2b2363-1040-4849-a9a9-5a14f960893c)

**When you see this message, press** ***Ctrl+D*** **again and wait for the system to switch you to Developer mode.**

**After the timer expires, you will see the same message that «OS verification is OFF»** **press** ***Ctrl+D*** **again.**

![maxresdefault](https://github.com/user-attachments/assets/6f0e0978-70ef-4370-8c3b-f2b34deb51a3)

[If you've done everything right, you'll see the new chromebook user registration window.]

**Important points when login:**

1. You need to connect to Wi-Fi, Hotspot or Ethernet
2. **ALWAYS** browse as guest
3. Uncheck the box for sending and diagnosing data

**After all the actions, when you have access to the** ***‘clean’*** **Chromebook, you need to physically disable the laptop's protection for the installation of the new operating system.**

# Stage three: Disable right-protection

For this part, you will need a screwdriver. Switch off your chromebook before doing anything else.

If your Сhromebook has a way to disconnect the battery without reaching in, remove it.

1. Unscrew the back cover of your Chromebook
2. Expose the motherboard
3. Carefully check for a screw labelled ***«WP»***
4. If you see such a screw, unscrew it and you're done

![2025-05-12_142248](https://github.com/user-attachments/assets/0561907e-3e88-4958-b859-6fcd891964a2)

[screw labelled «WP»]

**In cases where you do not see a screw on your motherboard labelled** ***«WP»*****, you will need to disconnect the battery bus.** In this case, along with the battery, you will disable right-protection and then you will need to work with the device permanently connected to the power supply.

![2025-05-12_142627](https://github.com/user-attachments/assets/30dd78aa-1fe8-4de2-abec-e1bf8ecdb573)

[the battery bus]

**After these steps, put your device back together and start it up with the power cable connected.**

*(the battery bus must be disconnected until the end of the firmware)*

# Stage four: Installing the firmware

**When you start without protection, you will see the same message «OS verification is OFF».**

**Press** ***Ctrl+D*** **and login in the same way as last time.**

(*Instructions for the correct login are described above)*

You should see the familiar guest mode interface. You should still be connected to the network.

**Instructions for installing the new firmware:**

1. Press ***Ctrl+Alt+T***
2. In the **‘crosh’** window that opens, enter **‘**`shell`**’**
3. If you get an error, press ***Ctrl+Alt+Forward Arrow Key*** (F2 on external keyboards)
4. You should see the ‘localhost login: **‘** line, where you should enter **‘**`chronos`**‘**
5. If all went well, you should be able to write the command to **‘chronos@‘**
6. Rewrite this command in **‘chronos@‘**

`cd;curl -LO -k https://mrchromebox.tech/firmware-util.sh && sudo bash firmware-util.sh`

If you did everything correctly, you should see this message:

![2025-05-13_185333](https://github.com/user-attachments/assets/0e55cf97-c361-4070-9a14-cd4fadfb72ef)

**At this point, you can make sure that your Chromebook has right-protection turned off.**

*If the utility script still sees* ***‘wp’*** *protection, try all the previous steps again.*

1. Select **‘Install/Update UEFI (Full ROM) Firmware‘**
2. When asked if you want to continue, choose \[y\]
3. Enter `I ACCEPT`
4. Press on keyboard Y
5. Insert the USB flash drive and copy your firmware image to it *(the USB flash drive must be formatted in FAT32)*
6. Press *Enter* to copy firmware
7. Continue and wait for the new firmware to be installed

**DO NOT SKIP THE STEP OF SAVING CHROME OS TO YOUR FLASH DRIVE.**

After the installation process is complete, you can put the battery bus back in place.

# Stage five: Windows installation

**You need one more USB flash drive of at least 8GB to install Windows 10**

Install the .iso format of Windows on a USB flash drive using [Rufus](https://rufus.ie/en/).

>*You can learn how to use Rufus on YouTube, there are many guides.*

>*Use* ***only*** *GPT partition scheme and FAT32 when using Rufus.*

**If in \[Stage One\] your hardware is able to support the regular version of Windows without any problems, then you can install the .iso file from the official website** [Windows](https://www.microsoft.com/en-gb/software-download/windows10)

**If your hardware can only support the ‘e*****xperimental support only***‘, I recommend installing a stripped-down version of Windows. You can find them on this website: [Stripped-down Windows](https://windows64.net/windows-10-x64-skachat-torrent/sborki/), they are not official versions of Windows.

**When you have a ready-made flash drive with an installed Windows image, you need to go to the Chromebook boot-menu.**

1. Press *Escape* at system startup to enter the boot-menu
2. Choose **Boot Menu**
3. Select your Windows flash drive from the list

**If everything is correct, you should see the Windows installation menu.**

*In case when touchpad does not work in the installer, you can use the arrows to navigate.*

1. Choose language, time and keyboard. Select *‘Next‘*
2. Select ***‘Install Windows‘***
3. Select ***‘I don't have a product key‘***
4. Choose OS you want to install. Select *‘Next‘*
5. Accept the license terms. Select *‘Next‘*
6. Select *‘Custom: Install Windows only (advanced)‘*

**Ideally, you should see this set of installation discs.**
![where-do-you-want-to-install-windows](https://github.com/user-attachments/assets/d748bb7b-93c6-4a21-a956-185a2be992ba)

**If you have a lot of discs with small capacities, you need to press** ***Shift+F10*** **to open cmd**

You should see the cmd console open.

1. Type `diskpart`  then press *Enter*
2. Type `list disk`  then press *Enter*
3. Type `select disk 0`  then press *Enter*
4. Type `clean`  then press *Enter*
5. Then type `exit`

*In some cases, you may also need to convert your disc to GPT format.*

Go back once again, select *‘Custom: Install Windows only (advanced)‘* and continue with a standard Windows installation.

***At this stage, there are a lot of different problems that arise when detecting discs, in my case, I needed to load an additional driver.***

# Stage six: Driver installation

**Greetings to you! You've installed Windows 10/11, now it's time to install the drivers for it to work properly.**

Go back to the [CoolStar](https://coolstar.org/) and install the drivers that are specified.

I hope that this guide will be useful for you and you will easily install a more convenient operating system on your Chromebook.

**If you have any problems with any of the stages, please do not hesitate to write your cases in the comments.**
