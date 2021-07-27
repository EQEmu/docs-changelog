---
description: EverQuest Emulator server changes for the year 2020
---

# 2021

### 7/27/2021

**\[Akkadius\]** \[Hotfix\] SendIllusion revert to October  
**\[Akkadius\]** \[Repositories\] Regenerate repositories with int64 support, reserved word support \([\#1440](https://github.com/EQEmu/Server/pull/1440)\)  
**\[Akkadius\]** \[Repository Generator\] Add int64/bigint support, add support for reserved words \([\#1439](https://github.com/EQEmu/Server/pull/1439)\)  
**\[Akkadius\]** \[Repository Usage\] Migrate NPC Scale Manager to use repositories \([\#1441](https://github.com/EQEmu/Server/pull/1441)\)  
**\[Dencelle\]** \[Code\] Addition of zone constants for hard coding \([\#1443](https://github.com/EQEmu/Server/pull/1443)\)  
**\[Dencelle\]** \[Commands\] Make \#maxskills work on target. \([\#1445](https://github.com/EQEmu/Server/pull/1445)\)  
**\[E Spause\]** Add SetGMStatus to LUA, cleanup unused variable, cleanup naming of new function added to Client class, remove unneeded return on void function. \([\#1471](https://github.com/EQEmu/Server/pull/1471)\)  
**\[Gangsta\]** \[Merchants\] Fix issue where an item purchased with 1 charges actually is bought with 0 charges  
**\[Gangsta\]** \[Bugfix\] Fixes guards assisting mobs against players \([\#1448](https://github.com/EQEmu/Server/pull/1448)\)  
**\[KayenEQ\]** Projectiles Update \([\#1468](https://github.com/EQEmu/Server/pull/1468)\)  
**\[KayenEQ\]** \[Feature\] New SPAs pass 1 \([\#1454](https://github.com/EQEmu/Server/pull/1454)\)  
**\[KayenEQ\]** \[Feature\] New SPAs pass 2 \([\#1459](https://github.com/EQEmu/Server/pull/1459)\)  
**\[KimLS\]** Fix for compile issue when you either don't have openSSL or you're using a version not supported by httplib  
**\[Kurt Gilpin\]** \[Inventory\] Remove Trader's Satchel ID from inventory.cpp \([\#1423](https://github.com/EQEmu/Server/pull/1423)\)  
**\[Michael Cook \(mackal\)\]** Add defines \(commented\) for further known SPAs \([\#1446](https://github.com/EQEmu/Server/pull/1446)\)  
**\[Michael Cook \(mackal\)\]** \[Bug Fix\] spell cast time cap issue introduced in [e5b9d72](https://github.com/EQEmu/Server/commit/e5b9d72b81e428aaac453281f127f1a4d83dd084) \([\#1435](https://github.com/EQEmu/Server/pull/1435)\)  
**\[Michael Cook \(mackal\)\]** \[Spells Cleanup\] Unify and add most hardcoded spell IDs \([\#1438](https://github.com/EQEmu/Server/pull/1438)\)  
**\[Natedog2012\]** Allow NPCs to aggro player pets with NPCAggro field set in database and new rule AggroPlayerPets set to true \([\#1450](https://github.com/EQEmu/Server/pull/1450)\)  
**\[splose\]** \[Quest API\] Add $client-&gt;SetGMStatus\(\) \([\#1465](https://github.com/EQEmu/Server/pull/1465)\)

### 6/12/2021

**\[Alex\]** \[Bots\] Add Bot scripting capabilities to the source. \([\#1378](https://github.com/EQEmu/Server/pull/1378)\)  
**\[Alex\]** \[Bots\] Remove hardcoded race-class combinations from bots. \([\#1375](https://github.com/EQEmu/Server/pull/1375)\)  
**\[Alex\]** \[Bug Fix\] Fix CMakeLists.txt so compile works. \([\#1387](https://github.com/EQEmu/Server/pull/1387)\)  
**\[Alex\]** \[Commands\] Add \#findclass \[search criteria\] command. \([\#1384](https://github.com/EQEmu/Server/pull/1384)\)  
**\[Alex\]** \[Commands\] Add \#viewzoneloot \[item id\] command. \([\#1382](https://github.com/EQEmu/Server/pull/1382)\)  
**\[Alex\]** \[Pets\] Unhardcode Beastlord pet values. \([\#1379](https://github.com/EQEmu/Server/pull/1379)\)  
**\[Alex\]** \[Quest API\] Add ChangeLastName\(\) and ClearLastName\(\) to Lua. \([\#1386](https://github.com/EQEmu/Server/pull/1386)\)  
**\[Alex\]** \[Quest API\] Add SetHideMe\(\) to Perl/Lua. \([\#1388](https://github.com/EQEmu/Server/pull/1388)\)  
**\[Alex\]** \[Quest API\] Add getcleannpcnamebyid\(npc\_id\) to Perl/Lua. \([\#1383](https://github.com/EQEmu/Server/pull/1383)\)  
**\[Alex\]** \[Quest API\] Add several methods to Perl/Lua API for LDoN stuff. \([\#1356](https://github.com/EQEmu/Server/pull/1356)\)  
**\[Alex\]** \[Shared Bank\] Add additional popup to shared bank warning message, as client-side filters can cause the message to be unseen. \([\#1368](https://github.com/EQEmu/Server/pull/1368)\)  
**\[Alex\]** \[Spells\] Adds a rule to allow right-click memorize from spell scrolls. \([\#1377](https://github.com/EQEmu/Server/pull/1377)\)  
**\[Dencelle\]** \[Bug Fix\] EntityList::AESpell fix for Pacify / Mez \([\#1354](https://github.com/EQEmu/Server/pull/1354)\)  
**\[Dencelle\]** \[Bug Fix\] Fix for charges not being sold correctly \([\#1357](https://github.com/EQEmu/Server/pull/1357)\)  
**\[Dencelle\]** \[Bug Fix\] NPC not breaking charm correctly \([\#1363](https://github.com/EQEmu/Server/pull/1363)\)  
**\[Kurt Gilpin\]** \(HEAD -&gt; master, origin/master\) Fix crash when casting with no target \([\#1390](https://github.com/EQEmu/Server/pull/1390)\)  
**\[Michael Cook \(mackal\)\]** Magic numbers bad \([\#1373](https://github.com/EQEmu/Server/pull/1373)\)  
**\[Michael Cook \(mackal\)\]** This skill bonus was suppose to only apply to monks with epics \([\#1364](https://github.com/EQEmu/Server/pull/1364)\)  
**\[Michael Cook \(mackal\)\]** \[Bug Fix\] EntityList::AESpell was off by one \([\#1351](https://github.com/EQEmu/Server/pull/1351)\)  
**\[Michael Cook \(mackal\)\]** \[Fix\] Fix Spell Cast Time reduction issues \([\#1369](https://github.com/EQEmu/Server/pull/1369)\)  
**\[Michael Cook \(mackal\)\]** \[Quest API\] Add Lua\_Mob::GetShuffledHateList \([\#1381](https://github.com/EQEmu/Server/pull/1381)\)  
**\[Michael\]** \[Rule\] Allow Skill ups from items \(Default: On\) \([\#1376](https://github.com/EQEmu/Server/pull/1376)\)  
**\[Paul Coene\]** \[GM Command\] \#list npcs Goto option now goes to higher Z if selected NPC is a boat. \([\#1349](https://github.com/EQEmu/Server/pull/1349)\)  
**\[RoTPvP\]** \[PVP\] Pvp guard assist code. \(Guards will assist in PvP based on faction\) \([\#1367](https://github.com/EQEmu/Server/pull/1367)\)  
**\[RoTPvP\]** \[Spells\] Added a pet check to Cazic Touch \([\#1365](https://github.com/EQEmu/Server/pull/1365)\)  
**\[TurmoilToad\]** \[Docs\] Create CODE\_OF\_CONDUCT.md \([\#1360](https://github.com/EQEmu/Server/pull/1360)\)  
**\[hg\]** \[Dynamic Zones\] Store min and max players on dz \([\#1355](https://github.com/EQEmu/Server/pull/1355)\)  
**\[hg\]** \[Expeditions\] Avoid expedition leader change if only member \([\#1372](https://github.com/EQEmu/Server/pull/1372)\)  
**\[hg\]** \[Expeditions\] Move member compass updates to dz \([\#1371](https://github.com/EQEmu/Server/pull/1371)\)  
**\[hg\]** \[Expeditions\] Store members on dynamic zone \([\#1358](https://github.com/EQEmu/Server/pull/1358)\)  
**\[hg\]** \[Quest API\] Add write overloads to lua packet quest api \([\#1366](https://github.com/EQEmu/Server/pull/1366)\)  
**\[hg\]** \[Repository Generator\] Fix repository generator on windows \([\#1353](https://github.com/EQEmu/Server/pull/1353)\)  
**\[regneq\]** \[Time\] strict spawn\_events now take into account EQ minute. \([\#1370](https://github.com/EQEmu/Server/pull/1370)\)  
**\[splose\]** \[Bug Fix\] Allow GMs to chat when stunned \([\#1380](https://github.com/EQEmu/Server/pull/1380)\)  
**\[splose\]** \[Rules\] Add rule to allow you to cast invis on already invis'd players \([\#1361](https://github.com/EQEmu/Server/pull/1361)\)

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



