---
title: Spine model components in Defold
brief: This manual explains how to create SpineModel components in Defold.
---

# Spine Model

The SpineModel component is used to bring _Spine_ skeletal animations to life in Defold.

## Creating SpineModel components

Select a game object to hold the new component:

Either create the component in-place (<kbd>right click</kbd> the game object and select <kbd>Add Component ▸ Spine Model</kbd>)

Or create it on file first (<kbd>right click</kbd> a location in the *Assets* browser, then select <kbd>New... ▸ Spine Model</kbd> from the context menu), then add the file to the game object by <kbd>right clicking</kbd> the game object and selecting <kbd>Add Component File</kbd>).

Set the *Properties* on the component:

Spine scene
: Set this to the Spine scene file you created earlier.

Blend Mode
: If you want a blend mode other than the default `Alpha`, change this property.

Material
: If you need to render the model with a custom material, change this property.

Default animation
: Set this to the animation you want the model to start with.

Skin
: If your model has skins, select the one you want it to start with.

You should now be able to view your Spine model in the editor:

![Spine model in editor](images/spinemodel/spinemodel.png){srcset="images/spinemodel/spinemodel@2x.png 2x"}

## Runtime animation

Defold provides powerful support for controlling animation in runtime:

```lua
local play_properties = { blend_duration = 0.1 }
spine.play_anim("#spinemodel", "jump", go.PLAYBACK_ONCE_FORWARD, play_properties)
```

The animation playback cursor can be animated either by hand or throught the property animation system:

```lua
-- set the run animation
spine.play_anim("#spinemodel", "run", go.PLAYBACK_NONE)
-- animate the cursor
go.animate("#spinemodel", "cursor", go.PLAYBACK_LOOP_PINGPONG, 1, go.EASING_LINEAR, 10)
```

