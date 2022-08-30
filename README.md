# Modding Notes

## [Essential Indicators](https://www.nexusmods.com/morrowind/mods/48267) by Anumaril21

Find this line in `...\mods\Essential Indicators\main.lua` 
``
local index = npcSide.index
``
and change it to
``
local index = npcSide.index or 0
``

## [Worth Its Weight](https://www.nexusmods.com/morrowind/mods/48070) by JaceyS

Find this line in `...\mods\WorthItsWeight\main.lua` 
``
local object = containerMenu:getPropertyObject("MenuContents_ObjectContainer")
``
and change it to
``
local object = containerMenu and
	containerMenu:getPropertyObject(
		"MenuContents_ObjectContainer")
``

## One Life to Live ([Nexus](https://www.nexusmods.com/morrowind/mods/48316), [Moddinghall](https://mw.moddinghall.com/file/139-one-life-to-live)) by Necrolesian

Find this line in `...\mods\OneLifetoLive\main.lua` 
``
local livesTooltip = tes3ui:createTooltipMenu()
``
and change it to
``
local livesTooltip = tes3ui.createTooltipMenu()
``

