![](../images/line3.png)

### Blueprint Iteration II

<sub>[previous](../iteration/README.md#user-content-blueprint-iteration) • [home](../README.md#user-content-ue5-bp-overview)</sub>

![](../images/line3.png)

Now loops are similar to switch statements and again, can contain lots of execution pins.  Keep your graph clean and organized.

<br>

---

##### `Step 1.`\|`BPOVR`|:small_blue_diamond:

Select the **Blueprints** folder and right click in the empty folder area to add a **Blueprint Class** of type **Actor** called `BP_Loops`.

![add BP_Loops actor blueprint](images/BPLoopActor.png)

![](../images/line2.png)

##### `Step 2.`\|`BPOVR`|:small_blue_diamond: :small_blue_diamond: 

Add two **Text Render** components renaming the first to `ForLoop` and second to `WhileLoop`.

![add two text render components](images/forWhileLoop.png)

![](../images/line2.png)

##### `Step 3.`\|`BPOVR`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Select the **ForLoop** component and set the **Text** to `For Loop`, the **Horizontal Algnment** to `Center` and **Vertical Alignment** to `TextCenter`.  Change the **Text Render Color** to the color you have been using (cut and paste it) and the **World Size** to `72`.

![fill in for loop component details](images/forLoop.png)

![](../images/line2.png)

##### `Step 4.`\|`BPOVR`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Repeat this for the **WhileLoop** component keeping everything the same as the above except make the **Text** say `While Loop`.

![fill in while loop component details](images/whileLoop.png)

![](../images/line2.png)

##### `Step 5.`\|`BPOVR`| :small_orange_diamond:

Create an **Integer** variable and call it `WhileInt`.  Make sure **Private** is set to `true`.  Lets start with a while loop.  *Right click* on the graph and select a **While Loop** node.

![while loop node](images/whileInt.png)

![](../images/line2.png)

##### `Step 6.`\|`BPOVR`| :small_orange_diamond: :small_blue_diamond:

Notice the **While Loop** has a **Condition** pin.  This is similar to `while (WhileInt < 10) {}` in C++.  So we drag a **Get WhileInt**t o the graph and send it to a **Less Than (<)** node.

![while int to < node](images/whileCondition.png)

![](../images/line2.png)

##### `Step 7.`\|`BPOVR`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

Connect the output of the **<** node to the **While Loop** condition bool.  Add another **Get WhileInt** node and select the data pin and choose a **++** increment node that will increment this variable by 1.  Connect it to the **Loop Body** pin.  This way when it reaches `10` it will fall out of the loop.  WIthout this, we would have an infinite loop.

![add increment during loop](images/whilePlusPlus.png)

![](../images/line2.png)

##### `Step 8.`\|`BPOVR`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Select all the nodes and add a **Comment** box by pressing the <kbd>C</kbd> key.  Call this comment box `While Loop`.

![add comment box](images/addComment.png)

![](../images/line2.png)

##### `Step 9.`\|`BPOVR`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Create a variable to hold concatonated numbers.  Lets make is a **String** type and call it `While String` making it **Private**. Drag the **While String** to the graph and add an **Append** string node with the **While String** going into **A**, the **B** pin set to `, `.  Press the **Add Pin** and add the output of the **++** node to the **C** pin (it will add an int to string conversion node).

![add commas between strings](images/appendString.png)

![](../images/line2.png)

##### `Step 10.`\|`BPOVR`| :large_blue_diamond:

Finally add a **Set WhileString** node and put the output of the **Append** node to the **While String**.  Connect the execution pin of the **++** node to the **Set While** string.

![set WhileString with concatonated value](images/setWhileString.png)

![](../images/line2.png)

##### `Step 11.`\|`BPOVR`| :large_blue_diamond: :small_blue_diamond: 

Drag off of the **While Loop | Completed** execution pin and add a **While Loop** and **Set Text** nodes.  Drag a **Get WhileString** node and connect it to the **Set Text | Value** pin. The engine will convert from a **String** to a **Text**.

![alter string](images/completedSetText.png)

![](../images/line2.png)

##### `Step 12.`\|`BPOVR`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: 

Go to the game engine and add a **BP_Loop** to the level and place it.  Make sure it is in the **Blueprint Types** folder in the details panel.

![add BP_Loop to game](images/bpLoopsInGame.png)

![](../images/line2.png)

##### `Step 13.`\|`BPOVR`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

Press the <kbd>Play</kbd> button and notice that we have an extra comma at the begining we don't want. Lets fix that.

![extra comma bug in game](images/commaBug.png)

![](../images/line2.png)

##### `Step 14.`\|`BPOVR`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:  :small_blue_diamond: 

So we want the first element to not add a comma.  So after the `++` increment integer node we add a **Branch Node**.  Since the **WhileLoop** integer starts at `0` the first number coming out of `++` will be `1`.  Drag a reference to **WhileInt** and add a **>** node and add `1` to the bottom field.  Plug the output of the **>** node to the **Branch** node.  Send the **Branch | True** pin to the **Set WhileString** node.  Now in the **Branch | False** pin send it to another **Set WhileString** node sending it just the **Get WhileInt** variable.

![fix comma bug](images/fixCommaBug.png)

![](../images/line2.png)

##### `Step 15.`\|`BPOVR`| :large_blue_diamond: :small_orange_diamond: 

Figure out on your own how to get a **For Loop** to print out the following:

````0, -10, -20, -30, -40, -50```

Now I believe on a blueprint for loop you can only increment (I don't think you can decrement) and it always increments by `1`.  So it is quite limiting compared to the syntax of a **C++ For Loop** where you can go in any diretion incremented by any amount.

![for loop](images/forLoopOnYourOwn.png)

![](../images/line2.png)


![alt_text](images/.png)

![](../images/line.png)

<!-- <img src="https://via.placeholder.com/1000x100/45D7CA/000000/?text=Next Up - The End!"> -->

![next up - ](images/banner.png)

![](../images/line.png)

| [previous](../iteration/README.md#user-content-blueprint-iteration)| [home](../README.md#user-content-ue5-bp-overview) |
|---|---|
