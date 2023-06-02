![](../images/line3.png)

### Blueprint Operators

<sub>[previous](../text/README.md#user-content-names-strings-text) • [home](../README.md#user-content-ue5-bp-overview) • [next](../)</sub>

![](../images/line3.png)

Lets create a countdown timer and see how we use operators which is a bit different in Blueprints compared to doing it in C++.

<br>

---

##### `Step 1.`\|`BPOVR`|:small_blue_diamond:

Select the **Blueprints** folder and right-click in the open folder and select an **Blueprint Class** and select **Actor**.  Call the new blueprint `BP_Countdown`.

![create BP_Countdown](images/countdownBP.png)

![](../images/line2.png)

##### `Step 2.`\|`BPOVR`|:small_blue_diamond: :small_blue_diamond: 

Open up **BP_Countdown** and add a **Text Render** component.  Chnage the name to `CountdownTimer`.  Copy and paste the **Text Render Color** so it is the same as the others. Change the **Horizontal Alignment** and **Vertical Alignment** to `Center` and `TextCenter`. Change the **Text** to `Countdown Timer` and the **World Size** to `72`.

![add CountdownTimer component and format text](images/countdownTimerComponent.png)

![](../images/line2.png)

##### `Step 3.`\|`BPOVR`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

This time we will not use the **Begin Play** but instead use the **Tick Event**.  In Unreal Engine, a **Tick Event** refers to a specific type of event that occurs every frame or at a regular interval. It is commonly used to update and control the behavior of objects or actors within the game world.

Think of the game world as a continuous flow of time, divided into small increments called frames. Each frame represents a snapshot of the game's current state, including the positions and properties of all objects. 

During each frame, the engine goes through various processes, such as rendering graphics and handling player input. In addition, it triggers tick events for objects that have been set up to receive them.

When an object receives a tick event, it means that the engine is giving it an opportunity to perform some actions or calculations. For example, an enemy character might use the tick event to update its position, check for collisions with other objects, or react to player input.

The tick event is called repeatedly, typically 30 or 60 times per second, depending on the frame rate of the game. This regular repetition ensures that objects can constantly update and respond to changes in the game world, providing smooth and interactive gameplay.

By utilizing the tick event, game developers can create dynamic and responsive behaviors for objects in Unreal Engine, making the game world come alive with movement and interactivity.

Drag the **Countdown Timer** to the graph and drag off the pin and add a **Set Text** node.  Now we will take the **Delta Seconds** pin and send it to the **Set Text | Value** pin.

![set text with delta time](images/deltaSecondsEventTick.png)

![](../images/line2.png)

##### `Step 4.`\|`BPOVR`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Drag a copy of **BP_Countdown** into the scene.  In the **Outliner** create a folder called `Blueprint Types` and move all the blueprints into the folder to clean up the outliner.

![add BP_Countdown to scene](images/putInFolder.png)

![](../images/line2.png)

##### `Step 5.`\|`BPOVR`| :small_orange_diamond:

Press the <kbd>Play</kbd> button and you see that it gives you the amount of time that past since last tick in milliseconds (ms).  Now we see that we have a consistent framerate of .017 milliseconds (ms).  1s/.017ms = 58 FPS. But this is not counting down.  What we need to do is subtract this amount from our timer which we will do.

https://github.com/maubanel/UE5-BP-Overview/assets/5504953/1adddd01-1e6f-4bad-9ee3-809c5c677a9a

![](../images/line2.png)

##### `Step 6.`\|`BPOVR`| :small_orange_diamond: :small_blue_diamond:

We will be counting down and need a variable to hold this time.  Create a new **float** variable called `GameTime`.

![create Game Time variable](images/createGameVar.png)

![](../images/line2.png)

##### `Step 7.`\|`BPOVR`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

Drag a **Get GameTime** variable onto the graph.  Add a **Subtraction** node.  Put the **GameTime** output to the top of the **Subtraction** node.  Then take **Event Tick | Delta Seconds** output pin and attach it to the bottom of the subtraction node.

![subtract delta seconds from gametime](images/subtractFromGametime.png)

![](../images/line2.png)

##### `Step 8.`\|`BPOVR`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now drag a **Set GameTime** variable to the graph.  Send the output of the **Subtraction** node to the **Set GameTime** data pin.  Send the output of **Game Time** node to **Set Text**.  Connect the execution pin from **Event Tick** to **Set GameTime** to **Set Text**. Set the default value for **GameTime** to `10` as we will countdown from 10 seconds. The fraction is causing the text to jitter.

![set game time](images/setGameTime.png)

![](../images/line2.png)

##### `Step 9.`\|`BPOVR`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Press the <kbd>Play</kbd> button and the time countdowns.

https://github.com/maubanel/UE5-BP-Overview/assets/5504953/9f56cc44-ab09-4dc3-a158-40f2e7b3bfb6

![](../images/line2.png)

##### `Step 10.`\|`BPOVR`| :large_blue_diamond:

Open up the arrow for advanced settings of the **To Text** node.  Set **Maximum Fractional Digits** to `0`. Pull off of the **To Text | Return Value** and select a **Format Text** node.

![set fraction to 0 and format text](images/noFracFormat.png)

![](../images/line2.png)

##### `Step 11.`\|`BPOVR`| :large_blue_diamond: :small_blue_diamond: 

In the **Format Text** node add

```
Countdown Timer
{A}
```

This adds an **A** pin which you will connect to **To Text**.  THen take the **Format Text | Result** node and send it to the **Set Text | Value** pin.

![add title to text](images/addCountdownTimer.png)

![](../images/line2.png)

##### `Step 12.`\|`BPOVR`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: 

Press the <kbd>Play</kbd> button and now we have a title and the seconds are just whole numbers and no fractions.

RECORD NEW VIDEO

![](../images/line2.png)

##### `Step 13.`\|`BPOVR`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

Select all of your nodes then press the <kbd>C</kbd> key.  Add `Countdown Timer` to title of comment box.  Pick a unique color.

![add comment to nodes](images/countdownTimeComments.png)

![](../images/line2.png)

##### `Step 14.`\|`BPOVR`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

Now the one bug we have is that the timer doesn't stop when it gets to `0`.  It goes to negative numbers.  Lets fix that.

![timer goes below 0](images/countdownNegative.png)

![](../images/line2.png)

##### `Step 15.`\|`BPOVR`| :large_blue_diamond: :small_orange_diamond: 

There are no **if** statements in blueprints.  Instead we have a **Branch** node.  This replaces, if, elseif and else nodes and can all be done with the **Branch** node. Add a **Branch** node and we will check if the value is less than 0.


![add branch node](images/ConditionIf.png)

![](../images/line2.png)

##### `Step 16.`\|`BPOVR`| :large_blue_diamond: :small_orange_diamond:   :small_blue_diamond: 

Add a **Less Than (<)** node and plug the output to the **Branch** input.  Take the output of the **Subtraction** node and plug it into the top of the **<** node.

![add less than node](images/conditionPin.png)

![](../images/line2.png)

##### `Step 17.`\|`BPOVR`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

Move the nodes below and connect the **Branch | False** pin to the **Set GameTime** node. This is when the the value is NOT less than 0 we will print the value as is.

![alt_text](images/setGameFalse.png)

![](../images/line2.png)

##### `Step 18.`\|`BPOVR`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Sn now if it is less than 0, then we add a **Set GameTime** node and leave it at `0` and connect it to the **Branch | True** pin.  THen send from **Set GameTime** to the **Set Text** node to have a separate setter for the **True** and **False** paths.  Add another **Format Text** node to the **True** branch.

![add set GameTime to 0 on true branch](images/setTimeToZero.png)

![](../images/line2.png)

##### `Step 19.`\|`BPOVR`| :large_blue_diamond: :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Duplicate the **Set Text** node.
![alt_text](images/DupeSetText.png)

![](../images/line2.png)

##### `Step 20.`\|`BPOVR`| :large_blue_diamond: :large_blue_diamond:

https://github.com/maubanel/UE5-BP-Overview/assets/5504953/e28b283e-4fe1-4533-b5c2-c474e5eb9a89

![alt_text](images/.png)

![](../images/line2.png)

##### `Step 21.`\|`BPOVR`| :large_blue_diamond: :large_blue_diamond: :small_blue_diamond:

![alt_text](images/.png)

![](../images/line.png)

<!-- <img src="https://via.placeholder.com/1000x100/45D7CA/000000/?text=Next Up - ADD NEXT PAGE"> -->

![next up - ](images/banner.png)

![](../images/line.png)

| [previous](../text/README.md#user-content-names-strings-text)| [home](../README.md#user-content-ue5-bp-overview) | [next](../)|
|---|---|---|
