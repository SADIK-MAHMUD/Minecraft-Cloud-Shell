# Minecraft Cloud Shell Tutorial & Info (Development Version)

## Note for Everyone
This Project is offically **Forked** into [LordOfWizard's Project](https://github.com/lordofwizard/mcserver). This project will consently be updating with different features. This is more like a development builds and LordOfWizard's will be the stable builds. Feel free to keep on testing this project out.

You can use [LordOfWizard's Project](https://github.com/lordofwizard/mcserver) if you want a static and more stable builds.

---
**In development:** 
> Development Build: `1.2`

- Changing from `screen` to `tmux` for better server screening.
- Adding interface for custom variable script for every server type. *(Easy to change the variables)*
---
In this project, we'll teach you host your very own Java/Bedrock Minecraft Server using `Google Cloud Shell`. This works under `Ubuntu/Debian` based Linux operation system.

**The following features are added into this project are:**
- Supports different type of Bedrock Servers
- Clean & Friendly Interface
- Supports Additional type of Java Server *(eg. Sponge, Paper, Fabric etc)*
- Added Server Management
- Easier functional scripts *(eg. [**./uninstall**](https://github.com/DumbCaveSpider/Minecraft-Cloud-Shell/blob/main/README.md#uninstallremove-the-server) allows you to delete your server easily)*
- Instant EULA script setup *(Completly skipping this part which makes other people's life much easier to manage)*
- Faster Server Installation *(It would probably take you like approx 30 seconds to setup a server)*

This is modified and license under **[MIT License](https://github.com/DumbCaveSpider/Minecraft-Cloud-Shell/blob/main/LICENSE)**

This script is used to host your very own Java/Bedrock Minecraft Server using `Google Cloud Shell`. This works under `Ubuntu/Debian` based Linux operation system.

If you want to see how it works, [**watch this tutorial**](https://youtu.be/0j0ijkwddz8).

Need help? Join my [Discord](https://discord.com/invite/HBrK26SsN4) server.

### Server Specs:
- **OS:** Debian GNU/Linux 10 (buster) x86_64
- **RAM:** 8GB to 16GB
- **Location:** Based on your physical location.
- **Storage:** Approx 55GB
- **CPU:**  AMD EPYC (2) 7B12 @ 2.249GHz or Intel Xeon (4) @ 2.199GHz

You can view your exact specs by doing `./specinfo`

### Service Used:
- [playit.gg](https://playit.gg)
- [console.cloud.google.com](https://console.cloud.google.com)

## Installation 
* Activate a [Google Cloud Shell](https://console.cloud.google.com/) on Google cloud.
* Clone this GitHub Project into the Console:
```
git clone https://github.com/DumbCaveSpider/Minecraft-Cloud-Shell
```
* Go into `Minecraft-Cloud-Shell` directory:
```
cd Minecraft-Cloud-Shell
```
* Allow all commands executable:
```
chmod +x *
```
* Run the Installation Script:
```
./install
```
Follow the installation step shown in the console
* Run the Start Server Script:
``` 
./startserver
```
(You only need to do this if you chose `No`.)

## Java Server Additional Setup (You can skip this part)
*(This only applies to Java Servers including Nukkit and if the EULA script didn't work for you.)*

If you first start up your server, it will fail to start because you need to accept the **EULA** to run properly.

* Go to the server directory and accept the [EULA](https://www.minecraft.net/en-us/eula)
```
cd server
```
```
nano eula.txt
```
* Be sure that `eula.txt` contains the following text below:
```
eula=true
```
Do `Ctrl + W` then press `Y` to save and press `Enter` exit the text editor.
* Go back to the main directory:
```
cd ..
```
- And [restart](https://github.com/DumbCaveSpider/Minecraft-Cloud-Shell/blob/main/README.md#restarting-your-server) your server.
* Now everything should be functional and ready. You can check if your server is up and running by doing `screen -r server`.
## Joining your Server
* To join your server, start your server by doing `./startserver` *(If you haven't started it yet)* and do this command:
``` 
screen -r playit
```
- Now click the **Claim URL** and it should show you your host IP and Tunnel Server.
- Once your in that page, scroll down and click **Add Tunnel** on Minecraft Java/Bedrock and next to the **Local server address**, click **Add**.
- Now copy the generated dedicated IP something along with `auto.playit.gg` and copy it into the Server Address in Minecraft and now you can play the server.

*(Note: If you want to change the Claim URL, you need to Stop the Server. This will reset your server IP.)*

## Accessing Server Console
* To access your server console, open this following session:
```
screen -r server
```
To completly stop the server, you can do `./stopserver` on the Linux console or do `exit` or `stop` on the Minecraft console

## Detaching Screen/Session
* To Detach the session you can do it using the following keyboard shortcuts 
`CTRL + A` then press `D`

## Third-Party Launcher
* If you are using like a cracked version of **Minecraft Java Edition**

Example: [Tlauncher](https://tlauncher.org/en/)

- Go to `server.properties` and find the properties `online-mode`:
```
nano server.properties
```
- Change it from `false` to `true`
```
online-mode=true
```
Do `Ctrl + W` then press `Y` to save and press `Enter` exit the text editor.

- [Restart](https://github.com/DumbCaveSpider/Minecraft-Cloud-Shell/blob/main/README.md#restarting-your-server) your server after you apply these changes.

## Access Server Files
If you want to access your server files, go to `Open Editor` on the top right.
- Once you there, if you don't see any folders on the left side, you can `Open Folder` and pick `Minecraft-Cloud-Shell` and go to `server` to view and modify anything inside.
- If you made any changes on your server, restart your server.
After you restarted your server, all the changes are saved into your server.

## Changing/Customize Variables
So image this part, so you want to setup a server that is on 1.12.2 but you can't because the script *"only"* does it install the latest version possible. Well you can now change the version of your server.
- To do this, go to either `/JavaInstallScripts` or `/BedrockInstallScripts` on `Cloud Shell Editor`

The following `Java` servers are supported for custom variables:
- **Fabric**
- **Forge**
- **Paper**
- **Vanilla**

The following `Bedrock` servers are supported for custom variables:
- **Nukkit**
- **PocketmineMP**
- **Vanilla**

These servers aren't supported for custom variables:
- Sponge `Java` *(This server type is too old and it only supports direct download)*
- GoMint `Bedrock` *(No Variables needed for this type of server)*

You can go inside the server scripts and edit **ONLY** on this section of the code:
```
# -- EDIT HERE | DO NOT EDIT ABOVE -- #
EXAMPLE_VARIBALES=VARIABLES # NOTE ABOUT VARIABLES
# -- EDIT HERE | DO NOT EDIT BELOW -- #
```

*(Note: Do not edit the code below and above as it will break the installation and you have to delete the project again.)*

## Restarting your Server
If you don't know what restarting your server mean, here's the step.
- Go to `~/Minecraft-Cloud-Shell` directory and do this command.
- Stop the server which stops both the Minecraft Server and Playit.gg tunneling system:
```
./stopserver
```
- And now start your server again:
```
./startserver
```
Now your server has fully restarted.
## Keeping the Server Alive 24/7
Due to the nature of **Cloud Shell** stopping all it's processing when closed, you can't *"technically"* host your server 24/7.
The only way to go around this issue is to keep the **Cloud Shell** open on another device that you don't use like an old phone or laptop and you can host your server that way.

*(Don't worry, your device that is being used to host your server isn't affected from the intensity of your server.)*

If you have any method the would possibly keep the server alive 24/7, feel free to **Fork** this project and request a **Pull** to this project. Any help will be greatly appreciated.

## Limitation of this project
### Google Cloud Shell Quota
While I was editing this project, I notice that Google has added a quota for each Cloud Shell uses and you can only host your server for the max of `50` hours per `Week`.
Once you used all of the hours, you can't use it again until next week.
### No Dedicated IP
Sadly you can't use the host IP into your dedicated IP as it won't let you join that server, you can only join your server by the generated dedicated IP provided by **playit.gg**. If you know how to reverse proxy the tunnel system, you *can* actually use the host IP to make a dedicated IP for your server but I highly doubt that would ever happen.
### Mixed Server Specs
Each Cloud Shell session will have different specs of your server based on your physical location so you won't always get the best performance of your server but good news being that it's always the range between `8GB` to `16GB` so you won't have to worry about lag when playing in the server with high processing in your server.

## Uninstall/Remove the Server
- If you want to make a new or delete your server, do this command inside `~/Minecraft-Cloud-Shell`:
```
./uninstall
```
It will tell you if you really want to uninstall it or not.

- This will remove the whole server folder and you can make a new one again by doing `./install`
## Deleting/Updating the whole Project
This project will constantly update day after day until I make a perfect project. If you have install this project before and it has some lack of features, you can update the project by doing this steps.
- First, go to the default folder
```
cd
``` 
- Now delete the whole project *(Be careful, backup/download your world folder FIRST before deleting it. You can't go back once you do this command)*:
```
sudo rm -r Minecraft-Cloud-Shell
```
If the project is completely deleted, you can clone the project again and it should be up to date with the new features and code from this project!
## Conclusion
Now you can host your very own Minecraft Server for both Java & Bedrock fast and easy and it won't cost you a single penny to make a fast and strong server. Best of all, IT'S FOREVER! Feel free to leave any requests you would like me to add into the project. If you have any issues, go to the [**Issues**](https://github.com/lordofwizard/mcserver/issues) tab and submit a issue there.

Thanks for using this project! *- LordOfWizard & -DumbCaveSpider*
