<p align="center">
  <img src="https://user-images.githubusercontent.com/28692063/154995679-17304c89-bd06-457d-a5c7-4c132f5070c1.png">
</p>

<h1 align="center">Mission Testing</h1>

<h2 align="center">Checklist & Procedures V1.5 (Updated: 15 jan. 2022 Pillow)</h2>


### Usage of Notes
Notes on ARCHUB are there to provide the mission maker with feedback and any clarification that needs to be made between the maker and the tester. Tester should provide clear and concise feedback and the maker should provide a changelog for each update and respond to each of the individual points given by the tester.

***Must** means that the given requirement needs to happen*

***Should** means that the given requirement is open to adjustment based on mission design*
___

### General
- [ ] TMF Autotest must be examined before exporting the mission
    - [ ] Any warnings must be acknowledged
    - [ ] Any errors must be resolved
- [ ] Add an admin briefing to assist with testing and potentialfor future replayability, containing mission/zeus intent and/or hidden tasks/equipment.
    - You can also use editor comments or archub notes. If you leave a mission undocumented it may be returned straight away by a tester.
- [ ] If using known elements make sure to rename BLUFOR/OPFOR/INDFOR to appropriate force names for example NATO/RUS/VDV, if using unknown elements then clear the BLUFOR/OPFOR/INDFOR designations
- [ ] Save file naming convention is as follows: ARC_coop/tvt/ade_nameofmission_yourname. Where coop/tvt/ade is relevant to mission type, and nameofmission needs to match the name of your operation for loading clarity.
- [ ] If a mission has been created using mods from the mission making modset, List the ones used in notes for mission testers to be aware of.
- [ ] If the mission includes special slotting orders or instructions, it must be noted in the MP Mission Summary. Examples:
  - DESCRIPTION HERE | Slotting: CO, Alpha SL/1/2, MAT1, Bravo SL/1/2, MAT2, etc
  - DESCRIPTION HERE | Standard slotting, MAT required, overflow to MMG
  - DESCRIPTION HERE | Standard slotting | OPF 2:1 BLU
___

### Units & AI
- Headless client and Zeus slots must be present (even in adversarial missions).
- Cooperative missions must have pre-placed AI.
- AI Count must not exceed 200. This is a server limitation, and should ideally be kept around 100-150. This can be found by TMF autotest, or using the TMF Admin menu.
  - Can be higher with aggressive wavespawners and dynamic simulation, though at no time should more than 200 be active.
- Enable and set up dynamic simulation for static units if comfortable with it. This can help relieve server stress, but is not a solution to the AI limit.
- AI units must not be labeled as players (name will be red in colour).
- All units must be at ground level (No Floating AI or Players).
- There must be excess JIP slots (Extra riflemen).
- AI placed in and around buildings/fortifications should be garrisoned using TMF Garrison module, CBA defend module or manually.
  - AI units can be forced to be stationary by entering “this disableAI ‘PATH’”; in object init. (https://pastebin.com/pmvB2nzw)
- AI placed on patrols must have waypoints or be synced to a CBA patrol module
- Reserve AI must be placed out of sight of players and at an appropriate location
- AI should not be in a bunch of 1 man groups
- Hostage AI must be set as captive in ACE unit settings.
- If tanks are in the mission, the strength of standard infantry launchers must be kept in mind. Standard infantry should not be equipped with HAT equipment.
- Likewise, player vics (Mike/Gambler) should not be killable in 1 hit by enemy fireteam level AT
___

### Assets
- DLC assets / Weapons should only be given to a handful of slots and the slots should include the name of the dlc required in the lobby.
  - TMF Autotest throws warnings for DLC usage.
- Vehicle inventories should be clear of default items or have relevant equipment for missions.
- Supplies such as ammo must fit the given weapon
- If you are utilizing any Refuel, Repair, Rearm (RRR) vehicles/assets, please ensure their respective ACE Settings are set up. Some vehicles retrieve these attributes automatically, but double check to be sure.
- Little Birds should use the MELB variant (higher quality)
- If there is enemy armour, ensure player equipment is capable and or reliable, and that they have adequate quantities of it.
  - Players must be able to destroy enemy armour
  - Eg. If the enemy has T-72s, give the players ATGMs like Javelins or Hellfires
___

### Intel
- Map markers must be concise and not excessive. Objective markers must not be black (should not blend in with player markers).
- Briefing must not contain typos.
- Briefing needs to have clarity (simple objective bullet points)
  - Situation is the place to add lore and fluff to your narrative.
  - Mission tab should be bullet points of the tasks to be completed by players, unless special circumstances.
- Briefing must be divided into appropriate sections
- Briefing must make use of all fields excluding special tasks and logistics, given that there is no relevant information for those fields.
- Logistics section should contain the amount of seats per transport vehicle (if any)
- The “TMF Spectator Objective” Module can be used to highlight points of interest (Hidden objectives, hostages, etc) for spectators.
- If there is a chance of betrayal or there is an element of risk to the cooperation it must be observable in at least a couple of locations. Either by outright stating it in mission task and one other place, or by implying tension in some form in situation and one other place. This must also be specified in Admin for tester awareness.
___

### Loadouts
***When checking loadouts you should load into a multiplayer instance of the mission and use the loadout command (#loadout).***
- Loadouts must not contain anything related to ACRE.
  - All radios must be assigned in the TMF ACRE Menu.
- The “example loadout” in the TMF Mission Template should be deleted and its reference in description.ext removed once you are done with building your loadout.
  - New loadouts can be added by duplicating and renaming this file, and adding a new file reference in the description.ext.
- Avoid using magnified optics unless by mission design and only for special roles. Anything 1x-2x is acceptable for a general rifleman.
- If the mission has darkness for a significant portion:
  - Ensure loadouts have map lights (unless by design) and sufficient illumination or NVGs (mortar, flashlights, hand flares) and that the amount is sufficient for the mission length
  - Weapons should be fitted with flash hiders (unless by design), at least the AR
  - If using night vision then binos and optics should be night vision compatibleIf night mission ensure loadouts have map flashlight (unless by mission design)
- Night missions should provide sufficient illumination or NVGs (mortar, flashlights, hand flares) and their amount is sufficient for the mission length.
- AAR must have correct ammo for AR:
  - Binoculars should also be added.
  - 1x Spare Barrel should also be added
- Leadership loadouts should have: 
  - Map tools, binoculars, etc...
- All ammo must fit the given weapon (magazines, GL rounds)
- Most infantry elements should have entrenchment tools at all times, with the only exception being missions that specifically calls for them to not have it.
- All roles must have 1x Canteen
- Some equipment must be assigned via macros defined in arc_misc.
  - All units must include the MEDICAL_R macro in items[] for basic medical equipment
  - Combat Life Savers must include the MEDICAL_CLS macro backpackItems[] for specialist medical equipment
  - Medics must include the MEDICAL_M macro in backpackItems[] for specialist medical equipment
  - Forward Air Controllers must use the FAC_GEAR macro in backpackItems[]
  - Mortar team leader must use the MTR_GEAR macro in items[]
- When adding multiple of the same item, LIST_n(x) macros must be used
- A standard CLS loadout should have:
  - 2 body bags
  - 20 bandages
  - 10 morphine
  - 5 epinephrine
  - 3 tourniquets
  - 10 splints
  - 1 saline 500ml
  - 5 saline 250ml
- A standard Medic loadout should have:
  - 40 bandages
  - 20 morphine
  - 15 epinephrine
  - 8 saline 500ml
  - 10 saline 250ml
  - 5 saline 1000ml
  - 3 tourniquets
  - 2 bodybags
  - 20 splints
- A CLS is a rifleman first, medic later. Squad medics should always have a greater amount of medical supplies.
- FAC loadout has coloured smokes, both hand and GL (red for enemy, green for friendly, purple for landing zones)
  - Minimum of 6 of each color
- FAC has a long range radio,Laser designator(batteries), Radio spike.
- Map markers in TMF Orbat settings are in proper squad hierarchy
- Radios are correctly set and frequencies allocated if used via TMF ACRE menu
- Pilots should have high quality night vision.
- Vehicle crew must have backpacks for toolkits
- Pilots and vehicle crew must have toolkits (either on person or in vehicle).
  - Backpacks are required if toolkits are provided.
  - The amount of toolkits can be changed at the Mission Makers discretion.
- Leadership, pilots and vehicle crew should have a GPS (unless by mission design)
- If a nighttime mission or expected to be, all elements including MG’s, to be equipped with flash hiders or suppressors unless specified not to by mission design. 
- If MicroDAGR’s are included in the loadout; Consider also adding GPS terminal - Whilst MicroDAGR’s are useful for the odd specialist role and non-inclusion of player unit markers, GPS are often better in a HUD sense and adds map markers. 
___

### Mechanics
- Expected amount of passengers can load into the given transport vehicle(s) without many extra vehicles. Excluding vehicles with dedicated crew, convoys must not exceed 3 vehicles per squad. 
- Sling loaded assets must be able to be sling loaded
- Triggers must work as intended and be double checked for locality
  - For server-only triggers ensure “server only” is checked
- Scripted mechanics must work as intended. Performance must be kept in mind.
- Be mindful of editor placed objects for performance reasons
  - Compositions are great indicators of performance issues
  - Disable simulation on objects that will not be moved or possibly interacted with.
  - When testing, be mindful of locked layers. These can be hiding extraneous objects.
- Weather and time of day should be interesting
  - We don’t want every mission to be clear day or night. If possible, make time of day logical to the mission in question.
- Moon phases can be used to adjust light levels in night missions. These settings can be found and the date and time settings for the mission.
- Make sure player equipment is suitable for both the starting conditions and ending conditions of the mission, if set at dusk do players need night vision by the end or by the halfway point? Is it going to get too dark too fast (or too light if set pre-dawn)
___

### Briefing
***Any key or mission critical information should be noted more than once.***
- Situation Section:
  - General background for the mission.
  - Flavor text, and any key lore surrounding the mission.
  - Weather information.
- Mission Section:
  - Where are the players located?
  - What is going on?
  - What is their objective?
  - Any failure states for the mission.
- Friendly Forces:
  - What friendly elements can players expect in the AO.
  - Are there active friendly AI on the field?
  - Do the friendlies have separate radio channels?
- Enemy Forces:
  - What kind of enemy forces should players expect?
  - Can be broad strokes, or a highly detailed roster of enemy forces.
- Movement Plan:
  - How you expect players to traverse the mission.
  - Any expected blockers of movement (roadblocks, IEDs, etc)
- Commander's Intent:
  - How you as a mission maker expect them to handle the mission.
  - Any pertinent information that you would like player commanders to keep in mind while drafting a plan.
- Fire support plan:
  - Note any friendly CAS strikes or artillery fire missions players should expect.
  - Should cover player controlled assets as well (Mortar, Helicopter support, etc)
  - Should also cover any fire support outside players control.
- Special Tasks:
  - Any secondary objective not noted in the mission section.
  - Any extra objectives you would like commanders to consider when drafting their plan.
- Administration:
  - A clear and concise list of any vehicles/priority assets players have at their disposal.
  - Anything from general transport vics, to high tier assets such as CAS birds, and artillery.
  - This should note a resupply plan if one is applicable.
- Mod Specific Information
  - Specific information relating to either resource-dependent mods or rarely used mods
    - For Example: When using fortify; add a tab with budget, items accessible, and item cost.
    - Or, when using something like the Paddle Mod, add a tab with the instructions for that mod. 
      - Insert the following to briefing.sqf in line with everything else, after “EXECUTION”: 
      ```sqf
      /* ===============================================
        MOD SPECIFIC INFORMATION
          - Provide an outline as to what additional controls/keybinds/information players may require.
      */

      private _relevantControls = ["diary", ["Mod-Specific Information","
      <br/>
      <font size='18'>MOD NAME HERE</font>
      ```
___

### Misc
- There must not be any land mines that are capable of instantly killing player infantry without adequate warnings about location.
  - FURTHER TO THE ABOVE: Bounding Mines are extremely deadly and should be used incredibly sparingly against players. If placed be prepared to be told to remove them, depending on location and amounts. 
- When hiding mission critical items make sure they can be easily found and looked at by the testers. Both by making a specific notation to them in game, and by placing them in their own sub folder, would be the most ideal. At least one method should be used.
- An interesting banner image and map screenshot must be uploaded to ARCHUB
- Mission must not be overly large, and must be reasonably concluded in the respective time limits.
  - Cooperative missions must not exceed 2 hours (including safestart).
  - Adversarial missions must not exceed 1 hour (including safestart).
  - Objectives should be unique and precise (EX: capture the command post, kill the spy)
  - Clearing a town is not a suitable mission objective, it is better left as a byproduct of player strategy/tactics
- Think of the mission as a player and if you see something that needs testing, test it
- Imagine possible plans the players might choose for attack/defence and ensure mission still functions with those plans in mind
- Mission .pbo must match standard naming convention to avoid being rejected by archub
  - ARC_[COOP | TVT | ADE]_MissionName_Author
    - Please use Pascal Case for the mission name (capitalize every word)
    - Do not use spaces or special characters in your mission file name
- Remember to use in editor comments or Admin briefing to explain certain aspects or objectives.
- Missions exported from eden editor can be find in your arma 3 folder
  - example: C:\Program Files (x86)\Steam\steamapps\common\Arma 3\MPMissions
- Missions uploaded to ARCHUB should be ready for play testing. 
- After uploading your mission, leave a note on the hub briefly explaining the mission and your expectations. Or use Admin Brief (admin.sqf)
- Missions must have a Zeus running them, even if the mission is autonomous.
- Do not Zeus from a JIP unit, use either the game master slot or create a specific Zeus unit with game master tag.
___

<br />
<br />
<h1 align="center">Known issues in the modset</h1>

***Please refer to this guide when creating/testing missions. Some of these issues can be fixed in the editor, while others not.***

## Editor/TMF
| Issue | Mitigation |
|-------|------------|
| Deleting an ACRE radio net will cause all networks under it to be assigned wrongly. If a net is not needed, just unassign it from units. | |
| UXO Placement - IED’s / Mines etc can be placed down within piles of debris. This creates a situation in which the IED is detectable and activatable (reliably by trigger or cellphone, partially depending on placement with pressure plate)  but not defusable. This should be double checked against mission maker intent as part of the testing process.. | Additional scrutiny in testing |
| Briefings specific to roles instead of whole faction break archub when uploaded | |
___

## Maps
### Podagorsk
| Issue | Mitigation |
|-------|------------|
| Rivers not suitable for boats | |

### Sahrani
| Issue | Mitigation |
|-------|------------|
| Trees in the northern area have dense vegetation close to their base that blocks players LOS but don't affect AI | Heavy editing |
___

## Vehicles
### General vehicle issues
| Issue | Mitigation |
|-------|------------|
| M1A2 Abrams variants introduced in latest CUPdate can break the commander seat. Vic disallowed from use until CUP hotfix applied. | |
| Red’n’tanks Wiesel is, per player feedback, “Terrible”. Unless Mission Critical, Suggest replacing with a different asset, or with arma Tanks DLC version (despite 2035 variation) if applicable. | |

### Aircraft carriers
| Issue | Mitigation |
|-------|------------|
| Vanilla USS Freedom Aircraft Carrier, specifically the skirts around the edge, are penable (and possibly see throughable) by AI on .50 mounted guns | |
___

## Gear
### Loadouts/Weapons
| Issue | Mitigation |
|-------|------------|
| Use of “This additem” scripts to add items to vehicle inventory is not reliable; use vanilla vehicle inventory functions instead. | |
| Diving goggles don’t appear if added through loadout files, needs to be in a box or something close to spawn | |
| Heavy loadouts **above 43.09kg will not have radios added**. This is a limitation of the game and can’t be fixed. The best solution is to add heavy equipment to a box next to the offending units’ spawn and remove them from the loadout files. | |
| MK17 SV act as DMR’s; same effect as long-guns with optics when on AI - AI NOT TO BE EQUIPPED WITH. | |
| NIArms MGs that should be Open Bolt are treated as Closed Bolt and should not currently be used. Rifles, Pistols, etc are still fine to use | |
| Red’n’Tanks deployable MG3 are too delicate for use and explode/enter destroyed state, killing the gunner, at the slightest provocation. BLACKLISTED FOR FURTHER USE UNTIL UPDATED. | |
