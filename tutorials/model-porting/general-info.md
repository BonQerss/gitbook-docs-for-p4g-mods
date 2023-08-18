---
description: Other features that go into making a model.
---

# 🖌 General Info

In this section, we'll discuss various extra features you can add to your model port.

## Textures

When importing textures into your models from various sources, you may have noticed other textures alongside them. In this section, we'll discuss applying most of them to your model to provide richer and deeper details.

The only tool you'll need here is a Photo editor like Photoshop or GIMP. For the sake of these instructions, I'll use GIMP but the information should still apply to other applications like Krita, Aseprite, paint.net, or even Photoshop.

First, open your main texture in your photo editor.&#x20;

If you have any transparent parts, you'll need to fill them in. Add a layer mask to the image, and then remove it, this will fill in the transparent parts.

Next, we'll go over what you should do for every other potential texture.

### Normal Maps

In your photo editor, add the normal map as a new layer. If the image isn't scaled, scale it up so it covers the entire image.

Next, go to saturation and turn it all the way down to zero.

After that, invert the colors.

Finally, set the blend mode to soft light.

Merge this new layer down.

### Shadow Maps

In your photo editor, open your shadow map as a new layer, scaling it up to match the size of the base image if needed.

Next, invert the colors of the shadow map layer.

Set blend mode to multiply and set the opacity to %50.

Merge this new layer down.

### Specular Maps

Before you get started, triple-check if the specular map is applicable to the model.&#x20;

Some spec maps are designed for real-time lighting and not flat lighting. If the specular map contains colors outside of black and white, it most likely uses real-time lighting.

Once you've confirmed it's applicable, carry on with the guide.

In your photo editor, open the specular map as a new layer, scaling up to match if needed.

Create a new layer that is light gray in color.

Move your specular map above this new gray layer and set the blend mode to multiply.

Merge the specular map down into the grey layer.

Set the blend mode to either Screen or Dodge, it's up to you which looks better.

Once satisfied, merge the specular map down.

### MSR Map

MSR maps are commonly used in SMT V models. MSR stands for Metal, Specular, Roughness. MSR maps split these types into three color channels. Red is Metal, Green is Specular, and Blue is Roughness.&#x20;

The same factors for Specular maps also apply to MSR maps. If a layer features color, it most likely requires real-time lighting.

In your photo editor of choice, decompose the MSR maps into 3 separate layers for each color channel.

Use the same technique to apply the maps as listed above.&#x20;

Apply the Blue layer like you would a normal map.\
Apply the Green layer like you would a specular map.\
Apply the Red layer like you would a specular map.

Once you're done, merge the layers down into the base texture.

## Artwork

Adding artwork for your newly added Persona is relatively simple.

First, find your desired artwork in a high-quality, transparent form. The Megaten wiki typically features high-quality images but requires converting the webp images to a useable format for photo editors

In a photo editor of choice, open the artwork and expand the canvas until the image is square on all sides.

The positioning is up to you, but what I find best is to expand the canvas towards the upper left corner.&#x20;

Camp TMX files (Compendium Artwork) are 1024x1024 in resolution and Card TMX files are 512x512 in resolution.

Next, to get your artwork in game you have two options for tools.

For PC users you should be using the TMX converter and [this fantastic guide](https://gamebanana.com/tuts/15675) by Pixelguin.\
For Playstation Vita users, you should be using [GJConv.](https://github.com/Pioziomgames/GJConv) Pass the argument `-id` `-so off` when converting to generate a file for Vita.

For getting your artwork in game, you should be following a structure like this, replace the missing name with the Persona's model ID.\
`camp/persona/pst_###.tmx`\
`card/persona/i_prc###.tmx`



