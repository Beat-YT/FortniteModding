# Quick tutorial on how to mod older versions of Fortnite.

## 1. Download the UE4 build that the Fortnite version you want to mod uses. 

- (For Season 4 i recommend using 4.19 as custom maps work on it, and for season 7, 4.21.)

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

**#include "FortTimeOfDayManager.h**
 
**public:**

 ![Hi]( https://media.discordapp.net/attachments/894281085393977408/894287035383283712/unknown.png "")
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
- ![image](https://user-images.githubusercontent.com/72986221/135767066-750487ba-51be-4f92-92c5-d5ce7df2b5a3.png)

![image](https://user-images.githubusercontent.com/72986221/135767105-b597d8ac-4a91-4442-82e5-9e5b217632f5.png)
Search for it here and place it on the map 

## 9. You are done! Now go to the File tab and press the Cook content for windows button.
![image](https://user-images.githubusercontent.com/72986221/135767386-70b085e4-c42f-469f-8ea1-8acb7242851f.png)

