# Modding Notes

Some notes I took for [this morrowind mod list](https://github.com/Necrolesian/morrowind-mod-list). 

# Utilites

## [Wrye Mash](https://www.nexusmods.com/morrowind/mods/45439)

### Mod Tab: Line Colors

- Red: The modification date/time of the master/plugin is problematic. Change the modification date of the files by a second or more via right panel Mod Details.

## [mlox](https://github.com/rfuzzo/mlox/releases/) and [mlox-rules](https://github.com/DanaePlays/mlox-rules)

I use mlox because I uninstall and reinstall mods a lot. Download zip and follow the steps from mlox-rules.

## Original Data Files Archive

Create an archive with all the directories in it. Yes, include BookArt, Icons, and Meshes directories, because why not. So the directory structure of the archive should be something like this:

```
01 BookArt
	BookArt
02 Fonts
	Fonts
03 Icons
	Icons
04 Meshes
	Meshes
05 Music - Battle
    Music
        Battle
06 Music - Explore
    Music
        Explore
07 Music - Special
    Music
        Special
08 Sound
    Sound
09 Splash
    Splash
10 Textures
    Textures
11 Video
    Video
```

# Bug Fixes

## [Texture Fix](http://mw.modhistory.com/download-56-10353)

Open up Texture Fix 2.0.esm in Enchanted Editor, delete `tx_lavacrust00.tga` and `MA_sandstone02` in the "Land Textures" category, then save the file.

## [Dubdilla Location Fix](https://www.nexusmods.com/morrowind/mods/46720)

Find these lines the script VampireMolag:

```
		elseif ( GetJournalIndex "MS_VampireCure" == 40 )
			if ( PCVampire != 0 )
				if ( Player->SayDone == 1 )
					Player->Say "Vo\Misc\MS_VampireMolag3.wav","I see you have done as I asked, little vampire. It was not easy for me to obtain the cure, but I was able to pry it from Vaermina after some...discussion. You have earned it. Now I have eternity to punish my daughter for her defiance. Your curse is lifted. Yet...I wonder, will you miss the taste of blood on your lips? When you sleep, will you taste the salt and copper flowing over your tongue? Go, mortal. Bask in your precious sunlight."
					Journal "MS_VampireCure" 50
					StartScript "Vampire_Cure_PC"
					set talk to 0
				endif
			endif
		endif
	endif
endif

```

and change them to

```
	elseif ( GetJournalIndex "MS_VampireCure" == 40 )
		if ( PCVampire != 0 )
			if ( Player->SayDone == 1 )
				Player->Say "Vo\Misc\MS_VampireMolag3.wav","I see you have done as I asked, little vampire. It was not easy for me to obtain the cure, but I was able to pry it from Vaermina after some...discussion. You have earned it. Now I have eternity to punish my daughter for her defiance. Your curse is lifted. Yet...I wonder, will you miss the taste of blood on your lips? When you sleep, will you taste the salt and copper flowing over your tongue? Go, mortal. Bask in your precious sunlight."
				Journal "MS_VampireCure" 50
				StartScript "Vampire_Cure_PC"
				set talk to 0
			endif
		endif
	endif
endif

```

Save the script and the plugin, then clean with tes3cmd.

# Convenience Mods

## [UI Expansion](https://www.nexusmods.com/morrowind/mods/46071) By NullCascade

### MCM Settings

On Features page:

- Auto-select search bar: None (This really annoys me.)

## [Essential Indicators](https://www.nexusmods.com/morrowind/mods/48267)

Find this line in `...\mods\Essential Indicators\main.lua`

```
local entry = tes3.getJournalIndex {id = (npcSide.entry)}
```

and change it to

```
local entry = tes3.getJournalIndex {id = (npcSide.entry)} or 0
```

# Graphics - User Interface

## [Crosshair White Dot](https://github.com/JoanyMcKarelyn/morrowind-modding-notes/raw/main/mods/Crosshair%20White%20Dot.7z)

A white dot crosshair.

## [Alternate Enchanted Item Icons](http://mw.modhistory.com/download-90-10395)

Add the content of `..\Alternate Icon Set 2\` to archive named `Alternate Enchanted Items Icons`.

# Graphics - Videos

## [Blank Intro Movies](https://www.nexusmods.com/morrowind/mods/44319)

Nobody watches the Morrowind intro so why even bother to install a high resolution one.

# Graphics - Mesh Replacers

I usually go with vanilla meshes and textures because I am on a potato laptop.

## [Weapon Sheathing](https://www.nexusmods.com/morrowind/mods/46069) and [Bow Position Edit](https://www.nexusmods.com/morrowind/mods/46069)

Make sure Weapon Sheathing is installed before Morrowind Optimization Patch **03 Weapon Sheathing Patch** and Bow Position Edit is installed after Weapon Sheathing.

## [Morrowind Optimization Patch](https://github.com/mop-org/morrowind-optimization-patch)

Grab mop from the GitHub repo not Nexus. In addition to the **00 Core** sub-package, install **01 Lake Fjalding Anti-Suck**, **02 Better Vanilla Textures** and **03 Weapon Sheathing Patch** sub-packages. Don't install the **03 Chuzei Fix** because we'll install a BTBGI compatible version later. Ignore the **05 Graphic Herbalism Patch**.

# Gameplay Mods

## [Magicka Expanded](https://www.nexusmods.com/morrowind/mods/47111) by OperatorJack

Install **00 - Framework**, **01 - Resource Pack** and **02 - Lore Friendly Pack** sub-packages. Vanilla Morrowind doesn't have Bound Greaves and Bound Pauldrons spell for some reason and Lore Friendly Pack adds them in the game.

# Game Balance and Difficulty

## [HardTrade](https://www.nexusmods.com/morrowind/mods/47368) by AxeMagister

Grab version 2.6 under "old files". MCM Settings: No Show messages, No Limit player stats to 100 when trading. Comment out a few lines:

```
	-- tes3.findGMST("fBargainOfferMulti").value = -10		tes3.findGMST("fSpellMakingValueMult").value = 10		tes3.findGMST("fEnchantmentValueMult").value = 100
    -- tes3.findGMST("fBribe10Mod").value = 20				tes3.findGMST("fBribe100Mod").value = 50				tes3.findGMST("fBribe1000Mod").value = 100
    -- event.register("uiActivated", onPersuationMenu, {filter = "MenuPersuasion"})
```

## [Morrowind Anti-Cheese Tweaked](https://www.nexusmods.com/morrowind/mods/50308) by Remiros and Sigourn

Delete the following NPC edits to make it compatible with MDMD:

- Draramu Hloran
- Dreveni Hlaren
- Elante
- Furius Acilius
- Galmis Dren
- Koffutto Gilgar
- Raxle Berne
- Sorkvild the Raven
- Vindamea Drethan
- Volrina Quarra

According to Sigourn and Necrolesian, Morrowind Anti-Cheese Tweaked.esp should come after BTB's Game Improvements (Necro Edit).esp but I don't know why. **I think** the only actual conflict between two mods is with the Golden Saint Staada: BTBGI gives Staada a Daedric Towershield and bound longsword spell and remove the random golden saint weapon and shield. If you load BTBGI first, it basically means no Daedric Towershield for you.

So **I think** Morrowind Anti-Cheese Tweaked.esp should be loaded before BTB's Game Improvements (Necro Edit).esp. Then we have our Daedric Towershield back. Yes, Scrap Metal is now worth 30 gold instead of 200 but I don't care.

## BTB's Game Improvements - Necro Edit ([Nexus](https://www.nexusmods.com/morrowind/mods/47129), [Moddinghall](https://mw.moddinghall.com/file/117-btbs-game-improvements-necro-edit)) by Necrolesian

### Settings

Restocking supplies of empty soul gems (Petty, Lesser, Common) have been added to the following merchants:

- Arrille, Seyda Neen: Petty, Lesser
- Aunius Autrus, Wolverine Hall Imperial Cult
- Chanil-Lee, Six Fishes
- Diren Vendu, Tel Mora Tower Service
- Elynu Saren, Suran Temple
- Fanildil, Hawkmoth Legion Garrison
- Ferise Varo, Vos Varo Tradehouse: Common, Greater
- J'Rasha, Vivec J'Rasha Healer: Petty, Lesser
- Medila Indaren, Caldera Mages Guild: Lesser, Common, Greater
- Mertisi Andavel, Tel Branora Upper Tower: Common, Greater
- Nelso Salenim, Telvanni Council House Entry: Lesser, Common, Greater
- Salver Lleran, Vivec Telvanni Sorcerer: Common, Greater
- Saras Orelu, Molag Mar Temple
- Solea Nuccusius, Moonmoth Prison Towers
- Syloria Siruliulus, Buckmoth: Lesser, Common, Greater
- Ulmiso Maloren, Ghostgate Tower of Dawn Lower Level: Common, Greater

## [Better Character Classes](https://www.nexusmods.com/morrowind/mods/47078)

Required for [Ahead of the Classes - Joseph Edit](https://github.com/JoanyMcKarelyn/Ahead-of-the-Classes-Joseph-Edit). Both this mod and Balanced Passive Races and Birthsigns are assuming the premise that the player only uses one primary weapon type (not counting marksman or hand-to-hand) and one primary armor type.

## [Ahead of the Classes - Joseph Edit](https://github.com/JoanyMcKarelyn/Ahead-of-the-Classes-Joseph-Edit)

Danae's original mod has preset classes for vanilla playable classes therefore not compatible with Better Character Classes. The Joseph Edit is not only compatible with Better Character Classes but also rebalance the loadouts to better suit BTBGI. You don't need neither TR_Data nor OAAB_Data as well.

## [Service Requirements Revised](https://www.nexusmods.com/morrowind/mods/50715) by Sigorun

Faction services (except healer service) are for faction members only and once a member, services are available for anyone ranked within one rank of the member they are trying to get services from.

Here is a list of places where you can find independent Enchanters:

- Ald'ruhn, Llethar Vari: Enchanter (I'm very surprised this dude isn't a Redoran)
- Vivec, Miun-Gei: Enchanter
- Tel Aruhn, Maren Uvaren: Enchanter
- Mournhold, Craftmen's Hall,
- Holamayan Monastery

## [Worth Its Weight](https://www.nexusmods.com/morrowind/mods/48070)

Find this line in `...\mods\WorthItsWeight\main.lua`

```
local object = containerMenu:getPropertyObject("MenuContents_ObjectContainer")
```

and change it to

```
local object = containerMenu and
	containerMenu:getPropertyObject(
		"MenuContents_ObjectContainer")
```

## [Ashfall](https://www.nexusmods.com/morrowind/mods/49057) by Merlord

What do I like about Ashfall:

- A necth leather backpack carried on my back and with my waterskin attached
- A bedroll with Ashlander blanket that helps me get better sleep on the cold ground
- Can't sleep because one blanket isn't enough to keep you from freezing on those cold nights
- A simple tent that sleeps me and my pet
- Bottles, Flasks, and Jugs that hold liquid
- A hammock that I crafted using wood, fabric, straw, and can lay down on
- A sack I made with fabric and rope

## [GMST Menu](https://www.nexusmods.com/morrowind/mods/46428) by Merlord

Required by the following mod.

## [JosephMcKean's GMST Adjustments](https://github.com/JoanyMcKarelyn/JosephMcKeans-GMST-Adjustments)

You know those mods. Mods that only change a few GMST and nothing else. Well, this is one of those mods except it is not a plugin. Incorporated [Reduced Forward Jump](https://www.nexusmods.com/morrowind/mods/45426), [avp BTBGI-NE - Game Settings - More Meaningful Encumbrance, and avp BTBGI-NE - Game Settings - Suggested Tweaks](https://www.nexusmods.com/morrowind/mods/48955).

You may ask, hey why not just use those mods? I say because I don't want to open the esp in the Enchanted Editor to delete the gmst. Also, with this, you don't need to care about the plugin load order. If you want to edit them yourself, here is a list of all the GMSTs: https://mwse.github.io/MWSE/references/gmst/

## One Life to Live ([Nexus](https://www.nexusmods.com/morrowind/mods/48316), [Moddinghall](https://mw.moddinghall.com/file/139-one-life-to-live)) by Necrolesian

Find this line in `...\mods\OneLifetoLive\main.lua`

```
local livesTooltip = tes3ui:createTooltipMenu()
```

and change it to

```
local livesTooltip = tes3ui.createTooltipMenu()
```

# Fixing Conflicts

## Load Order

Copy the following text to your `mlox_my_rules.txt` in your `mlox` folder. If you don't know where it is or don't see any `mlox_my_rules.txt`. Follow instructions from [mlox-rules](https://github.com/DanaePlays/mlox-rules). Install the latest mlox, not the 1.1.2 linked there.

```
;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
;; @Patch for Purists

[Order]
Patch for Purists - Book Typos.esp
Patch for Purists - Semi-Purist Fixes.esp

;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
;; @Hospitality_Papers_Expanded

[Order]
Patch for Purists - Book Typos.esp
Hospitality_Papers_Expanded*.esp

;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
;; @Divayth Fyr Puzzle Fixed Ownership Overhaul Patch

[Order]
Divayth Fyr Puzzle Fixed.ESP
Divayth Fyr Puzzle Fixed Ownership Overhaul Patch.ESP

;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
;; @Glass Domes of Vivec_atmospheric arena Ownership Overhaul Patch

[Order]
Glass Domes of Vivec_atmospheric arena.esp
Glass Domes of Vivec_atmospheric arena Ownership Overhaul Patch.ESP

;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
;; @Expansion Integrated MDMD Patch

[Order]
MDMD - More Deadly Morrowind Denizens.ESP
MDMD - Creatures Add-On.ESP
Expansions Integrated MDMD Patch.ESP

;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
;; @There Can Be Only One Expansions Integrated Patch

[Order]
Expansions Integrated.esp
There Can Be Only One Expansions Integrated Patch.ESP

[Order]
There Can Be Only One.ESP
There Can Be Only One Expansions Integrated Patch.ESP

[Order]
There Can Be Only One (Alt Fyr).ESP
There Can Be Only One Expansions Integrated Patch.ESP

[Order]
There Can Be Only One (Alt Fyr 2).ESP
There Can Be Only One Expansions Integrated Patch.ESP

;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
;; @There Can Be Only One MDMD Patch

[Order]
MDMD - More Deadly Morrowind Denizens.esp
There Can Be Only One MDMD Patch.ESP

[Order]
MDMD - More Deadly Morrowind Denizens.esp
There Can Be Only One (Alt Fyr) MDMD Patch.ESP

[Order]
MDMD - More Deadly Morrowind Denizens.esp
There Can Be Only One (Alt Fyr 2) MDMD Patch.ESP

[Order]
There Can Be Only One.ESP
There Can Be Only One MDMD Patch.ESP

[Order]
There Can Be Only One (Alt Fyr).ESP
There Can Be Only One (Alt Fyr) MDMD Patch.ESP

[Order]
There Can Be Only One (Alt Fyr 2).ESP
There Can Be Only One (Alt Fyr 2) MDMD Patch.ESP

;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
;; @BTB's Game Improvements (Necro Edit)

[Order]
Patch for Purists - Semi-Purist Fixes.ESP
BTB's Game Improvements (Necro Edit).esp

[Order]
Patch for Purists - Merged Fixes.esp.ESP
BTB's Game Improvements (Necro Edit).esp

[Order]
Morrowind Anti-Cheese Tweaked.esp
BTB's Game Improvements (Necro Edit).esp

;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
;; @BTBGI MDMD - Creatures Patch

[Order]
MDMD - Creatures Add-On.esp
BTBGI MDMD - Creatures Patch.esp

[Order]
BTB's Game Improvements (Necro Edit).esp
BTBGI MDMD - Creatures Patch.esp

;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
;; @Rebalance Series BTBGI Patch

[Order]
tribunal rebalance.ESP
Rebalance Series BTBGI Patch.ESP

[Order]
Bloodmoon Rebalance.esp
Rebalance Series BTBGI Patch.ESP

[Order]
Beware the Sixth House.esp
Rebalance Series BTBGI Patch.ESP
```

These rules (at the time of writing) are not in `mlox_user`, yet. So after you've done that, run mlox from Wrye Mash to update your load order.

You may notice the load order is very different from the one from Necrolesian's mod list. That is because _I think_ if a mlox rule mentions a plugin that you have, even if you don't have the other mod mentioned, mlox will still rearrange the load order using that rule.

What does that mean? Let me give you an example. Here are four rules in `mlox_user` that mlox will use for Necrolesian's mod list because you have The Publicans and BTB's Game Improvements (Necro Edit):

```
[Order]
Beautiful cities of Morrowind.esp
The Publicans.esp

[Order]
Morrowind Anti-Cheese.esp
Beautiful cities of Morrowind.esp

;; BTBGI-NE ( Ref: https://www.nexusmods.com/morrowind/mods/47129?tab=docs ) (Pharis)
[Order]
BTB's Game Improvements (Necro Edit).esp
BTBGI Creature Buffs.esp

[Order] ; Checked in TESPCD (Pharis)
BTBGI Creature Buffs.esp
Morrowind Anti-Cheese.ESP
```

So when you run mlox, even if you don't use BTBGI Creature Buffs, mlox will first put BTB's Game Improvements (Necro Edit) before BTBGI Creature Buffs. Then even if you use a different version of Morrowind Anti-Cheese, mlox wil put both BTB's Game Improvements (Necro Edit) and BTBGI Creature Buffs before Morrowind Anti-Cheese. Then Beautiful cities of Morrowind. Finally, The Publicans after Beautiful cities of Morrowind. And because we don't have those other mods, it becomes BTBGI before The Publicans.

What this results in is that the two mods we have installed get rearranged by rules that involved other mods that we don't have. So is it a bad thing or not? Well, in our case, since they don't conflict with each other, the load order shouldn't matter.

However, there are a few cases those rules causing cycles. When you notice cycles caused by `mlox_user`, please report them to [mlox-rules](https://github.com/DanaePlays/mlox-rules) or #mlox-rules in the [Morrowind Modding Discord Server](https://discord.me/mwmods).

## Merged Objects Fixes

Delete the following records:

- Enchantments: bm bloodaxe (overrides BTBGI edits with Expansions Integrated edits)
- Enchantments: equity_ring_en_unique (overrides BTBGI edits with Patch for Purists edits)
- Item Levelled: random excellent melee weapon (adds back Daedric weapons from Expansions Integrated, conflicts with There Can Be Only One)
- Magic Effects: 53 (Miising Mysticism sound from both Patch for Purists and BTBGI)
- Non Player Characters: sjoring hard-heart (overrides MDMD with Tribunal stats)
- Spells: ash feast (overrides Rebalance series BTBGI Patch magicka cost with Beware the Sixth House edit)
- Spells: shockball (overrides BTBGI spell area with Patch for Purists edit)
