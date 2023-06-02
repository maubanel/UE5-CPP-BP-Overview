![](../images/line3.png)

### Blueprint Iteration

<sub>[previous](../operators-ii/README.md#user-content-blueprint-operators-ii) • [home](../README.md#user-content-ue5-bp-overview) • [next](../iteration-ii/README.md#user-content-blueprint-iteration-ii)</sub>

![](../images/line3.png)

Lets add a stat to a game object and use a switch statement to change messages. Now iterating loops in Blueprints can be a bit unwieldly.  This is one area where I think **C++** is a bit easier to read and elegant than the amount of pins often needed in an iteration in a blueprint.

<br>

---

##### `Step 1.`\|`BPOVR`|:small_blue_diamond:

Select the **Blueprints** folder and right click in the open area and selet **Blueprint Class** and press the <kbd>Actor</kbd> button.  Name this new Blueprint `BP_State`.

![Create BP_State actor blueprint](images/bpState.png)

![](../images/line2.png)

##### `Step 2.`\|`BPOVR`|:small_blue_diamond: :small_blue_diamond: 

For visual interest add a **Cube** component.  This will simulate an actor with a thought bubble above their head.  Add a **TextRender** component and call it `State Description`.  Change the **Text** to `I am `, the **Horizontal Alignment** and **Vertical Alignment** to `Center` and `TextCenter` and the **Text Render Color** to the same color we have been using.  Finally change the **World Size** to `72`.  Adjust the height of the text so it is above the cube.

![add cube and textrender component to hold the state](images/addComponents.png)

![](../images/line2.png)

##### `Step 3.`\|`BPOVR`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/addStateVar.png)

![](../images/line2.png)

##### `Step 4.`\|`BPOVR`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/switchOnInt.png)

![](../images/line2.png)

##### `Step 5.`\|`BPOVR`| :small_orange_diamond:

![alt_text](images/addDescriptionText.png)

![](../images/line2.png)

##### `Step 6.`\|`BPOVR`| :small_orange_diamond: :small_blue_diamond:

![alt_text](images/setSwitch0.png)

![](../images/line2.png)

##### `Step 7.`\|`BPOVR`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](imagessequenceNode1/.png)

![](../images/line2.png)

##### `Step 8.`\|`BPOVR`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/addStateDescriptionText.png)

![](../images/line2.png)

##### `Step 9.`\|`BPOVR`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

![alt_text](images/runSwitch0.png)

![](../images/line2.png)

##### `Step 10.`\|`BPOVR`| :large_blue_diamond:

![alt_text](images/AddMoreSwitchCases.png)

![](../images/line2.png)

##### `Step 11.`\|`BPOVR`| :large_blue_diamond: :small_blue_diamond: 

![alt_text](images/state200.png)

![](../images/line2.png)

##### `Step 12.`\|`BPOVR`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: 

![alt_text](images/instanceEditable.png)

![](../images/line2.png)

##### `Step 13.`\|`BPOVR`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

![alt_text](images/randomeChange.png)

![](../images/line2.png)

##### `Step 14.`\|`BPOVR`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

![alt_text](images/resetTextInLoop.png)

![](../images/line2.png)

##### `Step 15.`\|`BPOVR`| :large_blue_diamond: :small_orange_diamond: 

Press the <kbd>Play</kbd> button.

https://github.com/maubanel/UE5-BP-Overview/assets/5504953/d96c3b09-d3ea-415b-866c-8bf431b0d2e6

![](../images/line.png)

<!-- <img src="https://via.placeholder.com/1000x100/45D7CA/000000/?text=Next Up - Iteration Continued"> -->

![next up - ](images/banner.png)

![](../images/line.png)

| [previous](../operators-ii/README.md#user-content-blueprint-operators-ii)| [home](../README.md#user-content-ue5-bp-overview) | [next](../iteration-ii/README.md#user-content-blueprint-iteration-ii)|
|---|---|---|
