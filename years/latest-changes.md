---
description: EverQuest Emulator server changes for the year 2020
---

# 2021

### 5/10/2021

This changelog entry encompasses the past 6 months of updates and PR's

**\[Akkadius\]** Drone Build Pipeline \([\#1144](https://github.com/EQEmu/Server/pull/1144)\)  
**\[Akkadius\]** \[DevTools\] Improve DevTools Toggling Options \([\#1161](https://github.com/EQEmu/Server/pull/1161)\)  
**\[Akkadius\]** \[Door Opening\] Rule to let configure Animal Door Opening \([\#1231](https://github.com/EQEmu/Server/pull/1231)\)  
**\[Akkadius\]** \[Repositories\] Insert repository improvements \([\#1236](https://github.com/EQEmu/Server/pull/1236)\)  
**\[Akkadius\]** \[Scheduler\] Event scheduler implementation \([\#1257](https://github.com/EQEmu/Server/pull/1257)\)                                                                  **\[Akkadius\]** Move data aliases after null checks for safety \[skip ci\]  
**\[Akkadius\]** Revert "\[BUG\] Fix for Group Leader Disband Issue"  
**\[Akkadius\]** Update repo with latest template \[skip ci\]  
**\[Akkadius\]** \[Hotfix\] DB Manifest  
**\[Akkadius\]** \[Hotfix\] Incorrect Perl usage method \(docs\)  
**\[Akkadius\]** \[Hotfix\] Remove test branch fields from repo  
**\[Akkadius\]** \[Installer\] Swap unstable powershell download for Perl LWP::Simple call  
**\[Alex\]** \[CLE\] Reset iterator in IsAccountInGame\(\) \([\#1345](https://github.com/EQEmu/Server/pull/1345)\)  
**\[Alex\]** Add HasDisciplineLearned\(\) to Perl/Lua.  
**\[Alex\]** Add ScaleNPC\(\) to Perl and Lua. \([\#1238](https://github.com/EQEmu/Server/pull/1238)\)  
**\[Alex\]** Add SetRadiantCrystals\(\) and SetEbonCrystals\(\) to Perl/Lua. \([\#1159](https://github.com/EQEmu/Server/pull/1159)\)  
**\[Alex\]** Add character-specific zone-based experience modifiers. \([\#1326](https://github.com/EQEmu/Server/pull/1326)\)  
**\[Alex\]** Add new experience modifiers table to GetCharacterTables\(\) and GetPlayerTables\(\) in database\_schema.h. \([\#1338](https://github.com/EQEmu/Server/pull/1338)\)  
**\[Alex\]** Add removeitem\(item\_id, quantity\) to Perl/Lua. \([\#1156](https://github.com/EQEmu/Server/pull/1156)\)  
**\[Alex\]** Convert NPC Spell AI from int16 to uint16. \([\#1262](https://github.com/EQEmu/Server/pull/1262)\)  
**\[Alex\]** Fix Perl NPC GetAvoidanceRating\(\) Perl Croak. \([\#1333](https://github.com/EQEmu/Server/pull/1333)\)  
**\[Alex\]** Fix SQL for NPC Spells. \([\#1265](https://github.com/EQEmu/Server/pull/1265)\)  
**\[Alex\]** \[Bug Fix\] Zone Heading for Binds, Summons, Teleports, and Zoning. \([\#1328](https://github.com/EQEmu/Server/pull/1328)\)  
**\[Alex\]** \[Experience\] Add exp mod to npc types to let a server op change the exp modifier \([\#1252](https://github.com/EQEmu/Server/pull/1252)\)  
**\[Alex\]** \[Library\] Update zlibng \([\#1255](https://github.com/EQEmu/Server/pull/1255)\)  
**\[Alex\]** \[Quest API\] Add HTML color tag method to Perl and Lua. \([\#1324](https://github.com/EQEmu/Server/pull/1324)\)  
**\[Alex\]** \[Quest API\] Add IsHorse\(\) to Perl and Lua. \([\#1264](https://github.com/EQEmu/Server/pull/1264)\)  
**\[Alex\]** \[Quest API\] Add IsRaidTarget\(\) to Perl and Lua \([\#1347](https://github.com/EQEmu/Server/pull/1347)\)  
**\[Alex\]** \[Quest API\] Add Mob-based data bucket methods to Perl/Lua. \([\#1237](https://github.com/EQEmu/Server/pull/1237)\)  
**\[Alex\]** \[Quest API\] Add new zone name methods to Perl and Lua. \([\#1309](https://github.com/EQEmu/Server/pull/1309)\)  
**\[Alex\]** \[Quest API\] Add secondstotime\(duration\) to Perl and Lua. \([\#1281](https://github.com/EQEmu/Server/pull/1281)\)  
**\[Alex\]** \[Quest API\] Convert Client GetLastName\(\) method export to Mob export. \([\#1331](https://github.com/EQEmu/Server/pull/1331)\)  
**\[Alex\]** \[Quest API\] Resolves traindiscs and scribespells issues in Perl/Lua. \([\#1249](https://github.com/EQEmu/Server/pull/1249)\)  
**\[Alex\]** \[Rules\] Cleanup all unused rules. \([\#1308](https://github.com/EQEmu/Server/pull/1308)\)  
**\[Alex\]** quest::getspellname\(\) and quest::getclassname\(\) fixes/additions. \([\#1158](https://github.com/EQEmu/Server/pull/1158)\)  
**\[E Spause\]** Add safeguard for issue with mobs pathing to 0,0,0 on teleport nodes with values 0,0,0 \([\#1140](https://github.com/EQEmu/Server/pull/1140)\)  
**\[JeffyW\]** \[Installer\] $ENV support, formatting, and optimizations \([\#1340](https://github.com/EQEmu/Server/pull/1340)\)  
**\[KimLS\]** Fix for issue in movement manager where a drop aggro can happen and processing continues.  
**\[Michael Cook \(mackal\)\]** Add include to PATH\_SUFFIXES for Windows builds \([\#1246](https://github.com/EQEmu/Server/pull/1246)\)  
**\[Michael Cook \(mackal\)\]** Add string util search\_deliminated\_string \([\#1260](https://github.com/EQEmu/Server/pull/1260)\)  
**\[Michael Cook \(mackal\)\]** Feature/underworld \([\#1146](https://github.com/EQEmu/Server/pull/1146)\)  
**\[Michael Cook \(mackal\)\]** Fix NPC Scale Manager leaking \([\#1254](https://github.com/EQEmu/Server/pull/1254)\)  
**\[Michael Cook \(mackal\)\]** Fix some leaks of groups/raids \([\#1242](https://github.com/EQEmu/Server/pull/1242)\)  
**\[Michael Cook \(mackal\)\]** Fix va\_list leaks in MakeAnyLenString/AppendAnyLenString \([\#1240](https://github.com/EQEmu/Server/pull/1240)\)  
**\[Michael Cook \(mackal\)\]** Hack to fix repulsable bard charms \([\#1320](https://github.com/EQEmu/Server/pull/1320)\)  
**\[Michael Cook \(mackal\)\]** LuaJIT calls it lua51.lib/dll on Windows ... \([\#1247](https://github.com/EQEmu/Server/pull/1247)\)  
**\[Michael Cook \(mackal\)\]** Provide more search paths for luajit \([\#1216](https://github.com/EQEmu/Server/pull/1216)\)  
**\[Michael Cook \(mackal\)\]** Switch scheduled hot zone check to search instead of split \([\#1313](https://github.com/EQEmu/Server/pull/1313)\)  
**\[Michael Cook \(mackal\)\]** \[Bug Fix\] Add Bounds Checking to OP\_LFGCommand Comment Processing  
**\[Michael Cook \(mackal\)\]** \[Bug Fix\] Fix use-after-free corruption with some DB calls \([\#1335](https://github.com/EQEmu/Server/pull/1335)\)  
**\[Michael Cook \(mackal\)\]** \[Bug Fix\] Misc Bard Song Fixes \([\#1317](https://github.com/EQEmu/Server/pull/1317)\)  
**\[Michael Cook \(mackal\)\]** \[Cleanup\] Nuke Make/AppendAnyLenString \([\#1251](https://github.com/EQEmu/Server/pull/1251)\)  
**\[Michael Cook \(mackal\)\]** \[Cleanup\] Only link Lua with zone \([\#1288](https://github.com/EQEmu/Server/pull/1288)\)  
**\[Michael Cook \(mackal\)\]** \[Cleanup\] use std::make\_unique \([\#1259](https://github.com/EQEmu/Server/pull/1259)\)  
**\[Michael Cook \(mackal\)\]** \[Fix\] Clean up Filtered/MessageString functions \([\#1311](https://github.com/EQEmu/Server/pull/1311)\)  
**\[Michael Cook \(mackal\)\]** \[Lua/Cmake\] Prefer LuaJIT over normal Lua \([\#1235](https://github.com/EQEmu/Server/pull/1235)\)  
**\[Michael Cook \(mackal\)\]** \[Rule\] Add a rule to disable the Pet Resist buff \([\#1337](https://github.com/EQEmu/Server/pull/1337)\)  
**\[Michael Cook \(mackal\)\]** \[Strings\] Split String Optimizations \([\#1325](https://github.com/EQEmu/Server/pull/1325)\)  
**\[Michael Cook \(mackal\)\]** zlib-ng1.dll ends up in a different path \([\#1268](https://github.com/EQEmu/Server/pull/1268)\)  
**\[Paul Coene\]** \#grid delete was deleting the grids everywhere \([\#1346](https://github.com/EQEmu/Server/pull/1346)\)  
**\[Paul Coene\]** Added RACE\_BOAT\_533 to IsBoat\(\) \([\#1154](https://github.com/EQEmu/Server/pull/1154)\)  
**\[Paul Coene\]** Client tracks pet sit/stand - force new pets to stand rather than use client \([\#1155](https://github.com/EQEmu/Server/pull/1155)\)  
**\[Paul Coene\]** Fix calls to GetSafePoints to not pass null\_ptr as zonename \([\#1336](https://github.com/EQEmu/Server/pull/1336)\)  
**\[Paul Coene\]** Prevent client update while on boat if boat turning \([\#1343](https://github.com/EQEmu/Server/pull/1343)\)  
**\[Paul Coene\]** Remove the extra erroneous message \(DoT landing message\) at mob death if mob dies of DoT. \([\#1138](https://github.com/EQEmu/Server/pull/1138)\)  
**\[Paul Coene\]** Remove unneeded calls to DoAnim\(\) for spells/bardsong \([\#1290](https://github.com/EQEmu/Server/pull/1290)\)  
**\[Paul Coene\]** \[Boats\] Fix x/y offsets from client to reflect EQ x/y instead of boat heading… \([\#1296](https://github.com/EQEmu/Server/pull/1296)\)  
**\[Paul Coene\]** \[Bug Fix\] Add debugging and fix edge case where no target for aggro mob \([\#1344](https://github.com/EQEmu/Server/pull/1344)\)  
**\[Paul Coene\]** \[Bug\] Fix ignore\_primary\_assist. \([\#1323](https://github.com/EQEmu/Server/pull/1323)\)  
**\[Paul Coene\]** \[Feature\] Allow any spawn2 spawned mob to path while zone is idle if new flag is set. \([\#1339](https://github.com/EQEmu/Server/pull/1339)\)  
**\[Peter Rigby\]** \[Fix\] Moved assigning of AISpellVar variables before AI\_Start\(\) so that any values that override the rule values will not be ignored \([\#1321](https://github.com/EQEmu/Server/pull/1321)\)  
**\[RoTPvP\]** Added a check to stop Bard song for Mezz/Stun \([\#1319](https://github.com/EQEmu/Server/pull/1319)\)  
**\[Thalic\]** Minor ortographic corrections of ruletypes.h \([\#1147](https://github.com/EQEmu/Server/pull/1147)\)  
**\[Thalix\]** Minor ruletypes.h cleanup \([\#1306](https://github.com/EQEmu/Server/pull/1306)\)  
**\[Thalix\]** Update command.cpp \([\#1289](https://github.com/EQEmu/Server/pull/1289)\)  
**\[Thalix\]** \[Crash\] Bugfix for zone crash caused by \#flymode -1 \([\#1291](https://github.com/EQEmu/Server/pull/1291)\)  
**\[TurmoilToad\]** Add category tags for Object methods. \([\#1232](https://github.com/EQEmu/Server/pull/1232)\)  
**\[TurmoilToad\]** Add category tags for corpse methods \([\#1234](https://github.com/EQEmu/Server/pull/1234)\)  
**\[TurmoilToad\]** Add category tags to new client methods. \([\#1233](https://github.com/EQEmu/Server/pull/1233)\)  
**\[TurmoilToad\]** Update perl\_questitem.cpp \([\#1227](https://github.com/EQEmu/Server/pull/1227)\)  
**\[TurmoilToad\]** \[Quest API\] Perl Client Annotations \([\#1224](https://github.com/EQEmu/Server/pull/1224)\)  
**\[TurmoilToad\]** \[Quest API\] Perl Door Annotations \([\#1241](https://github.com/EQEmu/Server/pull/1241)\)  
**\[TurmoilToad\]** \[Quest API\] Perl Entity List Annotations \([\#1243](https://github.com/EQEmu/Server/pull/1243)\)  
**\[TurmoilToad\]** \[Quest API\] Perl Group Annotations \([\#1261](https://github.com/EQEmu/Server/pull/1261)\)  
**\[TurmoilToad\]** \[Quest API\] Perl Hate Entry Annotations \([\#1244](https://github.com/EQEmu/Server/pull/1244)\)  
**\[TurmoilToad\]** \[Quest API\] Perl Mob Annotations \([\#1258](https://github.com/EQEmu/Server/pull/1258)\)  
**\[TurmoilToad\]** \[Quest API\] Perl NPC Annotations \([\#1245](https://github.com/EQEmu/Server/pull/1245)\)  
**\[TurmoilToad\]** \[Quest API\] Perl Raid Annotations \([\#1226](https://github.com/EQEmu/Server/pull/1226)\)  
**\[hg\]** Add missing includes to fix windows compile \([\#1314](https://github.com/EQEmu/Server/pull/1314)\)  
**\[hg\]** Throttle auto expedition leader changes \([\#1293](https://github.com/EQEmu/Server/pull/1293)\)  
**\[hg\]** \[Dynamic Zones\] Rename dynamic zone structs \([\#1327](https://github.com/EQEmu/Server/pull/1327)\)  
**\[hg\]** \[Expeditions\] Cleanup client dz safe return methods \([\#1300](https://github.com/EQEmu/Server/pull/1300)\)  
**\[hg\]** \[Expeditions\] Create common dz abstract class \([\#1312](https://github.com/EQEmu/Server/pull/1312)\)  
**\[hg\]** \[Expeditions\] Decouple dz updates from expeditions \([\#1303](https://github.com/EQEmu/Server/pull/1303)\)  
**\[hg\]** \[Expeditions\] Let dz process its expired state \([\#1310](https://github.com/EQEmu/Server/pull/1310)\)  
**\[hg\]** \[Expeditions\] Refactor expedition caching \([\#1315](https://github.com/EQEmu/Server/pull/1315)\)  
**\[hg\]** \[Expeditions\] Refactor expedition requests \([\#1301](https://github.com/EQEmu/Server/pull/1301)\)  
**\[hg\]** \[Expeditions\] Store description and leader name on dz \([\#1294](https://github.com/EQEmu/Server/pull/1294)\)  
**\[hg\]** \[Expeditions\] Track DZ member status in world \([\#1341](https://github.com/EQEmu/Server/pull/1341)\)  
**\[hg\]** \[Expeditions\] \[Quest API\] Add expedition IsLocked to Quest API \([\#1292](https://github.com/EQEmu/Server/pull/1292)\)  
**\[neckkola\]** Added new Perl/LUA GetSpellIDByBookSlot \([\#1151](https://github.com/EQEmu/Server/pull/1151)\)  
**\[splose\]** \[Rules\] Add rule 'GM:MinStatusToBypassLockedServer' \([\#1330](https://github.com/EQEmu/Server/pull/1330)\)  
**\[splose\]** add quest::get\_spell\_level\(uint16 spell\_id, uint8 class\_id\) \([\#1295](https://github.com/EQEmu/Server/pull/1295)\)  
**\[splose\]** setting spawn2.version to -1 will now properly spawn mobs in all zone versions \([\#1299](https://github.com/EQEmu/Server/pull/1299)\)

### 1/25/2021

**Kinglykrab**

* Add quest::message\(color, message\) to Perl.
* Add quest::whisper\(message\) to Perl.
* Add $client-&gt;HasDisciplineLearned\(spell\_id\) to Perl.
* Add eq.message\(color, message\) to Lua.
* Add eq.whisper\(message\) to Lua.
* Add client:HasDisciplineLearned\(spell\_id\) to Lua.
* Add 4 new special attacks to Perl and Lua.
  * IMMUNE\_DAMAGE\_CLIENT \(47\)
    * Immune to all damage except NPC damage.
  * IMMUNE\_DAMAGE\_NPC \(48\)
    * Immune to all damage except Client damage.
  * IMMUNE\_AGGRO\_CLIENT \(49\)
    * Immune to aggro by a Client.
  * IMMUNE\_AGGRO\_NPC \(50\)
    * Immune to aggro by an NPC, clients must attack directly to gain aggro, allows pet only boss mechanics and stuff.



### 1/3/2021

#### Kinglykrab

* Added $client-&gt;Fling\(\) to Perl.
* Added $client-&gt;SetEbonCrystals\(\) to Perl.
* Added $client-&gt;SetRadiantCrystals\(\) to Perl.
* Added client:GetTargetRingX\(\) to Lua.
* Added client:GetTargetRingY\(\) to Lua.
* Added client:GetTargetRingZ\(\) to Lua.
* Added client:Fling\(\) to Lua.
* Added client:SetEbonCrystals\(\) to Lua.
* Added client:SetRadiantCrystals\(\) to Lua.



