---
description: EverQuest Emulator server changes for the year 2020
---

# 2020

## 7/30/2020

**Akkadius**

[This PR / changelog covers many things](https://github.com/EQEmu/Server/pull/1094); it would be preferred to not have a PR this large ever but considering the sweeping changes, it needed very careful testing, coordination and rollout

<table>
  <thead>
    <tr>
      <th style="text-align:left">Component</th>
      <th style="text-align:left">Reference</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>Expansions Support / Content Filtering</b>
      </td>
      <td style="text-align:left">
        <p></p>
        <p><a href="https://eqemu.gitbook.io/server/in-development/project-peq-expansions/expansion-content-filtering">https://eqemu.gitbook.io/server/in-development/project-peq-expansions/expansion-content-filtering</a>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Multi Tenancy</b>
      </td>
      <td style="text-align:left">
        <p></p>
        <p><a href="https://eqemu.gitbook.io/server/categories/database/multi-tenancy">https://eqemu.gitbook.io/server/categories/database/multi-tenancy</a>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Repository Pattern (Developer Tool)</b>
      </td>
      <td style="text-align:left">
        <p></p>
        <p><a href="https://eqemu.gitbook.io/server/in-development/developer-area/repositories">https://eqemu.gitbook.io/server/in-development/developer-area/repositories</a>
        </p>
      </td>
    </tr>
  </tbody>
</table>

{% hint style="info" %}
**This PR has been running on PEQ for over 3 months stable**
{% endhint %}

{% hint style="info" %}
**PEQ Editor Accompanying Branch \(JJ\)** [https://github.com/ProjectEQ/peqphpeditor/compare/min-max-expansions](https://github.com/ProjectEQ/peqphpeditor/compare/min-max-expansions)
{% endhint %}

### General

* Add `Merchants` and `ZonePoints` logging categories
* Add fix for object display issues on RoF2 where objects would float, we are using GroundZ to correct these. Previous clients auto corrected objects and snapped them to the ground level, newer clients do not do this
* Added `WorldContentService` which has the responsibility of setting / getting content context for the server, expansions, flags etc.
* Added an optional second database connection to the config "content\_database" that will use a separate database connection for queries that target content tables. If none is specified it falls back to the default connection pointer
* Added connection labels to MySQL connect messages
* Added magical global helper methods `ZoneID(string short_name)` `ZoneName(zone_id)` `ZoneLongName(zone_id)` which are all pre-loaded in memory to be used at the zone or world level for common needs
* Added official single source of truth in `database_schema.h` which defines different table types `player`, `content`, `server`, `state`, `queryserv`, `login`, `version`
* Fix issues with world CLI interface returning exit code 1 \(error\) versus exit code 0 \(success\)
* Saylinks are added to `#fi` command for summoning items

### Performance Improvements

* Task goallists now bulk load
* Spawns prefer bulk loading
* Improvements to grid loading logic \(bulk load\)

### New Commands

* Added in-command `#gearup` - which takes in tooling data to automatically gear a GM test toon with expansion specific best-in-class gear
* Added in-game command `#copycharacter [source_char_name] [dest_char_name] [dest_account_name]`
* `Added console CLI command via world character:copy-character`

**Connection Label Messages**

```text
[ZoneServer] [Info] [MySQL] Connection [default] database [peq] at [mariadb]:[3306]
[ZoneServer] [Info] [MySQL] Connection [content] database [peq_content] at [content-cdn.projecteq.net]:[16033]    
```

### Quests

New methods available to support expansion & content filtering

{% tabs %}
{% tab title="Perl" %}
```perl
quest::is_content_flag_enabled(string flag_name)
quest::set_content_flag(string flag_name, bool enabled)

quest::is_classic_enabled()
quest::is_the_ruins_of_kunark_enabled()
quest::is_the_scars_of_velious_enabled()
quest::is_the_shadows_of_luclin_enabled()
quest::is_the_planes_of_power_enabled()
quest::is_the_legacy_of_ykesha_enabled()
quest::is_lost_dungeons_of_norrath_enabled()
quest::is_gates_of_discord_enabled()
quest::is_omens_of_war_enabled()
quest::is_dragons_of_norrath_enabled()
quest::is_depths_of_darkhollow_enabled()
quest::is_prophecy_of_ro_enabled()
quest::is_the_serpents_spine_enabled()
quest::is_the_buried_sea_enabled()
quest::is_secrets_of_faydwer_enabled()
quest::is_seeds_of_destruction_enabled()
quest::is_underfoot_enabled()
quest::is_house_of_thule_enabled()
quest::is_veil_of_alaris_enabled()
quest::is_rain_of_fear_enabled()
quest::is_call_of_the_forsaken_enabled()
quest::is_the_darkend_sea_enabled()
quest::is_the_broken_mirror_enabled()
quest::is_empires_of_kunark_enabled()
quest::is_ring_of_scale_enabled()
quest::is_the_burning_lands_enabled()
quest::is_torment_of_velious_enabled()
quest::is_current_expansion_classic()
quest::is_current_expansion_the_ruins_of_kunark()
quest::is_current_expansion_the_scars_of_velious()
quest::is_current_expansion_the_shadows_of_luclin()
quest::is_current_expansion_the_planes_of_power()
quest::is_current_expansion_the_legacy_of_ykesha()
quest::is_current_expansion_lost_dungeons_of_norrath()
quest::is_current_expansion_gates_of_discord()
quest::is_current_expansion_omens_of_war()
quest::is_current_expansion_dragons_of_norrath()
quest::is_current_expansion_depths_of_darkhollow()
quest::is_current_expansion_prophecy_of_ro()
quest::is_current_expansion_the_serpents_spine()
quest::is_current_expansion_the_buried_sea()
quest::is_current_expansion_secrets_of_faydwer()
quest::is_current_expansion_seeds_of_destruction()
quest::is_current_expansion_underfoot()
quest::is_current_expansion_house_of_thule()
quest::is_current_expansion_veil_of_alaris()
quest::is_current_expansion_rain_of_fear()
quest::is_current_expansion_call_of_the_forsaken()
quest::is_current_expansion_the_darkend_sea()
quest::is_current_expansion_the_broken_mirror()
quest::is_current_expansion_empires_of_kunark()
quest::is_current_expansion_ring_of_scale()
quest::is_current_expansion_the_burning_lands()
quest::is_current_expansion_torment_of_velious()
```
{% endtab %}

{% tab title="Lua" %}
```
eq.is_content_flag_enabled(string flag_name)
eq.set_content_flag(string flag_name, bool enabled)

eq.is_classic_enabled()
eq.is_the_ruins_of_kunark_enabled()
eq.is_the_scars_of_velious_enabled()
eq.is_the_shadows_of_luclin_enabled()
eq.is_the_planes_of_power_enabled()
eq.is_the_legacy_of_ykesha_enabled()
eq.is_lost_dungeons_of_norrath_enabled()
eq.is_gates_of_discord_enabled()
eq.is_omens_of_war_enabled()
eq.is_dragons_of_norrath_enabled()
eq.is_depths_of_darkhollow_enabled()
eq.is_prophecy_of_ro_enabled()
eq.is_the_serpents_spine_enabled()
eq.is_the_buried_sea_enabled()
eq.is_secrets_of_faydwer_enabled()
eq.is_seeds_of_destruction_enabled()
eq.is_underfoot_enabled()
eq.is_house_of_thule_enabled()
eq.is_veil_of_alaris_enabled()
eq.is_rain_of_fear_enabled()
eq.is_call_of_the_forsaken_enabled()
eq.is_the_darkend_sea_enabled()
eq.is_the_broken_mirror_enabled()
eq.is_empires_of_kunark_enabled()
eq.is_ring_of_scale_enabled()
eq.is_the_burning_lands_enabled()
eq.is_torment_of_velious_enabled()
eq.is_current_expansion_classic()
eq.is_current_expansion_the_ruins_of_kunark()
eq.is_current_expansion_the_scars_of_velious()
eq.is_current_expansion_the_shadows_of_luclin()
eq.is_current_expansion_the_planes_of_power()
eq.is_current_expansion_the_legacy_of_ykesha()
eq.is_current_expansion_lost_dungeons_of_norrath()
eq.is_current_expansion_gates_of_discord()
eq.is_current_expansion_omens_of_war()
eq.is_current_expansion_dragons_of_norrath()
eq.is_current_expansion_depths_of_darkhollow()
eq.is_current_expansion_prophecy_of_ro()
eq.is_current_expansion_the_serpents_spine()
eq.is_current_expansion_the_buried_sea()
eq.is_current_expansion_secrets_of_faydwer()
eq.is_current_expansion_seeds_of_destruction()
eq.is_current_expansion_underfoot()
eq.is_current_expansion_house_of_thule()
eq.is_current_expansion_veil_of_alaris()
eq.is_current_expansion_rain_of_fear()
eq.is_current_expansion_call_of_the_forsaken()
eq.is_current_expansion_the_darkend_sea()
eq.is_current_expansion_the_broken_mirror()
eq.is_current_expansion_empires_of_kunark()
eq.is_current_expansion_ring_of_scale()
eq.is_current_expansion_the_burning_lands()
eq.is_current_expansion_torment_of_velious()
```
{% endtab %}
{% endtabs %}

### Repositories

**Highlights**

* Heavily reducing the mental overhead of having to interact with the database at the programmatic level
* It creates an object representation of our tables \(persistence layer\) with a 1:1 mapping with what is in the source by having row values stored in a struct \(Data Transfer Object\)
* We reduce manual overhead by having code generation generate our database table representations
* Ease of maintenance; whenever we make schema changes, rerunning the repository updates fields and subsequent methods keeping code changes minimal 

**Methods Implemented**

* Single insertion covered by `InsertOne`
* Single update covered by `UpdateOne`
* Single delete covered by `DeleteOne`
* Single select covered by `FindOne`
* Bulk selection method via filtered `GetWhere(std::string where_filter)`
* Bulk deletion method via filtered `DeleteWhere(std::string where_filter)`
* Bulk insertion methods handled automatically via `InsertMany`
* Select all covered by `All`

**Code Generation**

This is a result of the repository generator located at 

```text
./utils/scripts/generators/repository-generator.pl

# Help
perl ~/code/utils/scripts/generators/repository-generator.pl [server-location] [table_name|all]

# Example
perl ~/code/utils/scripts/generators/repository-generator.pl ~/server/ all
```

**Example Use \(How do I use this?\)**

Starting at line 358 in the following Gist is an example CLI command that uses all of the above methods as examples; above line 358 is an example of what the a repository can look like

[https://gist.github.com/Akkadius/e341974521692000aa1eeaa2b6dcb091\#file-gistfile1-cpp-L358](https://gist.github.com/Akkadius/e341974521692000aa1eeaa2b6dcb091#file-gistfile1-cpp-L358)

## 7/7/2020

**Kinglykrab**

**Add hot reload saylinks.**

**Completely overhauled cross zone and world wide methods in quest API.**

{% tabs %}
{% tab title="Perl" %}
```text
quest::crosszonecastspellbycharid(character_id, spell_id);
quest::crosszonecastspellbygroupid(group_id, spell_id);
quest::crosszonecastspellbyraidid(raid_id, spell_id);
quest::crosszonecastspellbyguildid(guild_id, spell_id);
quest::crosszonedisabletaskbycharid(character_id, task_id);
quest::crosszonedisabletaskbygroupid(group_id, task_id);
quest::crosszonedisabletaskbyraidid(raid_id, task_id);
quest::crosszonedisabletaskbyguildid(guild_id, task_id);
quest::crosszoneenabletaskbycharid(character_id, task_id);
quest::crosszoneenabletaskbygroupid(group_id, task_id);
quest::crosszoneenabletaskbyraidid(raid_id, task_id);
quest::crosszoneenabletaskbyguildid(guild_id, task_id);
quest::crosszonefailtaskbycharid(character_id, task_id);
quest::crosszonefailtaskbygroupid(group_id, task_id);
quest::crosszonefailtaskbyraidid(raid_id, task_id);
quest::crosszonefailtaskbyguildid(guild_id, task_id);
quest::crosszonemoveinstancebycharid(character_id, instance_id);
quest::crosszonemoveinstancebygroupid(group_id, instance_id);
quest::crosszonemoveinstancebyraidid(raid_id, instance_id);
quest::crosszonemoveinstancebyguildid(guild_id, instance_id);
quest::crosszoneremovespellbycharid(character_id, spell_id);
quest::crosszoneremovespellbygroupid(group_id, spell_id);
quest::crosszoneremovespellbyraidid(raid_id, spell_id);
quest::crosszoneremovespellbyguildid(guild_id, spell_id);
quest::crosszoneresetactivitybycharid(character_id, task_id, activity_id);
quest::crosszoneresetactivitybygroupid(group_id, task_id, activity_id);
quest::crosszoneresetactivitybyraidid(raid_id, task_id, activity_id);
quest::crosszoneresetactivitybyguildid(guild_id, task_id, activity_id);
quest::crosszoneupdateactivitybycharid(character_id, task_id, activity_id, activity_count);
quest::crosszoneupdateactivitybygroupid(group_id, task_id, activity_id, activity_count);
quest::crosszoneupdateactivitybyraidid(raid_id, task_id, activity_id, activity_count);
quest::crosszoneupdateactivitybyguildid(guild_id, task_id, activity_id, activity_count);
quest::worldwideassigntask(task_id, enforce_level_requirement, min_status, max_status);
quest::worldwidecastspell(spell_id, min_status, max_status);
quest::worldwidedisabletask(task_id, min_status, max_status);
quest::worldwideenabletask(task_id, min_status, max_status);
quest::worldwidefailtask(task_id, min_status, max_status);
quest::worldwidemessage(type, message, min_status, max_status);
quest::worldwidemove(zone_short_name, min_status, max_status);
quest::worldwidemoveinstance(instance_id, min_status, max_status);
quest::worldwideremovespell(spell_id, min_status, max_status);
quest::worldwideremovetask(task_id, min_status, max_status);
quest::worldwideresetactivity(task_id, activity_id, min_status, max_status);
quest::worldwidesetentityvariableclient(variable_name, variable_value, min_status, max_status);
quest::worldwidesetentityvariablenpc(variable_name, variable_value);
quest::worldwidesignalclient(signal, min_status, max_status);
quest::worldwidesignalnpc(signal);
quest::worldwideupdateactivity(task_id, activity_id, activity_count, min_status, max_status);
```
{% endtab %}

{% tab title="Lua" %}
```lua
eq.cross_zone_cast_spell_by_char_id(character_id, spell_id);
eq.cross_zone_cast_spell_by_group_id(group_id, spell_id);
eq.cross_zone_cast_spell_by_raid_id(raid_id, spell_id);
eq.cross_zone_cast_spell_by_guild_id(guild_id, spell_id);
eq.cross_zone_disable_task_by_char_id(character_id, task_id);
eq.cross_zone_disable_task_by_group_id(group_id, task_id);
eq.cross_zone_disable_task_by_raid_id(raid_id, task_id);
eq.cross_zone_disable_task_by_guild_id(guild_id, task_id);
eq.cross_zone_enable_task_by_char_id(character_id, task_id);
eq.cross_zone_enable_task_by_group_id(group_id, task_id);
eq.cross_zone_enable_task_by_raid_id(raid_id, task_id);
eq.cross_zone_enable_task_by_guild_id(guild_id, task_id);
eq.cross_zone_fail_task_by_char_id(character_id, task_id);
eq.cross_zone_fail_task_by_group_id(group_id, task_id);
eq.cross_zone_fail_task_by_raid_id(raid_id, task_id);
eq.cross_zone_fail_task_by_guild_id(guild_id, task_id);
eq.cross_zone_move_instance_by_char_id(character_id, instance_id);
eq.cross_zone_move_instance_by_group_id(group_id, instance_id);
eq.cross_zone_move_instance_by_raid_id(raid_id, instance_id);
eq.cross_zone_move_instance_by_guild_id(guild_id, instance_id);
eq.cross_zone_remove_spell_by_char_id(character_id, spell_id);
eq.cross_zone_remove_spell_by_group_id(group_id, spell_id);
eq.cross_zone_remove_spell_by_raid_id(raid_id, spell_id);
eq.cross_zone_remove_spell_by_guild_id(guild_id, spell_id);
eq.cross_zone_reset_activity_by_char_id(character_id, task_id, activity_id);
eq.cross_zone_reset_activity_by_group_id(group_id, task_id, activity_id);
eq.cross_zone_reset_activity_by_raid_id(raid_id, task_id, activity_id);
eq.cross_zone_reset_activity_by_guild_id(guild_id, task_id, activity_id);
eq.cross_zone_update_activity_by_char_id(character_id, task_id, activity_id, activity_count);
eq.cross_zone_update_activity_by_group_id(group_id, task_id, activity_id, activity_count);
eq.cross_zone_update_activity_by_raid_id(raid_id, task_id, activity_id, activity_count);
eq.cross_zone_update_activity_by_guild_id(guild_id, task_id, activity_id, activity_count);
eq.world_wide_assign_task(task_id, enforce_level_requirement, min_status, max_status);
eq.world_wide_cast_spell(spell_id, min_status, max_status);
eq.world_wide_disable_task(task_id, min_status, max_status);
eq.world_wide_enable_task(task_id, min_status, max_status);
eq.world_wide_fail_task(task_id, min_status, max_status);
eq.world_wide_message(type, message, min_status, max_status);
eq.world_wide_move(zone_short_name, min_status, max_status);
eq.world_wide_move_instance(instance_id, min_status, max_status);
eq.world_wide_remove_spell(spell_id, min_status, max_status);
eq.world_wide_remove_task(task_id, min_status, max_status);
eq.world_wide_reset_activity(task_id, activity_id, min_status, max_status);
eq.world_wide_set_entity_variable_client(variable_name, variable_value, min_status, max_status);
eq.world_wide_set_entity_variable_npc(variable_name, variable_value);
eq.world_wide_signal_client(signal, min_status, max_status);
eq.world_wide_signal_npc(signal);
eq.world_wide_update_activity(task_id, activity_id, activity_count, min_status, max_status);
```
{% endtab %}
{% endtabs %}

## 6/30/2020

**Kinglykrab**

**Add GetDisplayAC\(\) to Perl/Lua.**

{% tabs %}
{% tab title="Perl" %}
```perl
$client->GetDisplayAC();
```
{% endtab %}

{% tab title="Lua" %}
```lua
client:GetDisplayAC();
```
{% endtab %}
{% endtabs %}

**Add DyeArmorBySlot\(\) to Perl/Lua.**

{% tabs %}
{% tab title="Perl" %}
```perl
$client->DyeArmorBySlot(slot, red, green, blue, [use_tint = 0x00]);
```
{% endtab %}

{% tab title="Lua" %}
```lua
client:DyeArmorBySlot(slot, red, green, blue, [use_tint = 0x00]);
```
{% endtab %}
{% endtabs %}

**Add MoveZoneInstance methods to Perl/Lua.**

{% tabs %}
{% tab title="Perl" %}
```perl
$client->MoveZoneInstance(instance_id);
$client->MoveZoneInstanceGroup(instance_id);
$client->MoveZoneInstanceRaid(instance_id);
```
{% endtab %}

{% tab title="Lua" %}
```lua
client:MoveZoneInstance(instance_id);
client:MoveZoneInstanceGroup(instance_id);
client:MoveZoneInstanceRaid(instance_id);
```
{% endtab %}
{% endtabs %}

**Add cross-zone player move utilities.**

{% tabs %}
{% tab title="Perl" %}
```perl
quest::crosszonemoveplayerbycharid(character_id, zone_short_name);
quest::crosszonemoveplayerbygroupid(group_id, zone_short_name);
quest::crosszonemoveplayerbyraidid(raid_id, zone_short_name);
quest::crosszonemoveplayerbyguildid(guild_id, zone_short_name);
```
{% endtab %}

{% tab title="Lua" %}
```lua
eq.crosszonemoveplayerbycharid(character_id, zone_short_name);
eq.crosszonemoveplayerbygroupid(group_id, zone_short_name);
eq.crosszonemoveplayerbyraidid(raid_id, zone_short_name);
eq.crosszonemoveplayerbyguildid(guild_id, zone_short_name);
```
{% endtab %}
{% endtabs %}

## 6/28/2020

**Akkadius**

* Fixed an issue where when a client first enters a zone; an NPC may not be aware of their presence immediately
* Fixed a UCS issue where a crash or another UCS connection would delete connection pointers; this should keep UCS connected more reliably
* Lowered the rate in which animation packets are throttled to 500ms from 1000ms; this should keep faster animations from being gated from being sent

**Kinglykrab**

* Fix $npc-&gt;RecalculateSkills\(\) in Perl.

#### Added Quest API MoveZone Methods

{% tabs %}
{% tab title="Perl" %}
```perl
$client->MoveZone(zone_short_name);
$client->MoveZoneGroup(zone_short_name);
$client->MoveZoneRaid(zone_short_name);
```
{% endtab %}

{% tab title="Lua" %}
```
client:MoveZone(zone_short_name);
client:MoveZoneGroup(zone_short_name);
client:MoveZoneRaid(zone_short_name);
```
{% endtab %}
{% endtabs %}

#### Added Quest API CrossZone Task Methods

{% tabs %}
{% tab title="Perl" %}
```perl
quest::crosszoneassigntaskbycharid(character_id, task_id, enforce_level_requirement);
quest::crosszoneassigntaskbygroupid(group_id, task_id, enforce_level_requirement);
quest::crosszoneassigntaskbyraidid(raid_id, task_id, enforce_level_requirement);
quest::crosszoneassigntaskbyguildid(guild_id, task_id, enforce_level_requirement);
```
{% endtab %}

{% tab title="Lua" %}
```lua
eq.cross_zone_assign_task_by_char_id(character_id, task_id, enforce_level_requirement);
eq.cross_zone_assign_task_by_group_id(group_id, task_id, enforce_level_requirement);
eq.cross_zone_assign_task_by_raid_id(raid_id, task_id, enforce_level_requirement);
eq.cross_zone_assign_task_by_guild_id(guild_id, task_id, enforce_level_requirement);
```
{% endtab %}
{% endtabs %}

#### Added Quest API Discipline Task Methods

{% tabs %}
{% tab title="Perl" %}
```perl
$client->GetDisciplineTimer(timer_id);
$client->ResetDisciplineTimer(timer_id);
```
{% endtab %}

{% tab title="Lua" %}
```lua
client:GetDisciplineTimer(timer_id);
client:ResetDisciplineTimer(timer_id);
```
{% endtab %}
{% endtabs %}

## 6/23/2020

**Noudess**

Updated \#grid show command to use alphabetic names so names display properly \(numerics were getting stripped\) and stacked the names of nodes that are in the same \#loc.

Added code to make sure that mobs that call for help, complete that activity before starting to move toward target.  As written \(previously\) a mob could be out of earshot of his neighbors because movement started immediately.  It was a race condition that nearly always resulted in mobs within the attacked mobs assist radius not hearing the call.

**Kinglykrab**

Added command \#findrace \[name\|id\].

![](../.gitbook/assets/image%20%283%29.png)

Added zone ID to \#findzone.

![](../.gitbook/assets/image%20%284%29.png)

Added eq.zone\(short\_name\) to Lua.

Added eq.zone\_group\(short\_name\) to Lua.

Added eq.zone\_raid\(short\_name\) to Lua.

Added quest::zonegroup\(short\_name\) to Perl.

Added quest::zoneraid\(short\_name\) to Perl.

## 5/26/2020

**Noudess**

SQL to load correct mods into faction\_list\_mod for Drakkin and Guktan races as well as Agnostic deity mods. Only to be used on databases converted to using the client faction ids.SQL found in optional SQL area as: utils/sql/git/optional/drakkin\_guktan\_faction\_data.sql



## 5/11/2020

**Kinglykrab**

### Added GetNPCBySpawnID\(\) to Perl/Lua.

{% tabs %}
{% tab title="Perl" %}
```perl
$entity_list->GetNPCBySpawnID(spawn_id);
```
{% endtab %}

{% tab title="Lua" %}
```lua
eq.get_entity_list():GetNPCBySpawnID(spawn_id);
```
{% endtab %}
{% endtabs %}

### Add several cross zone methods to Perl/Lua.

{% tabs %}
{% tab title="Perl" %}
```perl
quest::crosszonemessageplayerbygroupid(type, group_id, message);
quest::crosszonemessageplayerbyraidid(type, raid_id, message);
quest::crosszonemessageplayerbyguildid(type, guild_id, message);
quest::crosszonesignalclientbygroupid(group_id, value);
quest::crosszonesignalclientbyraidid(raid_id, value);
quest::crosszonesignalclientbyguildid(guild_id, value);
quest::crosszonesetentityvariablebygroupid(group_id, value);
quest::crosszonesetentityvariablebyraidid(raid_id, value);
quest::crosszonesetentityvariablebyguildid(guild_id, value);
```
{% endtab %}

{% tab title="Lua" %}
```lua
eq.cross_zone_message_player_by_group_id(type, group_id, message);
eq.cross_zone_message_player_by_raid_id(type, raid_id, message);
eq.cross_zone_message_player_by_guild_id(type, guild_id, message);
eq.cross_zone_signal_client_by_group_id(group_id, value);
eq.cross_zone_signal_client_by_raid_id(group_id, value);
eq.cross_zone_signal_client_by_guild_id(guild_id, value);
eq.cross_zone_set_entity_variable_by_group_id(group_id, value);
eq.cross_zone_set_entity_variable_by_raid_id(raid_id, value);
eq.cross_zone_set_entity_variable_by_guild_id(guild_id, value);
```
{% endtab %}
{% endtabs %}

## 4/14/2020

**Akkadius**

### UCS / Raid / Zone Fixes

**Raid::GetRaidByClient**

On PEQ we noticed via zone with high CPU footprint spending tons of time in in function `Raid::GetRaidByClient` where we excessively loop through all raids in zone, all members in the raid to return back a simple raid pointer. Now, we cache the pointer lookup instead of running the entire loop constantly. For perspective, with 100 toons in a zone all in a raid, you will easily see 4k/s calls to this function which adds up on a CPU profile \(nuts\)

**CPU Profile** [https://gist.github.com/Akkadius/a5c55654d4b729697964f938c824030f](https://gist.github.com/Akkadius/a5c55654d4b729697964f938c824030f)  
**Call Measurement Example**

```text
eqemu@ce0931611614:~$ tail -f ~/server/logs/**/*.log | grep "returning cached raid" | pv -lr 2>&1 >/dev/null
[4.04k/s]
```

**UCS**

We also noticed UCS sucking up a lot of CPU with 1,500 players online

**CPU Profile** [https://gist.github.com/Akkadius/14efe565caf468cc892293fd95cc0377](https://gist.github.com/Akkadius/14efe565caf468cc892293fd95cc0377)

* Converted to a less aggressive loop frequency 31.25 FPS and converted to using UV library
* No longer load characters into UCS context that are soft deleted
* Fixed UCS bug where it would not reconnect properly after a crash / improper shutdown
* Fixed UCS bug where it was not registering a new connection properly, and sending a "Not Available" to all zones right after it is in fact "Available"
* Added Logging in zone that clearly says whether or not UCS is online or not
* Properly removing UCS connected clients even if the /q /ex connections resolving by sending keepalive packets [\#735](https://github.com/EQEmu/Server/issues/735) this prevents UCS from looping over ghosted clients making unnecessary database calls and sending improper connected client counts
* Removed tons of verbose LogInfo logging and replaced the calls for LogDebug as it was writing to disk excessively for mostly debugging related information

**Zone**

* We are now properly shutting down zone processes by killing the UV loop instead of doing a hard process exit, allowing the zone to shut everything else down gracefully

## 4/9/2020

**Akkadius**

### Implement SendToGuildHall and Improve Instance ID Cycling

Instead of purging immediately expired instances every 7.5 minutes, we will purge expired instances from the database table after they've been completely expired for an entire day every 7.5 minutes. The reason for this is that the code will still determine that an instance is expired when it needs to; but in order to not re-use the same instance ID not long after it had been freed while a zone is still online with the same instance ID, we're simply going to wait a grace period of 1 day to purge those entries as it will not harm anything

Client::SendToGuildHall\(\) will send a client to a Guild Hall instance for 90 days based on a configurable rule. This will send the player to a Guild Hall instance regardless of whether they are in a Guild or not and it is up to the discretion of the server operator to check for guild id before making the call. If you are not guilded, you share an instance with other non-guilded players

We pull instance remaining time out of the database once on zone bootup because the timer class is returning the value in milliseconds which causes the values to overflow and improperly show remaining instance time for instances that are open for long period of time

Created new rule category `Instances`

```text
RULE_INT(Instances, ReservedInstances, 30, "Will reserve this many instance ids for globals... probably not a good idea to change this while a server is running")
RULE_BOOL(Instances, RecycleInstanceIds, true, "Will recycle free instance ids instead of gradually running out at 32k")
RULE_INT(Instances, GuildHallExpirationDays, 90, "Amount of days before a Guild Hall instance expires")
```

This exports Lua / Perl method `client->SendToGuildHall`

## 4/5/2020

**Kinglykrab**

* Added getcharidbyname\(name\) to Perl/Lua.

{% tabs %}
{% tab title="Perl" %}
```perl
quest::getcharidbyname(name);
```
{% endtab %}

{% tab title="Lua" %}
```lua
eq.get_char_id_by_name(name);
```
{% endtab %}
{% endtabs %}

* Added getcharnamebyid\(char\_id\) to Perl/Lua.

{% tabs %}
{% tab title="Perl" %}
```perl
quest::getcharnamebyid(char_id);
```
{% endtab %}

{% tab title="Lua" %}
```lua
eq.get_char_name_by_id(char_id);
```
{% endtab %}
{% endtabs %}

## 3/31/2020

**Kinglykrab**

* Added getitemname\(item\_id\) to Perl/Lua.

{% tabs %}
{% tab title="Perl" %}
```perl
quest::getitemname(item_id);
```
{% endtab %}

{% tab title="Lua" %}
```lua
eq.get_item_name(item_id);
```
{% endtab %}
{% endtabs %}

* Added getspellname\(spell\_id\) to Perl/Lua.

{% tabs %}
{% tab title="Perl" %}
```perl
quest::getspellname(spell_id);
```
{% endtab %}

{% tab title="Lua" %}
```lua
eq.get_spell_name(item_id);
```
{% endtab %}
{% endtabs %}

* Added gettaskname\(task\_id\) to Perl/Lua.

{% tabs %}
{% tab title="Perl" %}
```perl
quest::gettaskname(task_id);
```
{% endtab %}

{% tab title="Lua" %}
```lua
eq.get_task_name(task_id);
```
{% endtab %}
{% endtabs %}

* Added CheckInstanceByCharID\(instance\_id, char\_id\) to Perl/Lua.

{% tabs %}
{% tab title="Perl" %}
```perl
quest::CheckInstanceByCharID(instance_id, char_id);
```
{% endtab %}

{% tab title="Lua" %}
```lua
eq.check_instance_by_char_id(instance_id, char_id);
```
{% endtab %}
{% endtabs %}

## 3/5/2020

**Noudess**

* Added a new field \(always\_aggro\_foes\) to npc\_types.  If non-zero, the npc/mob will always aggro foes regardless of intelligence or level.  This was so mobs such as the int casters in Befallen, who will agro their enemies regardless of level and I didn't want to have to reduce the \_int field of INT caster NPCs to achieve the aggro.

## 3/2/2020

#### Uleat

### Monk Bot Changes

* Added a 'monk' class special attack timer to class NPC
* Monk bots will now use the ability `Tiger Claw` on a seperate timer from the other disciplines - resulting in an additional attack
* Bot usage of `Master Wu's Technique` now falls inline with current client behavior \(rules and all\)
* Added bot owner option `monkwumessage` to toggle a notification message to the bot's owner whenever `MWT` triggers \(off by default .. use `^oo monkwumessage` to enable/disable\)

**Special Note:**

By default, all classes process class attacks based on active timers. This involves checking attackability of target with every call - which is VERY expensive when done every server processing cycle since the timer is always 'ready.'

I added code to disable 'class' timers in classes that don't use them or are inactive because they don't have a skill. Class-based timers will not reactivate..but, skill-based ones will once a `CalcBotStats` call is made during the 'leveling' process. \(If the skill is not available after leveling, the timer will disable itself again.\)

Hopefully, this will help reduce bot cpu usage.

Please report any issues on our forums or in Discord - Thanks!

## 2/4/2020

#### hg

### **Auto Consent Implemented with Group / Raid / Guild Consent**

* Auto Consent client options are now supported. Toggling these options results in consenting \(or denying\) a player's current corpses.
  * These options are now also saved and restored for characters.
* The /consent and /deny commands for group, raid, and guild are now implemented. These commands are not case sensitive.
  * `/consent group` - adds current group id to all character corpses
  * `/consent raid` - adds current raid id to all character corpses
  * `/consent guild` - adds current guild id to all corpses and updates db
  * `/deny group|raid|guild` - sets the consent type id to 0 on all corpses
* Consent and deny commands are throttled to once every two seconds
* When consenting a player by name, both the corpse owner and the player being consented receive a message for every \(loaded\) zone a corpse is in.
* Corpses now store the list of consented player names. Previously clients stored a list of players they could drag corpses for.

Guild consent is persistent. The `character_corpses` table has a new `guild_consent_id`column which is updated when a player issues a guild consent command. This means guild consented corpses may be dragged by guild members after a corpse is loaded \(summoning the corpse to another zone or loading the corpse in a previously unloaded zone\)

Group and raid consent are not persistent. Corpses will lose these consents when a corpse is summoned or if the corpse is loaded by a zone after consent was issued.

## 1/15/2020

#### Uleat

### Update to EVENT\_COMMAND and EVENT\_BOT\_COMMAND

The handlers for EVENT\_COMMAND and EVENT\_BOT\_COMMAND have been updated to allow a 'no change' behavior.

Script files using these event types will perform as before without the need to move the command scripting into them .. so long as there is no defined function for them.

Once a definition is given, the old method of using EVENT\_SAY to handle them will no longer work and the new formatting must be applied.

If you have any questions, please direct them to our forums or the `#support-quest-scripts` channel in discord.

## 1/10/2020

**Akkadius**

### Character Soft Deletes

Unless new system rule **Character:SoftDeletes** \(default: true\) is disabled, characters will now no longer hard delete from all respective character tables and will only be marked as deleted via the newly created `deleted_at` column that can be found in the `character_data` table. This can make it far easier to recover accidentally deleted characters

![](../.gitbook/assets/image%20%281%29.png)

## 1/7/2020

#### Uleat

### EVENT\_COMMAND and EVENT\_BOT\_COMMAND

* EVENT\_COMMAND now processes its own code and is no longer shared with EVENT\_SAY
* EVENT\_BOT\_COMMAND was added..but, will have limited functionality until more of the Bot class is exposed in the scripting apis
* Both event types have new or updated entries on the [Events](https://eqemu.gitbook.io/quest-api/methods/events/) page
* In the template scripts, just replace the example command data with your own
* Perl: `"command_name" => [<status_required>, "command_description"]`
* Lua: `["command_name"] = {<status_required>, "command_description"}`
* Anything in the `command_data` hash will be automatically parsed upon any `#help` call - to include partial matching criteria
* The same is true for `bot_command_data`
* These templates are not required for use..but, do provide a basic 'use' structure so that command coding is simplified and easier to implement
* Older 'say' command code may still work as-is..though, it has not been tested







