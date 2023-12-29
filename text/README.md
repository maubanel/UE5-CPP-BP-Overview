![](../images/line3.png)

### Names Strings Text

<sub>[previous](../fractions/README.md#user-content-fractional-numbers) • [home](../README.md#user-content-ue5-bp-overview) • [next](../operators/README.md#user-content-blueprint-operators)</sub>

![](../images/line3.png)

There are three types of text formats in **Unreal**.  It doesn't use the same **String** class as used in **C++ Standard Template Library**.  Usually for games more efficient libraries are written that sacrifice robustness for performance.

The three data types are **Names**, **Strings** and **Text**.

If you do not know about text types, it might be good to read the history of how we got here in [Unicode and Character Sets](https://www.joelonsoftware.com/2003/10/08/the-absolute-minimum-every-software-developer-absolutely-positively-must-know-about-unicode-and-character-sets-no-excuses/).

They are **FText**, **FName** and **FString**.<br><br>[FName](https://docs.unrealengine.com/en-us/Programming/UnrealArchitecture/StringHandling/FName) are used for names (non-customer facing) of items in the **Content Browser**. When you name a new asset in the Content Browser, change a parameter in a Dynamic Material Instance, or access a bone in a Skeletal Mesh. This format is 8 bytes per character. It is the smallest format and is used to refer to objects in the editor (like the name of a Material variable).  It is also the smallest format and is often used in multiplayer to reduce the size of packets sent, if text needs to be sent between client and server or vice versa. **FName** is case insensitive. It has very fast look up using hash tables.

[FString](https://docs.unrealengine.com/en-us/Programming/UnrealArchitecture/StringHandling/FString) is a 
16 byte format that allows dynamic modification as well as replace, search concatonate etc... It is less performant but is used most often for manipulation.

[FText](https://docs.unrealengine.com/en-us/Programming/UnrealArchitecture/StringHandling/FText) a 40 byte format is for all customer facing text that requires localization (Like the HUD, or buttons in the front end).<br><br>Please note that in **Blueprints** we do not have the built-in **char** ????CEHCK THIS MARC???? type. You can use it in C++ only but will not show up in **Blueprint**. 

<br>

---

##### `Step 1.`\|`BPOVR`|:small_blue_diamond:

Select the **Blueprints** folder and right click in the directory and a **Blueprint Class** and select the **Actor** class.  Call this new **Blueprint** `BP_Text`.

![new BP_Text actor blueprint](images/createBP.png)

![](../images/line2.png)

##### `Step 2.`\|`BPOVR`|:small_blue_diamond: :small_blue_diamond: 

Open up **BP_Text**. Add a **TextRender** component and call it `Text`. Change the **Text** to `Text`.  Adjust the **Horizontal Alignment** and **Vertical Alignment** to `Center` and `Text Center`.  Copy and paste the color from **BP_Frac**.  Change the **World Size** to `72`.

![set text render component](images/textRenderComponent.png)

![](../images/line2.png)

##### `Step 3.`\|`BPOVR`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Drag the **Text** component onto the graph.  Then drag off the pin and select a **Set Text** node.  Connect the execution pin to **Begin Play**.

![add text and set text nodes](images/setText.png)

![](../images/line2.png)

##### `Step 4.`\|`BPOVR`|:small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Now lets demonstrate the three text types (they will all look identical) by adding a **Make Literal String** , **Make Literal Text** and **Make Literal Name** node. Then add

`I am a string`

`I am a text`

`I am a name`

to the appropriate Literal.

![add three text literals](images/makeLiterals.png)

![](../images/line2.png)

##### `Step 5.`\|`BPOVR`| :small_orange_diamond:

Now change the **Text** to say `String-TextName`.

![change text to sting-text-name](images/stringTextNam.png)

![](../images/line2.png)

##### `Step 6.`\|`BPOVR`| :small_orange_diamond: :small_blue_diamond:

Now connect the **Make Text Literal** output to the **Set Text | Value** pin.

![alt_text](images/showText.png)

![](../images/line2.png)

##### `Step 7.`\|`BPOVR`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond:

Drag a copy of **BP_Text** to the level. Rotate it to face the camera.

![put BP_Text in game](images/dragToGame.png)

![](../images/line2.png)

##### `Step 8.`\|`BPOVR`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

Press the <kbd>Play</kbd> button and you will see it print **I am a text**.

![print text object in game](images/pressPlayText.png)

![](../images/line2.png)

##### `Step 9.`\|`BPOVR`| :small_orange_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond: :small_blue_diamond:

You can see that if we connect **Make Literal Name** to the **value** pin we will see in game **I am a name**.

![send literal name to print](images/connectNameToGame.png)

![](../images/line2.png)

##### `Step 10.`\|`BPOVR`| :large_blue_diamond:

Now when you don't initialize an `FString` or `FText`, it is an empty string "".  With an `FName` it defaults to `none` as it is used.  Delete all the text and run the game, and you will see it print none.

![name has none as text](images/nameNone.png)

![](../images/line2.png)

##### `Step 11.`\|`BPOVR`| :large_blue_diamond: :small_blue_diamond: 

To prove this go to the **Text Literal** and remove the text.  When you run the game no text prints at all (empty text).

![print empty text](images/emptyText.png)

![](../images/line2.png)

##### `Step 12.`\|`BPOVR`| :large_blue_diamond: :small_blue_diamond: :small_blue_diamond: 

Test the **String Literal** to print **I am a string**.  Put the text back to:

`I am a string`

`I am a text`

`I am a name`

![I am a string to game](images/stringWorks.png)


![](../images/line.png)

<!-- <img src="https://via.placeholder.com/1000x100/45D7CA/000000/?text=Next Up - Blueprint Operators"> -->

![next up - ](images/banner.png)

![](../images/line.png)

| [previous](../fractions/README.md#user-content-fractional-numbers)| [home](../README.md#user-content-ue5-bp-overview) | [next](../operators/README.md#user-content-blueprint-operators)|
|---|---|---|
