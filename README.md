# MultiplayerFIX1.16.4-1.16.5
How to fix "Multiplayer is disabled. Please check your Microsoft account settings." in minecraft

## The issue

Trying to enter Multiplayer or Minecraft Realms appears the following message:

![Minecraft 1.16.5 with message "Multiplayer is disabled. Please check your Microsoft account settings." when hovering over Multiplayer or Minecraft Realms](https://media.discordapp.net/attachments/1122366459927081050/1191924629837709363/170424739111628216.png)

This error appear to be a authlib error (idk what is but i think its something about error handling?)

## Fix 1 (Every boot)

- turning off the internet when launching minecraft and after appear the main screen, turn on the internet. Now the two buttons should be enabled

## Fix 2 (Permanent) only for PollyMc, Prism Launcher, UltimmMC, MultiMC 

the other fix implies modifying the minecraft version with a patch

i'll show you the steps:

- Enter the **Edit** mode of the instance and go to **Version**
- Select **Minecraft** and press the button at the right that says **Customize**

Now we need to edit a little file, if you press the folder button from the instance you will see a folder named patches, you need to edit the file inside that folder (**net.minecraft.json**)

i recommend Notepad++, search for **com.mojang:authlib**

![com.mojang:authlib](https://media.discordapp.net/attachments/1122366459927081050/1191929536913342495/170424856212799276.png)

And **Replace** that with         

```
        {
            "downloads": {
                "artifact": {
                    "sha1": "0d73fe20bbeb6336a2add5ccc20d1803a3b6d1f8",
                    "size": 77642,
                    "url": "https://libraries.minecraft.net/com/mojang/authlib/2.1.28/authlib-2.1.28.jar"
                }
            },
            "name": "com.mojang:authlib:2.1.28"
        },
```

Save the file.

___
Now you need to replaced a file (Authlib)
-  **Download**  file: [Link](https://github.com/CmlLib/CmlLib.Core/files/12069936/authlib-2.1.28-workaround.zip)

- open your Launcher Root folder 
- go to **libraries\com\mojang\authlib\2.1.28** 
- delete the jar and paste the jar from the zip above to that folder (changing the jar file name to **authlib-2.1.28.jar**)

All done!! Now if you open the game it should work perfect


## Fix 3 (Permanent) (Any Launcher)

-  **Download**  file: [Link](https://github.com/CmlLib/CmlLib.Core/files/12069936/authlib-2.1.28-workaround.zip)
- Go to your .minecraft 
- go to **libraries\com\mojang\authlib\2.1.28** 
- delete the jar and paste the jar from the zip above to that folder (changing the jar file name to **authlib-2.1.28.jar**)

Now this is the important thing, you need to **disable write acess**  to that file, because if your launcher detects another hash that is not from the original file, it will override it with broken


i will show you:

- Right click, Properties -> **Security** -> **Advanced**
- Click **Disable inheritance**
- Convert inherited permissions into explicit permissions on this object.
- Now you need to enter every user thats appear on the **Permision entries** and only allow them to **Read & Execute** and **Read**
Like This: ![x](https://media.discordapp.net/attachments/1122366459927081050/1191934316679282748/170424970113938049.png)

Click **Apply** and it should be good!

Now if you open minecraft it should work
