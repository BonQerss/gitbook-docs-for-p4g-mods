---
description: Porting HD Persona models from P5R to P4G.
cover: ../../.gitbook/assets/a13338b336ac58abe821c72b19b08159 (1).jpg
coverY: 0
layout:
  cover:
    visible: true
    size: full
  title:
    visible: true
  description:
    visible: true
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# 🎭 P5R Models

{% hint style="info" %}
**GitBook tip:** Try out a range of different content types to keep folks engaged and interested in each feature, some content types work for different chunks of information
{% endhint %}

## Required tools

<table><thead><tr><th width="180">Tool</th><th>Usage</th><th></th></tr></thead><tbody><tr><td>GFD Studio</td><td>Needed for viewing P5R GMD models</td><td><a href="https://github.com/DeathChaos25/GFD-Studio">https://github.com/DeathChaos25/GFD-Studio</a></td></tr><tr><td>3DS Max</td><td>Modeling program needed for porting models.</td><td></td></tr><tr><td>GMD Import Script</td><td>The script needed for importing the .GMD and .GAP files from P5R</td><td><a href="https://drive.google.com/drive/folders/1isBtlZN7oJ3GQpYrZAiTvRsnYGhS7mzR">https://drive.google.com/drive/folders/1isBtlZN7oJ3GQpYrZAiTvRsnYGhS7mzR</a></td></tr><tr><td>GMOConv &#x26; GIMConv</td><td>Needed for converting exported FBX into usable GMO and converting textures.</td><td><a href="https://cdn.discordapp.com/attachments/925531160392658944/1038502426686259240/PSP_Tools.7z">https://cdn.discordapp.com/attachments/925531160392658944/1038502426686259240/PSP_Tools.7z</a></td></tr><tr><td>Sadoaiya</td><td>Needed for optimizing models.</td><td><a href="https://pioziomgames.github.io/programs/sadoaiya">https://pioziomgames.github.io/programs/sadoaiya</a></td></tr><tr><td>Notepad++</td><td>Recommended for fixing materials and changing texture file extensions.</td><td><a href="https://notepad-plus-plus.org">https://notepad-plus-plus.org</a></td></tr><tr><td>GMOView</td><td>Checking your model visually.</td><td><a href="https://cdn.discordapp.com/attachments/925531160392658944/1038502426686259240/PSP_Tools.7z">https://cdn.discordapp.com/attachments/925531160392658944/1038502426686259240/PSP_Tools.7z</a></td></tr><tr><td>GMO2AMD Python Script<br></td><td>Adding the AMD header to GMO files.</td><td><a href="https://github.com/Timo654/gmo2amd">https://github.com/Timo654/gmo2amd</a></td></tr><tr><td>A complete dump of the game.</td><td>For working with any and all files.</td><td>I obviously can't link you this.</td></tr></tbody></table>

## Before you get started

First, you need to find the model you want to import by dumping it from your own copy of P5R. P5R Persona models are located at model/character/persona, you can find which ID goes with what Persona by checking this [list](https://amicitia.miraheze.org/wiki/Persona\_5\_Royal/Personas).

Next, open up GFD studio and drag your .GMD file inside to verify it's the one you want to work with. Also, drag the corresponding .GAP file inside to check its animations.\


<figure><img src="https://cdn.discordapp.com/attachments/728860176198926437/1127685531933884577/image.png" alt=""><figcaption></figcaption></figure>

<figure><img src="https://cdn.discordapp.com/attachments/728860176198926437/1127685749270118430/image.png" alt=""><figcaption></figcaption></figure>

To move the camera position, hold the middle mouse button and drag to move. To rotate the camera position, hold Alt and then drag along to rotate.

When working with Persona model mods for P5R that don't contain GAP files, try using the same GAP file for the model from your base files.

All good? You can continue with the rest of the guide.

## Model Importing

Open 3DS Max.

Click Script > Run Script > then open the 3DS Max Import Script, a new window should pop up that looks like this:&#x20;

<figure><img src="https://cdn.discordapp.com/attachments/728860176198926437/1127686225390739526/image.png" alt=""><figcaption></figcaption></figure>

Click Import File.

Navigate to your model and add the model that starts with "ps0."

Click Load Model in 3DS Max.

The model will be rotated and aligned to the floor, carry on for now.

Click Import File again.

Load the .GAP file for the model, the file you need should start with "bps."

The animation it loads is dependent on the animation index value, it has the same range as the animation count shown in GFD Studio.

## Model Importing pt. 2

Once an animation is selected, click load animation.

Next, play the animation by clicking the white triangle play button in the bottom right to verify animations are working.&#x20;

<figure><img src="https://cdn.discordapp.com/attachments/728860176198926437/1127626528172298280/image.png" alt=""><figcaption></figcaption></figure>

If the animations are working, move to the left side of the screen and locate a bone titled "root\_bone" or "bone\_root" or anything similar.                                                                                       &#x20;

<figure><img src="https://cdn.discordapp.com/attachments/728860176198926437/1127627291900514335/image.png" alt=""><figcaption></figcaption></figure>

Select it by clicking it, then move over to the rotation option at the top, it's a white arrow that forms a circle.       &#x20;

&#x20;&#x20;

<figure><img src="https://cdn.discordapp.com/attachments/728860176198926437/1127627472826011809/image.png" alt=""><figcaption></figcaption></figure>

Right-click the rotate option, and set all the values to 0 by overwriting the old value.

You want the model to be facing upright and towards the back of the scene. First, orientate the camera view by clicking and dragging the white cube in the top right so that the face it's centered on says "back."&#x20;

Next, adjust the values so that the model is positioned upright and facing toward the camera. (Typically you'd put 90 for the X value and 180 for the Z value, but you can mess around with it to your liking.) Your model view should look something like this once you're done.&#x20;

<figure><img src="https://cdn.discordapp.com/attachments/728860176198926437/1127687846900289626/image.png" alt=""><figcaption></figcaption></figure>

Once you've assured that everything is correct, click File > Export > Export in the top left.

Save the model as something easy to keep track of like the Persona name followed by the animation name.

In the export settings, change the export to FBX Ascii 2009 for full compatibility with GMOConv

<figure><img src="https://cdn.discordapp.com/attachments/728860176198926437/1127628552918007839/image.png" alt=""><figcaption></figcaption></figure>

Repeat those same steps for the remaining animations.

## Smooth Magic Animation (Optional)

This next part is entirely optional, but it's an added bonus. In this section, I'll describe how to merge animations 6-10 to create a fluid Magic animation like in P5R.

## Model Converting

Once you have all 3 of your fbx files for the model, you'll need to merge them as a single model with all 5 motions. Open up a command prompt next to GMOConv and type in a command like this

`gmoconv 'Phys.fbx' 'Skill.fbx' 'Phys.fbx' 'Skill.fbx' 'Idle.fbx' -motions`

This will merge all of the animation data into a single GMO file for use in P4G. It should have merged all of them into the first model entered in the command prompt, so let's continue working with that one.&#x20;

To verify that the process worked, open up GMOView and drag your GMO file in. Press 2 on your keyboard to open up the animation config and flick through them to ensure that the process went over smoothly. Here's an example of what I mean:\


<figure><img src="https://cdn.discordapp.com/attachments/728860176198926437/1127631666639286323/Untitled-1.png" alt=""><figcaption></figcaption></figure>

&#x20;You should have a total of 5 animations, the first 4 being Phys and Skill repeated twice, and the last one being an Idle position for use in the Compendium.

Once you've verified that the model is working, you can move on to texture importing.

## Texture Importing

While converting with gmoconv, you may have noticed it was throwing out errors about being unable to convert DDS to TM2, in this section we'll fix that.

NOTE: For Vita users, you'll need to take an extra step to prevent crashes on original hardware. Instead of converting DDS directly to TM2, first, convert the DDS to PNG, halve the resolution, then convert the PNG to TM2.

First, we need to check which DDS files are actually necessary. You'll want to extract your GMO as a GMS using GMOConv for this, so pass an argument like this:

`gmoconv -S 'path to gmo'`

At the bottom, it should state which textures it attempted to import, including the path and extension, we'll edit this later.

Open a command prompt at the location where gimconv is located and pass an argument like this for each necessary dds file:

`gimconv 'path to dds' -o 'output path for new tm2'`

Now that you've converted all of your DDS textures to TM2, we'll need to import them into the model. Go back to the .GMS file you opened in a text viewer and find the Texture locations near the bottom. You'll want to change the path to where your newly made .TM2s are, and change the extension to .TM2 as well.

Your file should look something like this:

<figure><img src="https://cdn.discordapp.com/attachments/728860176198926437/1127694955062767636/Untitled-3.png" alt=""><figcaption><p>Shown here are both Notepad++ and the stock Notepad app in Windows</p></figcaption></figure>

When converting with GMOConv, if you place the .TM2 next to the .GMS, you won't have to put the full path, just the file name.

Convert the GMS back to GMO with GMOConv by dragging the .GMS over the exe.

With your newly made GMO, check it again in GMOView. Assuming the process went right, your model should now be fully textured. If you missed any during the editing process, GMOView will let you know with a warning on the left.    &#x20;

<figure><img src="https://cdn.discordapp.com/attachments/728860176198926437/1127689193410281504/image.png" alt=""><figcaption></figcaption></figure>

Once you've verified that the model has all the necessary textures, convert the GMO to AMD with the Gmo2Amd python script and continue with the rest of the guide

## Testing in game

To get your model in game for testing, it's easiest to replace an existing model before beginning on giving it its own unique slot. You can find the model you intend to replace by checking this [page](https://amicitia.miraheze.org/wiki/Persona\_4\_Golden/data.cpk/model/persona).

Once in the game with the mod applied, you'll need to verify three things, its compendium position and scaling, its fusion position and scaling, as well as its battle position and scaling. Test the model in all 3 scenarios and verify that the positioning is to your liking. I've attached an example of what is and isn't right:&#x20;

<figure><img src="https://cdn.discordapp.com/attachments/728860176198926437/1127697043939405934/Untitled-2.png" alt=""><figcaption></figcaption></figure>

Your model should be fully viewable without any parts out of frame. It should also take up most of the space on the right.

If the model positioning and scaling are correct, and everything else works, then you've successfully imported a custom model! If the model position and scaling isn't correct, then you have just a bit more work to do.

All three positions listed above can be adjusted via patches.

* For Compendium and Fusion Position, you'll need to modify ps\_model.bin, which you can dump from facility/cmbroot.arc/ps\_model.bin using Amicitia.
* You can use this tool [here](https://github.com/ShrineFox/P4GPS\_ModelEditor.) to adjust to your liking. I recommend following [this tutorial](https://www.youtube.com/watch?v=H\_YEB8efylQ) instead of adjusting blindly.
* For Battle Positioning, you'll need to make adjustments to model.tbl located inside of init\_free.bin. You'll need to use rudiger's alt p4g\_tbl.bt template in 010 editor to make these changes. You can find that [here](https://cdn.discordapp.com/attachments/746431668058849280/934548704994676818/P4G\_tbl.bt).
* After you've made your adjustments to the table, you can make a tbl patch with this tool.
* Once you're satisfied with the positioning on all three fronts, you're finished! Your model is successfully imported, congrats!
