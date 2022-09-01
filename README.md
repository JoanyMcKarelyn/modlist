# Modding Notes

My thoughts on mods and fixes and tweaks. 

# Convenience Mods

## [Essential Indicators](https://www.nexusmods.com/morrowind/mods/48267) by Anumaril21

Find this line in `...\mods\Essential Indicators\main.lua` 
```
local entry = tes3.getJournalIndex {id = (npcSide.entry)}
```
and change it to
```
local entry = tes3.getJournalIndex {id = (npcSide.entry)} or 0
```

# Game Balance and Difficulty

## BTB's Game Improvements - Necro Edit ([Nexus](https://www.nexusmods.com/morrowind/mods/47129), [Moddinghall](https://mw.moddinghall.com/file/117-btbs-game-improvements-necro-edit))

### Equipment

With BTBGI, the values of high-end equipment have been greatly reduced and armor ratings have been rebalanced. 

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

## [Better Character Classes](https://www.nexusmods.com/morrowind/mods/47078)

Required for [Ahead of the Classes - Joseph Edit](https://github.com/JoanyMcKarelyn/Ahead-of-the-Classes-Joseph-Edit). Both this mod and Balanced Passive Races and Birthsigns are assuming the premise that the player only uses one primary weapon type (not counting marksman or hand-to-hand) and one primary armor type. 

## [Ahead of the Classes - Joseph Edit](https://github.com/JoanyMcKarelyn/Ahead-of-the-Classes-Joseph-Edit)

Danae's original mod has preset classes for vanilla playable classes therefore not compatible with Better Character Classes. The Joseph Edit is not only compatible with Better Character Classes but also rebalance the loadouts to better suit BTBGI. You don't need neither TR_Data nor OAAB_Data as well. 

## [Worth Its Weight](https://www.nexusmods.com/morrowind/mods/48070) by JaceyS

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

## One Life to Live ([Nexus](https://www.nexusmods.com/morrowind/mods/48316), [Moddinghall](https://mw.moddinghall.com/file/139-one-life-to-live)) by Necrolesian

Find this line in `...\mods\OneLifetoLive\main.lua` 
```
local livesTooltip = tes3ui:createTooltipMenu()
```
and change it to
```
local livesTooltip = tes3ui.createTooltipMenu()
```

