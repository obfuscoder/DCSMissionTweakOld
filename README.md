# DCSMissionTweaker

With this tool, you can convert any single player mission into a multiplayer mission.

The tool can be used with missions of copyprotected DLC campaigns as well.
The copy protection is not circumvented with this tool.
All clients/players are still required to have a purchased license of that DLC campaign.

## Download

Either compile the source code with Visual Studio or download a precompiled executable here:

https://drive.google.com/open?id=1pqKflZaAkdw_mAOhSlpCsKup3NyI4ld9

SHA1: 84081c37f52b371e1aa72c8bad817c699aac50d9

SHA256: 8051d4d1d67768a804bfe1444b1341eaf260e2cd100e35dd1e7de399b75e2873

The compiled executable is not signed. Windows will warn you when you try to execute it. You need to "accept the risk".

## Disclaimer

This tool DOES NOT circumvent any DCS copy protection. If you tweak a mission of a copyprotected DLC campaign, all joining clients are still required to have the original DLC campaign installed. Otherwise they won't be able to join.

As this tool does not circumvent the copyprotection, Eagle Dynamics is ok with it. I have permission from them to publish it. If you want to know, how it works, see blow.

## Limitations

Quite a few missions use SPACE BAR triggers in order to advance the mission progress.
Due to this reason, one of the players/clients must also host the mission.
This hosting player is able to hit the SPACE BAR.

A few missions also use conditions/triggers based on specific cockpit dials or switches.
Again, those conditions/triggers will only work for the hosting player.

## Usage

```
dcsmissiontweak.exe <path_to_missionfile.miz> <numberofclients>
```

This will change the units of the group the single player is part of to clients.
Only the first <numberofclients> units will be converted to clients.
The tool does not yet increase the number of existing units within the group.
If the group has fewer units than the specified <numberofclients>, only the existing units of that group are converted to clients.

## Requirements

This tool runs on Windows with Microsoft .Net Framework 4.5 or higher installed.

## Planned improvements

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

## How does it work?

Essentially, miz-files are just zip archives. The file "mission" within the archive is a *lua* config file. This file contains all units. The tool simply parses this config file and updates those units. The method also works with copyprotected missions because only the triggers/conditions, scripts, behavior has been extracted into an encrypted file (extension .crypt) located side-by-side with the mission files. The miz file contains a reference to that file. This reference is not touched by the tool. The encryption mechanism does not include any checksums for the mission file itself or other content within the miz archive. This allows modifying it without breaking the copy protection. It also allows placing that miz file anywhere - even downloading from a DCS server). Upon loading that miz file, the referenced encrypted and protected file is being loaded as well. If that encrypted file cannot be located (e.g. client does not have a license of that DLC campaign or did not install it in his DCS version), that user is unable to join the mission.

## Contributions

Feel free to contribute to this tool. Add issues if you find any bugs and or create pull requests for enhancements/fixes.
