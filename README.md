# Story of Seasons: Trio of Towns - Lulukoko Portrait Mod
#### Version 1.0

This mod changes the portraits used for the Lulukoko villagers to better match their in-game models and official artwork.

Currently this mod only changes the portraits for Ludus and his children. This includes the post-marriage CG as well. Mods for Siluka, Iluka, and their children are next priority, with the other Lulukoko villagers to be added afterwards.

Example:

![A comparison of Ludus's original portrait sprite to an edit with darker skintone](/readme_imgs/ludus_edit_compare.jpg)

Please note that **this mod has only been tested on a US, non-modded version of ToT** running in Citra Nightly 2104 for Windows. Due to the simple nature of this mod, it should be compatible with other versions; however, the method for installation may be slightly different.
If you encounter a problem with this mod, please open an issue on this page and I will address it if I am able.

This mod should be compatible with existing save files and should not have the ability to corrupt any saves. However, as a safety net, **it is recommended that you back-up your save before attempting any modding.**

## Installation

This assumes that you are running the game in Citra. Any other emulator with RomFS support should also work, but I will not describe them here.

Download this repository by clicking the green `Code` button followed by the `Download ZIP` button.

![Image showing the buttons to download code from a GitHub repo](/readme_imgs/tutorial_2.jpg)

Extract the ZIP anywhere on your computer. Note the folder named `/romfs`.

Once you have loaded your game's directory in Citra, right-click your game and select `Open Mods Location`. This will open up a folder named `/load/mods/<your_game_ID>`.

![Image showing the menu to open the mod directory in Citra](/readme_imgs/tutorial_1.jpg)

If your game has no existing RomFS mods, this folder should be empty. Simply paste the `/romfs` folder from the ZIP into this folder, and the mod will be installed.

![Screenshot of the romfs folder present in the mods folder](/readme_imgs/tutorial_3.jpg)

Once the modded `/romfs` folder is present in your Citra mods folder, you can run your game with Citra and see the new portraits!

## Making Your Own Sprite Edits

This section describes how to create your own graphical edits for SoS:ToT. This assumes you are in a Windows environment.

Tools you will need:
- [Citra](https://citra-emulator.com/)
- [Kuriimu](https://github.com/IcySon55/Kuriimu/releases)
- An image editor of your choice (I prefer [Photopea](https://www.photopea.com/) for simple edits)

Note: Since 2021, Kuriimu has been deprecated and replaced with Kuriimu2. However, as of 02/16/2025, *Kuriimu2 currently has a bug when saving the necessary .bflim files present in ToT.* Therefore, it is important you use the original Kuriimu from the provided link.

To begin, right-click your game in Citra and click `Dump RomFS`. After a short wait, your game's dumped assets will be located at `C:\Users\<your_username>\AppData\Roaming\Citra\dump\romfs\<your_game_id>`.

![Image showing the dumped contents of a 3DS ROM](/readme_imgs/tutorial_4.jpg)

It is recommended to copy the entire contents of this dump and paste it elsewhere on your computer for editing purposes.

SoS:ToT stores all of its graphics inside of .arc archive files. Explore the RomFS and find an .arc you wish to edit. (For reference, most 2D graphics are in the `/Layout` folder)

Let's look at the player icon shown on the File Select screen, which is located at `/Layout/SaveloadLower.arc`.

![The female player icon shown on the game's file select screen](/readme_imgs/female.bflim.00.png)

Open the folder where you installed Kuriimu and open `Karameru.exe`. Select `File->Open` and navigate to the .arc file. Once opened, you should be able to see the files present inside the archive. The `timg` folder holds all of the graphics.

![Screenshot of a .arc file open inside Karameru](/readme_imgs/tutorial_5.jpg)

We want to edit the female player icon, so right-click `female.bflim` and select `Edit in Kukkii`. You should see the image open in another window. I have highlighted the relevant buttons we will be using.

![Screenshot of the interface of Kukkii](/readme_imgs/tutorial_6.jpg)

Click the `Export PNG` button (highlighted in red) to convert the .bflim image to a .png image. At this point, you may edit the image however you wish. It is important that you do not change the overall image dimensions, or the game will likely crash.

Once you have your edited .png, click the `Import PNG` button (highlighted in blue) to replace the graphic with your new version. Then, click `Save As...` (highlighted in green) to save your image as a new .bflim!

Now that we have an edited .bflim, we need to go back to Karameru and actually replace the archived graphic with our new one so that the game can recognize it. To do this, inside Karameru, right-click the .bflim you want to change and select `Replace`. Select your new .bflim, and the file inside the .arc should turn orange to indicate that it's been replaced.

![Image showing the menu to replace a graphic in Karameru](/readme_imgs/tutorial_7.jpg)

Now click `Save`. You will now have an edited copy of the .arc file.

To install your modded file, simply navigate to your game's mods location (`/load/mods/<your_game_id>`/romfs), and paste your new .arc file in the same relative location as the original file.

For instance, the save menu graphics were originally located in `/dump/romfs/<your_game_id>/Layout/SaveloadLower.arc`. Therefore, the modded file should be located in `/load/mods/<your_game_id>/romfs/Layout/SaveloadLower.arc`.

![Screenshot of the correct location for the modded file](/readme_imgs/tutorial_8.jpg)

Start the game in Citra and you will see your edits in-game!

![Screenshot of the editted sprite inside the game](/readme_imgs/tutorial_9.jpg)

Note that Kuriimu (in combination with other programs) can also be used to edit things besides graphics, such as text and models. However, that is outside the scope of this mod (and my technical abilities).
