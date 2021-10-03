# Quick tutorial on how to mod older versions of Fortnite.

## 1. Download the UE4 build that the Fortnite version you want to mod uses. 

- (For Season 4 i recommend using 4.19 as custom maps work on it, and for 7.10/7.30, 4.21.)

> How to check what UE4 build the Fortnite version i want to mod uses?

![It is easy.](https://cdn.discordapp.com/attachments/873974318101565440/894271829957554176/ezgif-3-c813ffde612b.gif "")

## 2. After you download Unreal Engine, open it and create a new blank project called "FortniteGame".

## 3. After you've done that, make a folder and call it "Maps", then create a level inside of it and choose a name for it.
![Hi](https://cdn.discordapp.com/attachments/874274681316864028/894277073173086258/ezgif-3-918f36ef43eb.gif "")

## 4. Then create 2 c++ classes, one that's an Actor, call it "FortTimeOfDayManager", and second one thats a child of WorldSettings, call it "FortWorldSettings".
- You need either Visual Studio 2017 or 2019, depends on the UE4 build that you are using!

![Hi](https://cdn.discordapp.com/attachments/894281085393977408/894281159985471498/ezgif-3-c9251f59b54b.gif "")

- If you have this issue, press Yes
![Hi](https://media.discordapp.net/attachments/874274681316864028/894284910582464512/unknown.png "")
- It will open the output log window, you possibly dont have Windows SDK v8.1 installed! If thats the case then install it and.
![Hi](https://media.discordapp.net/attachments/874274681316864028/894284641392021514/unknown.png "")

## 5. After creating the c++ classes, in visual studio go to FortWorldSettings.h, add an include for FortTimeOfDayManager, and paste the rest under "GENERATED_BODY()"

 ![Hi]( https://media.discordapp.net/attachments/874274681316864028/894286009628520558/ezgif-3-ebc55a794921.gif "")

```#include "FortTimeOfDayManager.h```

``` 
public:

UPROPERTY(EditAnywhere, BlueprintReadWrite)
TSubclassOf<AFortTimeOfDayManager> TimeOfDayManager;
```
 - You need to rewrite this part because markdown is skunked.

- Then get out of vs and press the compile button.

## 6. After it compiled everything successfully, re-open your project

## 7. Then go to the edit tab and select Project Settings.
- From here search for World Settings Class
![Hi](https://cdn.discordapp.com/attachments/894281085393977408/894289294242508810/unknown.png "")
- Change it to Fort World Settings
- ![Hi](https://media.discordapp.net/attachments/894281085393977408/894289424668561448/unknown.png?width=1103&height=304 "")

## 8. Then compile the project again and open your map
- In case you dont have the World Settings menu on the right side of UE4, open the Window tab

![image](https://user-images.githubusercontent.com/72986221/135766739-74756250-3d2e-405b-b322-c2019c42454a.png)

- And press on World Settings

![image](https://user-images.githubusercontent.com/72986221/135766748-82763c43-d449-4b79-ba78-988c0a95a692.png)
![image](https://user-images.githubusercontent.com/72986221/135766774-9f235bee-d1ad-4461-aace-de6a403bfa0a.png)

- Here you will find the Time Of Day Manager variable you have just made, now go back to the Content folder

![image](https://user-images.githubusercontent.com/72986221/135766796-b0f64964-a97b-4907-b445-b2a3594bea48.png)
- Make a folder called TimeOfDay

![image](https://user-images.githubusercontent.com/72986221/135766806-0c8bc393-0dd4-48f9-95b2-bd71f3baebc7.png)
- And inside of it another one called TODM

![image](https://user-images.githubusercontent.com/72986221/135766811-10005f7f-65a1-43c0-8d88-77dde746182c.png)
- And another one inside of it called BR

![image](https://user-images.githubusercontent.com/72986221/135766818-fc6bb3a5-7e62-48e9-98e5-8dfba08ecf4b.png)

- Then just follow what i did on the gif

![image](https://cdn.discordapp.com/attachments/894281085393977408/894294585872875540/ezgif-2-d1035d703103.gif)

- After that make a new c++ class thats a child of PlayerStart and call it FortPlayerStartWarmup

![image](https://user-images.githubusercontent.com/72986221/135767066-750487ba-51be-4f92-92c5-d5ce7df2b5a3.png)

![image](https://user-images.githubusercontent.com/72986221/135767105-b597d8ac-4a91-4442-82e5-9e5b217632f5.png)

Search for it here and place it on the map 

## 9. You are done! Now go to the File tab and press the Cook content for windows button.

![image](https://user-images.githubusercontent.com/72986221/135767386-70b085e4-c42f-469f-8ea1-8acb7242851f.png)


## 10. Go to the folder with your project

![image](https://user-images.githubusercontent.com/72986221/135767509-283110b9-da11-4ab7-9b71-4c3a6fd7c781.png)

- Go to the saved->cooked->windowsnoeditor->fortnitegame->content folder
- Copy the Maps folder from here.
> Download u4pak https://cdn.discordapp.com/attachments/894281085393977408/894324308950798406/u4pak.zip
- Unpack it and create a folder inside of it called FortniteGame, then another one inside of FortniteGame called Content, and here paste your Maps folder.

![image](https://user-images.githubusercontent.com/72986221/135767761-45142c84-8517-4eed-a692-ce826d213d05.png)

- Then just drag the FortniteGame folder on the bat.

![image](https://user-images.githubusercontent.com/72986221/135767774-800e5657-50e7-43bd-a01e-985493f3b290.png)

- Congrats, you made a pak file. Rename it to whatever you want (make sure it starts with "pakchunk" and ends with -WindowsClient")

## 11. Put the pak file inside of the Paks folder.
- Copy the pak file and put it inside of the Paks folder of the fortnite version you are modding

![image](https://user-images.githubusercontent.com/72986221/135767841-f90697f8-db11-41dd-96c4-ae4290090afd.png)

- For 7.10/7.30 i recommend this sig
> https://cdn.discordapp.com/attachments/894281085393977408/894298941607280640/pakchunk2521-WindowsClient.sig
- For the other builds just copy and rename the smallest one thats in the Paks folder and rename it so the name of it is equal to the name of the custom pak you have just made.

## 12. Now launch your game using the era launcher, then in the lobby open the console and type "open /Game/Maps/{YourMapName}?game=/game/athena/athena_gamemode.athena_gamemode_c"

** NOTE: You will be probably loading into the map for like 2-4 minutes, thats normal and danii is working on a fix already!**








## Fun stuff!

> Minecraft block material.
![image](https://user-images.githubusercontent.com/72986221/135770573-103c73e9-ffc8-4ad7-9435-fc80857b23b3.png)
![image](https://user-images.githubusercontent.com/72986221/135770576-42053f47-810d-40d0-accf-e08a4a313791.png)
![image](https://user-images.githubusercontent.com/72986221/135770579-d7198098-b40b-414c-b5d2-cdb20182763c.png)


# Cube material.

- Rune material function
 ![image](https://user-images.githubusercontent.com/72986221/135770622-249084ac-50a3-4327-bd47-86365854737c.png)

- Base color material function
![image](https://user-images.githubusercontent.com/72986221/135770654-027f3ca7-05c1-48f8-8da6-41ff521cab26.png)
![image](https://user-images.githubusercontent.com/72986221/135770659-8ffabd88-5990-47bb-ac12-55935bcf2068.png)

- Smooth sphere gradient material function
![image](https://user-images.githubusercontent.com/72986221/135770670-825afcce-90d7-4925-9670-f23182298c2f.png)

- RuneMask material function (Makes the runes move and disappear in some places)
![image](https://user-images.githubusercontent.com/72986221/135770688-2b83a9c7-ea5d-4a69-8696-fc22592ea782.png)

- CubePurple Emissive Material function (The main material function)
![image](https://user-images.githubusercontent.com/72986221/135770710-704f4cc0-2a54-4448-8527-6648ab7f1d12.png)
![image](https://user-images.githubusercontent.com/72986221/135770711-6d5777b5-77ca-4563-8049-b49f507b2a95.png)
![image](https://user-images.githubusercontent.com/72986221/135770714-223ccb15-7429-4862-b516-9d52f7358624.png)

- The material it self.
![image](https://user-images.githubusercontent.com/72986221/135770719-83f3f723-3721-4d7c-a8fb-6c12ef2addda.png)

> Material instance values
![image](https://user-images.githubusercontent.com/72986221/135770749-0ca51243-b091-41e5-95c9-e5d937a4c752.png)


**Effect:**
![image](https://user-images.githubusercontent.com/72986221/135770738-a9812536-f32f-4cf6-ae68-edb6c8468571.png)


## Level sequences
Using them you can make a cutscene or your own "event".

![image](https://user-images.githubusercontent.com/72986221/135770793-5d5f4755-fa99-4a8f-a5ab-8f07dbf0ee9d.png)

> Press on Cinematics

![image](https://user-images.githubusercontent.com/72986221/135770801-2270630d-1161-44b8-9961-cbdcbd6507ef.png)

> Add level sequence

![image](https://user-images.githubusercontent.com/72986221/135770813-7827cc7a-6557-44af-891d-7612af1aa64f.png)

- Now watch some youtube tutorials about how level sequences work, if you want to trigger some events on the player then use the Event Track 
https://docs.unrealengine.com/4.26/en-US/AnimatingObjects/Sequencer/Workflow/EventTrackOverview/

## Box Trigger

- Make a new actor

![image](https://user-images.githubusercontent.com/72986221/135770878-4f0bdf9b-4ff3-4f5c-bc12-fbc3d6555b2b.png)

- Add an box collision component

![image](https://user-images.githubusercontent.com/72986221/135771033-b8c3b9b4-684b-4484-bd7d-c382d010be23.png)
- Resize it

- Scroll down in details and press + on Component begin overlap

![image](https://user-images.githubusercontent.com/72986221/135771047-fe034b66-f440-4168-a957-d3ce38df8ea9.png)

- Call whatever function you want.

Example:
![image](https://user-images.githubusercontent.com/72986221/135771149-696187dd-c871-45c5-972c-d6e1dbdbd15d.png)

## Random Minecraft World Generation

- Make a blueprint that has a default cube mesh component inside of it

- Make a blueprint called BP_WorldGenerator

- Recreate this https://blueprintue.com/blueprint/gpj2zfpq/

![image](https://user-images.githubusercontent.com/72986221/135771291-40459a9c-f983-49b1-bfd4-71c975982d40.png)
![image](https://user-images.githubusercontent.com/72986221/135771293-0d7d71f4-0865-4987-8752-9a162eea6589.png)


