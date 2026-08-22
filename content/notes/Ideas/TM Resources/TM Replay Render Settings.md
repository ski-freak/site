---
title: TM Replay Render Settings
enableToc: 
date: 2024-09-28
tags:
  - tmresources
---
Before rendering, you need to ensure you have the correct in game settings as well as render quality settings.

### In Game Video Settings:
- Set texture filtering as high as it goes
- Enable "Customize advanced video settings"
	- Max out Shaders Quality, Shadows Quality, Textures Quality, and Reflections on Vehicles.
	- Set reflections on water surfaces to low (nadeo broke the higher ones in renders)
	- Other reflections ON
	- Bloom and Lens Flare - I set this to medium but it may or may not matter
	- Motion blur OFF
- This isn't in the video settings, but disable advertisements, obviously.
Alternatively to doing this manually, you can download this [config file](https://ski-freak.github.io/site/notes/attachments/Default.json), and replace your `Documents\Trackmania\Config\Default.json` file with it. This will set all of the above settings.
### Render Settings
Now open the map or replay you would like to render from (in map or replay editor. If you are opening a replay click on open in editor.) We will be using the AVI button in the bottom left to render. There is a set of random things you need to check before actually rendering, but lets go over these settings in the AVI button first.

Ensure your settings match these (you can change the name of course):
![[Pasted image 20240928183750.png]]

> [!NOTE]
> The videos are rendered as avi files in 2gb chunks, this is normal.
### Codec
Once you click ok it will open up a prompt for the video compression codec, you will want to use one because otherwise the file size for rendering 1 replay will be massive. If you are using Davinci Resolve (or working with someone who does, such as myself), use the Grass Valley codec on the HQX version. Here is a direct download link to the codec [installer](https://www.edius.net/download/codec/GV_CodecOption_Setup-8.5.0.1927.exe). If you are not using Resolve, a codec such as Lagarith Lossless will also do the trick.

### Important Info
To not have a broken render, you need to ensure you do these things:
- **CALCULATE SHADOWS BEFORE RENDERING!!!**
- If you have any of them enabled, **DISABLE** Tweaker (the draw distance plugin) and any skid marks plugins. Also ensure you do not have a `Documents\Trackmania\Skins\Stadium\ModWork` folder. If you have a modwork folder, delete it / back it up somewhere else. If for some reason you wish to have custom skids in your render, you can skip disabling skids, though most people disable them for map showcases and such.
- Turning down the motion blur setting in the render settings will make the camera go all wonky, don't do that. Edit: According to Zai, none motion blur is fixed in tm2020, but half and quarter are still broken.
- If you are rendering from the map editor, the big stadium signs may display the graphic of your pinned club, so unpin your pinned club if you have one or pin one that has a mostly blank background (such as the Pancake Mapping Zone club which I use specifically for this purpose).
- You may need to use the export and import clip buttons in the bottom left to copy the ambience media tracker (if a map has it) over to where you are rendering from if you are rendering from the map editor or from an autosaved replay.
- If you are rendering with a Player Camera (such as when rendering a normal replay of driving), ensure you move the green player head OFF of the ghost clip track in the timeline before clicking the avi button. If you don't do this, the replay will begin rendering at the camera position it was when you clicked the button, ruining the beginning of the render.
- If you want 16:9 aspect ratio use 2560x1440 or whatever your preferred resolution is. 1440p or higher is recommended for youtube as you get much better compression.
	- If you are rendering for Ski, ensure you are rendering in camera 2 (set in the player camera clip), and in 3440x1440 resolution (set in the avi render settings).
- If you are going through the Create -> Replay Editor menu, when you check the replay you want to render and click it, don't click the render button there, just open it in the actual replay editor, otherwise some of these steps are impossible.
- If someone has a dumb car skin you don't want in your video, you can replace it in the ghost clip settings. Whiskey made these simple skins with colored accents just for rendering videos, you can download them from this [Google Drive](https://drive.google.com/drive/folders/1oE6aBaIj5NgwwggB9ywr3sQCyikygaLt?usp=sharing) page and put them into `Documents\Trackmania\Skins\Models\CarSport` (do not unzip them).

### Some Notes
- You may need to restart your game after doing some of the setup, such as installing the codec, deleting your modwork folder, or adding the car skins to your documents/trackmania folder.
- You cannot change the folder the videos are rendered to, because Nadeo sucks. Better hope you have space on your C drive.
- With these settings, render speeds of ~2fps are normal on maps with somewhat heavy scenery and a video card similar to an RTX 2070. On maps with very light scenery you may get up to about 12fps.
- DON'T render in 16:9 and add black bars, if you do you are very dumb.