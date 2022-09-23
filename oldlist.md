# Graphics - User Interface

## [Crosshair White Dot](https://github.com/JoanyMcKarelyn/morrowind-modding-notes/raw/main/mods/Crosshair%20White%20Dot.7z)

A white dot crosshair.

## [Alternate Enchanted Item Icons](http://mw.modhistory.com/download-90-10395)

Add the content of `..\Alternate Icon Set 2\` to archive named `Alternate Enchanted Items Icons`.

# Graphics - Mesh Replacers

## [Weapon Sheathing](https://www.nexusmods.com/morrowind/mods/46069) and [Bow Position Edit](https://www.nexusmods.com/morrowind/mods/46069)

Make sure Weapon Sheathing is installed before Morrowind Optimization Patch **03 Weapon Sheathing Patch** and Bow Position Edit is installed after Weapon Sheathing.

## [Morrowind Optimization Patch](https://github.com/mop-org/morrowind-optimization-patch)

Grab mop from the GitHub repo not Nexus. In addition to the **00 Core** sub-package, install **01 Lake Fjalding Anti-Suck**, **02 Better Vanilla Textures** and **03 Weapon Sheathing Patch** sub-packages. Don't install the **03 Chuzei Fix** because we'll install a BTBGI compatible version later. Ignore the **05 Graphic Herbalism Patch**.

# Graphics - Shaders and Weather

## [MGE XE Shader Pack](https://www.dropbox.com/s/egtk0osv4vrgar2/MGE%20XE%20Shader%20Pack%202021-11-26.7z?dl=1)

In the core sub-package, _delete_ the `MWSE` directory. Install only the core sub-package. Open up MGE XE. Doesn't matter the Enable shader checkbox is ticked here or not, you can always toggle it on and off in game. Here is the shader list I recommend (and their order is important):

```
MGG SSAO
Underwater Interior Effects
Underwater Effects
Sunshafts
Bloom Soft
Bloom Soft Sky
EdgeAA
```
# Graphics - Lighting

## [The Midnight Oil](https://www.nexusmods.com/morrowind/mods/48293) by Merlord

This mod prevents lanterns from expiring by forced unequipping when the duration of the lantern is less than 1. So when we try to hotkey equip a light, and the last light is an "expired" lantern, even if you have other lights in your inventory, the mod will only try equipping that one. So you'll need to manually equip a non-"expired" light. 

# Graphics - Atlas Mods

## [Glass Domes of Vivec](https://www.nexusmods.com/morrowind/mods/48935) and [Moonrain Edition](https://www.nexusmods.com/morrowind/mods/48946) by tewlwolow

If you are using [Project Atlas](https://www.nexusmods.com/morrowind/mods/45399) version 0.7.2 and Glass Domes of Vivec Moonrain Edition version 1.2.8, then you'll need to install the `\Textures\ATL\atlas_velothi.dds` from version 0.6.5 as well. 

# Gameplay Mods

## [Magicka Expanded](https://www.nexusmods.com/morrowind/mods/47111) by OperatorJack

Install **00 - Framework**, **01 - Resource Pack** and **02 - Lore Friendly Pack** sub-packages. Vanilla Morrowind doesn't have Bound Greaves and Bound Pauldrons spell for some reason and Lore Friendly Pack adds them in the game.

## [Enhanced Detection](https://www.nexusmods.com/morrowind/mods/47480) by OperatorJack and Enhanced Detection Lite ([Nexus](https://www.nexusmods.com/morrowind/mods/48471), [Moddinghall](https://mw.moddinghall.com/file/145-enhanced-detection-lite)) by Necrolesian

Change this in `mods\OperatorJack\EnhancedDetection\main.lua`

```
if (timerController.active == false and timerController.timer == nil) then
```
to
```
if (timerController and timerController.active == false and
        timerController.timer == nil) then
```

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

## [Better Character Classes](https://www.nexusmods.com/morrowind/mods/47078)

Required for [Ahead of the Classes - Joseph Edit](https://github.com/JoanyMcKarelyn/Ahead-of-the-Classes-Joseph-Edit). Both this mod and Balanced Passive Races and Birthsigns are assuming the premise that the player only uses one primary weapon type (not counting marksman or hand-to-hand) and one primary armor type.

## [Ahead of the Classes - Joseph Edit](https://github.com/JoanyMcKarelyn/Ahead-of-the-Classes-Joseph-Edit)

Danae's original mod has preset classes for vanilla playable classes therefore not compatible with Better Character Classes. The Joseph Edit is not only compatible with Better Character Classes but also rebalance the loadouts to better suit BTBGI. You don't need neither TR_Data nor OAAB_Data as well.

## [No Disease Labels](https://www.nexusmods.com/morrowind/mods/48295)

An MWSE mod that substitutes all substrings `Blighted, Diseased, Infected, Plague, Plaguebearer` with empty strings in creature names. 

## [Service Requirements Revised](https://www.nexusmods.com/morrowind/mods/50715) by Sigorun

Faction services (except healer service) are for faction members only and once a member, services are available for anyone ranked within one rank of the member they are trying to get services from.

Here is a list of places where you can find independent Enchanters:

- Ald'ruhn, Llethar Vari: Enchanter (I'm very surprised this dude isn't a Redoran)
- Vivec, Miun-Gei: Enchanter
- Tel Aruhn, Maren Uvaren: Enchanter
- Mournhold, Craftmen's Hall,
- Holamayan Monastery

## [DM_DB Armor Replacer TCBOO Patch](https://github.com/JoanyMcKarelyn/morrowind-modding-notes/raw/main/mods/DM_DB%20Armor%20Replacer%20TCBOO%20Patch.7z)

This plugin merges the inventory of `db_assassin3` and `db_assassin3a` so Dark Brotherhood Assassins have both the Dark Brotherhood Mask from DM_DB Armor Replacer and the Adamantium Shortsword from There Can Be Only One. Loads after TCBOO (mlox rules written below).

## [Silver Tongue](https://www.nexusmods.com/morrowind/mods/49086) by VitruvianGuar

Change this in `mods\silverTongue\main.lua`
```
disposition = parent:createFillBar{id = tes3ui.registerID("MenuDialog_disposition2"), current = npcRef and npcRef.object.disposition, max = 100}
```
to this
```
disposition = parent:createFillBar{
        id = tes3ui.registerID("MenuDialog_disposition2"),
        current = npcRef and npcRef.object.disposition,
        max = 100
    }
```

# Not Optional Hardcore Mods

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

Change this in `mods\mer\ashfall\camping\tents\tentcontroller.lua`

```
return tentConfig.tentActivetoMiscMap[activeRef.object.id:lower()]
```
to 
```
return tentConfig.tentActivetoMiscMap[activeRef.object.id and
               activeRef.object.id:lower()]
```

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
;; @There Can Be Only One

[Order]
DM_DB Armor Replacer.esp
There Can Be Only One.ESP

[Order]
DM_DB Armor Replacer.esp
There Can Be Only One (Alt Fyr).ESP

[Order]
DM_DB Armor Replacer.esp
There Can Be Only One (Alt Fyr 2).ESP

;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
;; @DM_DB Armor Replacer TCBOO Patch

[Order]
There Can Be Only One.ESP
DM_DB Armor Replacer TCBOO Patch.esp

[Order]
There Can Be Only One (Alt Fyr).ESP
DM_DB Armor Replacer TCBOO Patch.esp

[Order]
There Can Be Only One (Alt Fyr 2).ESP
DM_DB Armor Replacer TCBOO Patch.esp

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
;; @Morrowind Anti-Cheese Tweaked

[Order]
Wares_Vvardenfell.esp
Morrowind Anti-Cheese Tweaked.esp

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
- Magic Effects: 53 (Missing Mysticism sound from both Patch for Purists and BTBGI)
- Non Player Characters: sjoring hard-heart (overrides MDMD with Tribunal stats)
- Spells: ash feast (overrides Rebalance series BTBGI Patch magicka cost with Beware the Sixth House edit)
- Spells: shockball (overrides BTBGI spell area with Patch for Purists edit)
