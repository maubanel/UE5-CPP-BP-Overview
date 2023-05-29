![](../images/line3.png)

### Setting Up Unreal

<sub>[home](../README.md#user-content-ue5-bp-overview) • [next](../)</sub>

![](../images/line3.png)

It is easiest to manage the various versions of Unreal using the **Epic Launcher**.  Thi allows you to install and run multiple versions of the engine.  Go to [Epic Launcher Download](https://store.epicgames.com/en-US/download) and install the Epic Game Launcher.  From here we will manage our game assets and resources. Intall Unreal 5.2 and use a PC.

<br>

---

##### `Step 1.`\|`BPOVR`|:small_blue_diamond:

You will need to have an account with Epic games, but don't worry they are free to register for.  Unreal Engine 4 is freely available for students.
Once you have installed the launcher run the program and select **Unreal Engine** on the side menu and **Library** on the top menu. Press the **+** button to add a new build (if needed) and select the latest version.  In my case it is `5.2.X`. Make sure it is of version `5.2.x` if you want to ensure that you are compatible with this walk through (the third digit should work as these represent non-breaking changes to the engine and just bug-fixes).

Also, before installing select **Options** and only download platforms you need support (PC is built in).  So I saved some space by removing hand held versions of the engine. We also do not need the **Editor symbols for debugging** yet so we can save ~60 gigs here by not including it.  You can add these at any time in the future.

![install unreal 5.2 on your PC](images/MakeSureUnreal52.png)

![](../images/line2.png)

##### `Step 2.`\|`BPOVR`|:small_blue_diamond: :small_blue_diamond: 

Now once it installs press the **Launch** button on the **5.2.X** version of Unreal.

![launch Unreal](images/launchGame.png)

![](../images/line2.png)

##### `Step 3.`\|`BPOVR`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

This brings up the **Unreal Project Browswer** window.  This allows you to select templates with the key assets already implemented.  We will select from the **Games** templates a **Blank** project. We will start with a **Blueprint** project.  Leave the quality at **Maximum Quality**, **Raytracing** disabled, a target platform of **Desktop** and we have **No Starter Content**. Then select a folder and call the project `BPOverview`. Press the **Create** button.

![alt_text](images/BlankGame.png)

![](../images/line2.png)

##### `Step 4.`\|`BPOVR`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

You should get to a project screen with an **Untitled** map with some elements already placed for you in the **World Outliner**.  Now even though we selected a blank template, Unreal gives you a whole set of base functionality out of the gate. 

![untitled level](images/untitledLevel.png)

![](../images/line2.png)

##### `Step 5.`\|`BPOVR`| :small_orange_diamond:



![alt_text](images/NewLevel.png)

![](../images/line2.png)

##### `Step 6.`\|`BPOVR`| :small_orange_diamond: :small_blue_diamond:

![alt_text](images/.png)

![](../images/line2.png)

##### `Step 7.`\|`BPOVR`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:
You see an **Atmospheric Fog** which adds some fog to the scene (sometimes used to cut down draw calls for distant objects), a floor to move around on, a light source simulating the sun a **Player Start** object that decides where the player gets spawned when the level starts, a **Sky Sphere** that contains the sky and sun in a round ball that we are inside of, a **SkyLight** that imitates bounced lights so that the shadows are not as sharp and there is detail in parts of then scene that don't have direct sun and finally a **SpereReflector** object that handles reflecting objects in shiny surfaces.  We will just leave all of this alone, and you can hit the **Play** button and notice that nothing happens but you can move around the scene with the arrow buttons.

![alt_text](images/.png)

![](../images/line2.png)

##### `Step 8.`\|`BPOVR`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/.png)

![](../images/line2.png)

##### `Step 9.`\|`BPOVR`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/.png)

![](../images/line2.png)

##### `Step 10.`\|`BPOVR`| :large_blue_diamond:

![alt_text](images/.png)

![](../images/line2.png)

##### `Step 11.`\|`BPOVR`| :large_blue_diamond: :small_blue_diamond: 

![alt_text](images/.png)

![](../images/line2.png)

##### `Step 12.`\|`BPOVR`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: 

![alt_text](images/.png)

![](../images/line2.png)

##### `Step 13.`\|`BPOVR`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

![alt_text](images/.png)

![](../images/line2.png)

##### `Step 14.`\|`BPOVR`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

![alt_text](images/.png)

![](../images/line2.png)

##### `Step 15.`\|`BPOVR`| :large_blue_diamond: :small_orange_diamond: 

![alt_text](images/.png)

![](../images/line2.png)

##### `Step 16.`\|`BPOVR`| :large_blue_diamond: :small_orange_diamond:   :small_blue_diamond: 

![alt_text](images/.png)

![](../images/line2.png)

##### `Step 17.`\|`BPOVR`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/.png)

![](../images/line2.png)

##### `Step 18.`\|`BPOVR`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/.png)

![](../images/line2.png)

##### `Step 19.`\|`BPOVR`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/.png)

![](../images/line2.png)

##### `Step 20.`\|`BPOVR`| :large_blue_diamond: :large_blue_diamond:

![alt_text](images/.png)

![](../images/line2.png)

##### `Step 21.`\|`BPOVR`| :large_blue_diamond: :large_blue_diamond: :small_blue_diamond:

![alt_text](images/.png)

![](../images/line.png)

<!-- <img src="https://via.placeholder.com/1000x100/45D7CA/000000/?text=Next Up - ADD NEXT PAGE"> -->

![next up - ](images/banner.png)

![](../images/line.png)

| [home](../README.md#user-content-ue5-bp-overview) | [next](../)|
|---|---|
