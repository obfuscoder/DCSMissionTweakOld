# DCSMissionTweaker

With this tool, you can convert any single player mission into a multiplayer mission.

The tool can be used with missions of copyprotected DLC campaigns as well.
The copy protection is not circumvented with this tool.
All clients/players are still required to have a purchased license of that DLC campaign.

*Attention:*

Quite a few missions use SPACE BAR triggers in order to advance the mission progress.
Due to this reason, one of the players/clients must also host the mission.
This hosting player is able to hit the SPACE BAR.

A few missions also use conditions/triggers based on specific cockpit dials or switches.
Again, those conditions/triggers will only work for the hosting player.

Usage:

```
dcsmissiontweak.exe <path_to_missionfile.miz> <numberofclients>
```

This will change the units of the group the single player is part of to clients.
Only the first <numberofclients> units will be converted to clients.
The tool does not yet increase the number of existing units within the group.
If the group has fewer units than the specified <numberofclients>, only the existing units of that group are converted to clients.

Planned improvements:

1. Changing airframe

This will allow flying missions with other aircraft.
This will only work if the mission does not rely on aircraft specific cockpit triggers/conditions of course.
As long as the new airframe has about the same capabilities as the original airframe the clients shouldn't have too much issues.
The first iteration of this feature will not add any loadout on the new airframe. The clients need to add the loadout themselves.
Additional iterations of that feature will attempt to convert the loadout from the original airframe to the new one.

2. Increasing number of units

If the number of clients is higher than the number of already existing units of the group, additional units (up to 4) will be added to the group.

3. Additional groups (with different airframe)

It will be possible to just add additional groups to the mission. The tool will attempt to be as smart as possible to add those units/groups.
Based on the starting configuration for the original units, the additional units will be configured and placed.
a few options will be provided to give the user some choice.

4. GUI

For the users who like a nice GUI, there will be one.

## Contributions

Feel free to contribute to this tool. Add issues if you find any bugs and or create pull requests for enhancements/fixes.
