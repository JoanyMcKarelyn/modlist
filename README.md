# Modding Notes

My thoughts on mods and fixes and tweaks.

# Utilites

## [mlox](https://github.com/rfuzzo/mlox/releases/) and [mlox-rules](https://github.com/DanaePlays/mlox-rules)

I use mlox because I uninstall and reinstall mods a lot. Download zip and follow the steps from mlox-rules.

# Bug Fixes

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

## [Essential Indicators](https://www.nexusmods.com/morrowind/mods/48267)

Find this line in `...\mods\Essential Indicators\main.lua`

```
local entry = tes3.getJournalIndex {id = (npcSide.entry)}
```

and change it to

```
local entry = tes3.getJournalIndex {id = (npcSide.entry)} or 0
```

# Game Balance and Difficulty

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

```
[Order]
Morrowind Anti-Cheese Tweaked.esp
BTB's Game Improvements (Necro Edit).esp
```

## BTB's Game Improvements - Necro Edit ([Nexus](https://www.nexusmods.com/morrowind/mods/47129), [Moddinghall](https://mw.moddinghall.com/file/117-btbs-game-improvements-necro-edit)) by Necrolesian

## [Better Character Classes](https://www.nexusmods.com/morrowind/mods/47078)

Required for [Ahead of the Classes - Joseph Edit](https://github.com/JoanyMcKarelyn/Ahead-of-the-Classes-Joseph-Edit). Both this mod and Balanced Passive Races and Birthsigns are assuming the premise that the player only uses one primary weapon type (not counting marksman or hand-to-hand) and one primary armor type.

## [Ahead of the Classes - Joseph Edit](https://github.com/JoanyMcKarelyn/Ahead-of-the-Classes-Joseph-Edit)

Danae's original mod has preset classes for vanilla playable classes therefore not compatible with Better Character Classes. The Joseph Edit is not only compatible with Better Character Classes but also rebalance the loadouts to better suit BTBGI. You don't need neither TR_Data nor OAAB_Data as well.

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

## [GMST Menu](https://www.nexusmods.com/morrowind/mods/46428) by Merlord

Required by the following mod.

## [JosephMcKean's GMST Adjustments](https://github.com/JoanyMcKarelyn/JosephMcKeans-GMST-Adjustments)

You know those mods. Mods that only change a few GMST and nothing else. Well, this is one of those mods except it is not a plugin. Incorporated [Reduced Forward Jump](https://www.nexusmods.com/morrowind/mods/45426), [avp BTBGI-NE - Game Settings - More Meaningful Encumbrance, and avp BTBGI-NE - Game Settings - Suggested Tweaks](https://www.nexusmods.com/morrowind/mods/48955).

You may ask, hey why not just use those mods? I say because I don't want to open the esp in the Enchanted Editor to delete the gmst. Also, with this, you don't need to care about the plugin load order. If you want to edit them yourself, here is a list of all the GMSTs: https://mwse.github.io/MWSE/references/gmsts/

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

## Merged Objects Fixes

Delete the following records:

- Enchantments: bm bloodaxe (overrides BTBGI edits with Expansions Integrated edits)
- Enchantments: equity_ring_en_unique (overrides BTBGI edits with Patch for Purists edits)
- Item Levelled: random excellent melee weapon (adds back Daedric weapons from Expansions Integrated, conflicts with There Can Be Only One)
- Non Player Characters: sjoring hard-heart (overrides MDMD with Tribunal stats)
