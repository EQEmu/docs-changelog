---
description: EverQuest Emulator server changes for the year 2020
---

# 2021

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



