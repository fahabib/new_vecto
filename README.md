# stable-diffusion-webui-vectorstudio

## Beta-Phase
Adds  Javascript-SVG-Editor (```SVG-Edit```) as a tab to Stable-Diffusion-Webui Automatic 1111.

* You can either generate txt2vectorgraphics and finish/edit them in this svg editor
* Or start drawing in svg editor and send your sketches to Controlnet (txt/img2-img) to a particular control net instance.

# Installation
* Easy way: open Extension Tab in SD-Webui and load Available Extensions, checkbox the Vector Studio
* Or: Copy this url from the git repository and add this extension by pasting it into the Extension Tab/Url. (more or less git clone)
---
* If you want to create vectorgraphics (svg) download POTRACE and put it into ```extensionfolder/bin/```  
This is tested only under windows, yet.

## For Hackers and Betatesters
* Linux & MacOos. Potrace is compiled for each OS, so you can just download and add the binary as mentioned to ```extensionfolder/bin/potrace.exe```.  
Yes, rename it either to ```potrace.exe```or create a link named potrace.exe and point to your installation.


## How it works
It tunes your prompts in that way to create suitable images to be vectorizied by the POTRACE command line tool.
The resulting SVG or PDF file is stored next to your png files in output/samples (default).

## Examples

| prompt  |PNG  |SVG |
| :--------  | :-----------------: | :---------------------: |
| Happy Einstein | <img src="https://user-images.githubusercontent.com/7210708/193370360-506eb6b5-4fa7-4b2a-9fec-6430f6d027f5.png" width="40%" /> | <img src="https://user-images.githubusercontent.com/7210708/193370379-2680aa2a-f460-44e7-9c4e-592cf096de71.svg" width=30%/> |
| Mountainbike Downhill | <img src="https://user-images.githubusercontent.com/7210708/193371353-f0f5ff6f-12f7-423b-a481-f9bd119631dd.png" width=40%/> | <img src="https://user-images.githubusercontent.com/7210708/193371585-68dea4ca-6c1a-4d31-965d-c1b5f145bb6f.svg" width=30%/> |
coffe mug in shape of a heart | <img src="https://user-images.githubusercontent.com/7210708/193374299-98379ca1-3106-4ceb-bcd3-fa129e30817a.png" width=40%/> | <img src="https://user-images.githubusercontent.com/7210708/193374525-460395af-9588-476e-bcf6-6a8ad426be8e.svg" width=30%/> |
| Headphones | <img src="https://user-images.githubusercontent.com/7210708/193376238-5c4d4a8f-1f06-4ba4-b780-d2fa2e794eda.png" width=40%/> | <img src="https://user-images.githubusercontent.com/7210708/193376255-80e25271-6313-4bff-a98e-ba3ae48538ca.svg" width=30%/> |


### Screenshot
![image](https://user-images.githubusercontent.com/7210708/221387609-37ca2c3c-3da5-42aa-ad0f-8491c5f862f7.png)
![image](https://user-images.githubusercontent.com/7210708/221387629-1666d116-7213-41af-8b6f-a9ace3fc6083.png)

Dark Theme, with SVG-Background checkerboard:
![image](https://user-images.githubusercontent.com/7210708/227962150-ed6f6c8d-1a36-4524-818e-2a73f875fda0.png)


## Features

* Added SVG-Edit as Tab with "Sendto"-Buttons from Gallery to SVG-Editor and from SVG-Editor your canvas as input for Controlnet!

* New: Added Visual Styles - RadioButtons provided by the script. Edit the script to extend of modify 
Stuff like Illustration, Tattoo, Anime etc, to save your time finding prompts on your own.
If nothing matches, select "None - promp only" and have back full control.

# POTRACE for non-windows
### Linux
If you're running under WSL, Ubuntu or another Linux distro you will need to install potrace. 
Run `sudo apt install potrace`.

### Mac
Run `brew install potrace`.  Ensure `potrace` is in your PATH so that you could run in simply by calling from a command terminal.

## Dependencies, Potrace
https://potrace.sourceforge.net/download/1.16/potrace-1.16.win64.zip  
and extracts only the executable into scripts folder in the scripts folder.

# Recommendations
- Use short prompts, like "Einstein", "Happy Einstein" ...
- avoid "realistic" attributes
- Sampling Steps ~40 is my best experience (to reduce noise and avoid details)
- CFG Scale 10-12
- Dont restore faces
- use 512x512 if no special demand on ratio
- Batch count support (16)
- Mostly you want to make white parts opaque (see checkbox in the scripts ui)
- Same for clipping the content to SVG size

* ***HINT***: Install Microsoft Powertoys for free, and enjoy in your file explorer SVG previews.
![image](https://user-images.githubusercontent.com/7210708/195476107-3a2d799f-306e-46c8-ad3c-75a44fbcfdb8.png)

# Using
* Vector studio is still listed in the script-section:
![image](https://user-images.githubusercontent.com/7210708/227960089-8166212d-c63c-4121-8598-8c23f4a2e527.png)

* Three divisons here
  * style buttons(deprecated) -> your your Webui-Styles instead 
  * lower left: vector-settings
  * lower right: png2png-settings (quant, set transparent color for poor men)

## Edit SVG - Button
Select any created SVG and click below of the gallery the "Edit SVG" button.
It sends (by overwriting eveything else) the SVG to the build-in SVG-Edit´or
Finish/check your svg for details, and or send back to Controlnet

![image](https://user-images.githubusercontent.com/7210708/227963114-19d0ac2e-3c76-4b23-b0bd-8203b8013c9c.png)


# History
* Added Background-Style dedicated for any SVG-Graphic in WebUI. 
Default is a checkerbox background to determine what is white shape and what is unfilled.
For customizing please edit the file ```style.css``` in the extension folder of vectorstudio; either comment in/out white or checker pattern; or whatever you like...
![image](https://user-images.githubusercontent.com/7210708/227958543-b7b7564b-60e4-4307-b00d-b6ce94cd3385.png)
* Fix on Controlnet internal images
* Display SVGs in gallery!
  




## Todos
* Linux/Mac-Support
* Settings
* Rework of the GUI for vectorizing

## Note
This extension will replace the simple "txt2vectorgraphics" script. No need for both



