Files prepped for applying specific fest event color settings on modded hardware: currently only supports the idols. Exclusively tested in offline emuMMC, would not risk attempting online

These are set up for version 9.2.0 (change the "920" in TeamColorDataSet.Product.920.rstbl.byml as needed)

Requires [patches](https://github.com/Coxxs/public-pchtxt) and [scene modding](https://gamebanana.com/wips/70362)

Assembled using [FesData](https://github.com/RAMDRAGONS/Splatoon-FesData)

To use:
- Identify which fest colors you'd like to see in-game 
- Copy the equivalent RSDB folder (whole thing)
- Paste within the romfs folder in your Switch's SD card path. For emulators this would look like: \sdmc\atmosphere\contents\0100C2500FC20000\romfs\RSDB
- Verify your path doesn't look like \romfs\RSDB\RSDB. There should only be one RSDB folder

To add custom colors:
- Get your three custom colors' hexcodes, establish which one will be alpha/bravo/charlie. Optionally you may also choose a neutral color
- Figure out the decimal RGBA values per hexcode via [this site](https://rgbcolorpicker.com/0-1) and note them (for example, keeping three browser tabs of the color picker site or copying the data to a text file)
- Make a new copy of TeamColorDataSet.Product.920.rstbl.byml.zs from the default folder to a new folder
- In [Switch Toolbox](https://github.com/KillzXGaming/Switch-Toolbox), open this new TeamColorDataSet.Product.920.rstbl.byml.zs copy
- Right click the text entry beside the + plus sign
- Select Export from the dropdown menu
- Save as .yaml. Keep Toolbox open
- Open the .yaml export in a text editor ([Notepad++](https://notepad-plus-plus.org/downloads/), [VS Code](https://code.visualstudio.com/))
- Navigate to line 2058. We're looking for the Alpha/Bravo/Charlie configurations *above* the "Tag: VersusTricolor" (TriColorDefault version)
- Change the RGBA values for AlphaTeamColor, BravoTeamColor,  CharlieTeamColor and optionally NeutralColor according to the RGBA values you calculated earlier
  - Ensure you're changing the right values, it's easy (for me at least) to mix up which line is which
  - AlphaTeamColor is on line 2067
  - BravoTeamColor is on line 2080
  - CharlieTeamColor is on line 2093
  - NeutralColor is on line 2105
- Save the file
- Back in Toolbox, right click the same text entry beside the + plus sign
- Select Import from the dropdown menu
- Navigate to the .yaml file you just edited
- Select the save icon 💾
- Select yes on the prompt. You should immediately get a popup saying it worked
- You're good to go; add this .zs file to your mod folder as usual (described above)

SPLATFESTS COLOR SETS KEY
|[codename](https://docs.google.com/spreadsheets/d/1v1FJh1PXtyfW3L1eYS3CbMq23kC1CqFAXjlQ8xXinO0) |ingame name|
| :--- | :--- |
|default | unused -- unaltered internal file|
|00 mujintou|Rock vs. Paper vs. Scissors|
|01 island|Gear vs. Grub vs. Fun|
|02 pocket|Grass vs. Fire vs. Water|
|02 pocket2|EARLY Grass vs. Fire vs. Water|
|03 taste|Spicy vs. Sweet vs. Sour|
|04 chocolate|Dark Chocolate vs. Milk Chocolate vs. White Chocolate (2023)|
|05 cryptid|Nessie vs. Aliens vs. Bigfoot|
|06 green|Power vs. Wisdom vs. Courage|
|07 icecream|Vanilla vs. Strawberry vs. Mint Chip|
|08 life|Money vs. Fame vs. Love|
|09 oden|Shiver vs. Frye vs. Big Man|
|10 maple|Zombie vs. Skeleton vs. Ghost|
|11 greeting|Handshake vs. Fist Bump vs. Hug / Kaiten-yaki vs. Ōban-yaki vs. Imagawa-yaki|
|11 greeting2|EARLY Handshake vs. Fist Bump vs. Hug|
|11 naniyaki|EARLY Kaiten-yaki vs. Ōban-yaki vs. Imagawa-yaki|
|12 stove|Friends vs. Family vs. Solo|
|13 filling|Red Bean Paste vs. Custard vs. Whipped Cream|
|13 weekend|Friday vs. Saturday vs. Sunday|
|14 chips|Lightly Salted vs. Consommé vs. Salted Seaweed|
|14 band|Drums vs. Guitar vs. Keyboard|
|15 dumpling|SpringFest (Fresh Season 2024)|
|16 endofworld|Same Ol' vs. Bucket List vs. Save the Day|
|17 sweat|Palace vs. Theme Park vs. Beach|
|18 carbo|Bread vs. Rice vs. Pasta|
|19 sand|Past vs. Present vs. Future|
|20 maple2|Wizard vs. Knight vs. Ninja|
|21 stove2|Money vs. Experiences vs. Presents|
|22 chocolate2|Dark Chocolate vs. Milk Chocolate vs. White Chocolate (2025)|
