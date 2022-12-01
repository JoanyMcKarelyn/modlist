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
