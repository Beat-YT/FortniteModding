# Quick tutorial on how to mod older versions of Fortnite.

## 1. Download the UE4 build that the Fortnite version you want to mod uses. 

- (For Season 4 i recommend using 4.19 as custom maps work on it, and for 7.10/7.30, 4.21.)

> How to check what UE4 build the Fortnite version i want to mod uses?

![](Images/VersionCheck.gif)

## 2. After you download Unreal Engine, open it and create a new blank project called "FortniteGame".

## 3. After you've done that, make a folder and call it "Maps", then create a level inside of it and choose a name for it.
![](Images/LevelCreation.gif)

## 4. Then create 2 c++ classes, one that's an Actor, call it "FortTimeOfDayManager", and second one thats a child of WorldSettings, call it "FortWorldSettings".
- You need either Visual Studio 2017 or 2019, depends on the UE4 build that you are using!

![](Images/FortTimeOfDayManager.gif)

- If you have this issue, press Yes
![](Images/ActorIssue.png)
- It will open the output log window, you possibly dont have Windows SDK v8.1 installed! If thats the case then install it and.
![](Images/BuildError.png)

## 5. After creating the c++ classes, in visual studio go to FortWorldSettings.h, add an include for FortTimeOfDayManager, and paste the rest under "GENERATED_BODY()"

 ![](Images/Code.gif)

```cpp
#include "FortTimeOfDayManager.h

...

public:

UPROPERTY(EditAnywhere, BlueprintReadWrite)
TSubclassOf<AFortTimeOfDayManager> TimeOfDayManager;
```
 - You need to rewrite this part because markdown is skunked.

- Then get out of vs and press the compile button.

## 6. After it compiled everything successfully, re-open your project

## 7. Then go to the edit tab and select Project Settings.
- From here search for World Settings Class
![](Images/ProjectSettings.png)
- Change it to Fort World Settings
- ![](Images/FortWorldSettings.png)

## 8. Then compile the project again and open your map
- In case you dont have the World Settings menu on the right side of UE4, open the Window tab

![](Images/WindowTab.png)

- And press on World Settings

![](Images/WorldSettings.png)
![](Images/TODMSelection)

- Here you will find the Time Of Day Manager variable you have just made, now go back to the Content folder

![](https://user-images.githubusercontent.com/72986221/135766796-b0f64964-a97b-4907-b445-b2a3594bea48.png)
- Make a folder called TimeOfDay

![](https://user-images.githubusercontent.com/72986221/135766806-0c8bc393-0dd4-48f9-95b2-bd71f3baebc7.png)
- And inside of it another one called TODM

![](https://user-images.githubusercontent.com/72986221/135766811-10005f7f-65a1-43c0-8d88-77dde746182c.png)
- And another one inside of it called BR

![](https://user-images.githubusercontent.com/72986221/135766818-fc6bb3a5-7e62-48e9-98e5-8dfba08ecf4b.png)

- Then just follow what i did on the gif

![](https://cdn.discordapp.com/attachments/894281085393977408/894294585872875540/ezgif-2-d1035d703103.gif)

- After that make a new c++ class thats a child of PlayerStart and call it FortPlayerStartWarmup

![](https://user-images.githubusercontent.com/72986221/135767066-750487ba-51be-4f92-92c5-d5ce7df2b5a3.png)

![](https://user-images.githubusercontent.com/72986221/135767105-b597d8ac-4a91-4442-82e5-9e5b217632f5.png)

Search for it here and place it on the map 

## 9. You are done! Now go to the File tab and press the Cook content for windows button.

![](https://user-images.githubusercontent.com/72986221/135767386-70b085e4-c42f-469f-8ea1-8acb7242851f.png)


## 10. Go to the folder with your project

![](https://user-images.githubusercontent.com/72986221/135767509-283110b9-da11-4ab7-9b71-4c3a6fd7c781.png)

- Go to the saved->cooked->windowsnoeditor->fortnitegame->content folder
- Copy the Maps folder from here.
> Download u4pak https://cdn.discordapp.com/attachments/894281085393977408/894324308950798406/u4pak.zip
- Unpack it and create a folder inside of it called FortniteGame, then another one inside of FortniteGame called Content, and here paste your Maps folder.

![](https://user-images.githubusercontent.com/72986221/135767761-45142c84-8517-4eed-a692-ce826d213d05.png)

- Then just drag the FortniteGame folder on the bat.

![](https://user-images.githubusercontent.com/72986221/135767774-800e5657-50e7-43bd-a01e-985493f3b290.png)

- Congrats, you made a pak file. Rename it to whatever you want (make sure it starts with "pakchunk" and ends with -WindowsClient")

## 11. Put the pak file inside of the Paks folder.
- Copy the pak file and put it inside of the Paks folder of the fortnite version you are modding

![](https://user-images.githubusercontent.com/72986221/135767841-f90697f8-db11-41dd-96c4-ae4290090afd.png)

- For 7.10/7.30 i recommend this sig
> https://cdn.discordapp.com/attachments/894281085393977408/894298941607280640/pakchunk2521-WindowsClient.sig
- For the other builds just copy and rename the smallest one thats in the Paks folder and rename it so the name of it is equal to the name of the custom pak you have just made.

## 12. Now launch your game using the era launcher, then in the lobby open the console and type "open /Game/Maps/{YourMapName}?game=/game/athena/athena_gamemode.athena_gamemode_c"

** NOTE: You will be probably loading into the map for like 2-4 minutes, thats normal and danii is working on a fix already!**
