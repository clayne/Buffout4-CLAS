=====================================================================================================
# CLASSIC CHANGELOG #

7.30.3
*CHANGES*
- Now queries the registry for the game's install directory first before falling back to parsing the F4SE log
- Add the ability to toggle the audio notifications, also now uses Qt's built-in sound effect library so we no longer need to bundle NumPy (which was a dependency of the old audio library)
- Logs copied from F4SE directory now go into a new "Crash Logs" folder (which is automatically created if it doesn't exist). Existing logs in the main CLASSIC directory will be moved to this folder.
- No longer automatically checks for latest F4SE version since it is obsolete because F4SE is now doing new releases on Nexus.

7.30.2
*CHANGES*
- Game installation directory is now properly saved to the local data file.
- Removed the FormID database creation code and opted for bundling a premade database
There is also a second database for you to add your own mods form ids to, just add the bundled xEdit script in CLASSIC Data to create the list and use the included tools to add them.


7.30.1
*CHANGES*
- Prompts for INI directory and Game directory will be handled in the GUI
- Fixed typos that prevented the detection of X-Cell in FCX mode.

*KNOWN ISSUES*
The Papyrus log monitor is still a WIP

7.30 (Formerly known as 7.26.1 Unofficial)
*CHANGE SUMMARY*
- CLASSIC now uses a database cache, generated on startup, to improve query speed for the "Show FID Values" feature.
- Fixes the NoneType error, which was caused by the initialization code failing to store the location of the F4SE Address Library.
- FCX mode no longer crashes when duplicate section entries are found in an INI file or a section it's looking for doesn't exist.
- Fix FCX mode for Fallout 4 VR. Turns out F4SEVR also uses the F4SE directory and not a separate F4SEVR directory in the "My Games" folder.
- Add caching code for YAML file lookups to minimize the number of times a file actually needs to be read.
- Add conflict and configuration checks for perchik71's X-Cell mod.
- Bump BA2 Limit check's severity to 6 because any other crash suspects are likely the result of the BA2 limit crash.
- Reclassified loose previsibine files as a *CAUTION* instead of a *NOTICE* since current conensus is that loose previsibine files are problematic.
- Add separate core mod list for Fallout: London (Right now, it's pretty much the same as the vanilla one, just removes UFO4P and PRP since they are incompatible with FOLON)
- Brand new UI made with the goal of making the window no longer confined to "650x950". It's still not resizable, but the groundwork is laid to make it scale better for larger resolutions.
This new UI also no longer pops up a console window, all console output is now printed in a text box in the main window.
- Custom crash handler that has a button to instantly copy the traceback message to the clipboard.
- Scans now run off the main thread so the window no longer freezes while scans are running.
- Update the current Buffout 4 NG version to 1.35.1.
- Fix plugin tests running when no plugin list was loaded.
- More fixes and optimizations that didn't make the changelogs of the past.

7.26.1 Unofficial
*BUG FIXES*
- Papyrus Monitor no longer launches a new instance of CLASSIC.
- Fixed formatting errors in Papyrus Monitor that were hidden by the old display method.
- Revert the initialization threading changes from the previous versions hotfixes.

7.26 Unofficial
*NEW UI*
- Scans run off the main thread, so the window no longer freezes when scans are running.
- Terminal is now embedded into the window, in the text box formerly reserved for the credits.
- Credits have been moved to an about screen, the button for it is next to the help button.
I think it looks better like that, anyways.
- No more custom widgets, which will make maintainance and feature development easier.
- Crash dialog with a button to easily copy the traceback to the clipboard.

*WHAT'S NOT PORTED YET*
- The background image, still working on how to integrate it.
- The game selection box, until there are other games to switch to (Skyrim support is coming someday), there's no point for it to be there.

7.25.12 Unofficial
*CHANGES*
- Add encoding detection to INI file checks to prevent issues with some non-latin encodings
- Update Check will now display in the window instead of the terminal.
- Minor consistency changes
- Bump BA2 Limit check to severity 6 because other suspects might actually be triggered by the BA2 limit.
- Minor backend optimizations
- Fixed plugin detection for FONG logs.

7.25.11 Unofficial
*CHANGES*
- Add separate core mod list for Fallout: London

7.25.10 Unofficial
*CHANGES*
- Add Buffout 4 configuration fixes to FCX mode.
- Added conflict between X-Cell and PrivateProfileRedirector (from 7.25.9-hotfix2)

7.25.9 Unofficial
*CHANGES*
- Add conflict and configuration checks for perchik71's X-Cell mod.

7.25.8 Unofficial
*CHANGES*
- Check the registry instead of shell32.dll for the location of the "Documents" directory
- Add a cache to the YAML lookup code to improve performance (hopefully)
- Reclassified loose previsibine files as a *CAUTION* instead of a *NOTICE* since current conensus is that loose previsibine files are problematic.
- Fix log stat counting.
- Change latest Buffout 4 NG version to 1.35.1

7.25.7 Unofficial
*CHANGES*
- Further improve exception handling when parsing INI files with FCX mode or Scan Game Files.

7.25.6 Unofficial
*CHANGES*
- Fix plugin tests not running when loadorder.txt was used instead of a log's plugin section.

7.25.5 Unofficial
*CHANGES*
- Fix plugin tests running when there was no plugin list loaded.

7.25.4 Unofficial
*CHANGES*
- Make reading text files more resilient
- Add message informing about the possibility of "False Negatives" with the core mods.

7.25.3 Unofficial
*CHANGES*
- Changed location FCX mode looks for F4SEVR's log to {docs_directory}\\F4SE\\f4sevr.log

7.25.2 Unofficial
*CHANGES*
- Fix `KeyError`s occurring when scanning mod INI files and the section being searched for doesn't exist.
- Possible fix for FCX mode not finding Address Library in situations where it should be able to.

7.25.1 Unofficial
*CHANGES*
- Unofficial Series Only: Redirect update queries to my GitHub page.

7.25 Unofficial
*NEW FEATURES*
- CLASSIC will now generate a cache of the Form-IDs list for faster searching.
- Added tools to add new form-ids or update existing form-ids in the cache.

*CHANGES*
- Fix Address Library path not being saved in the local data file.
- Only match the first GPU in the log to avoid issues with systems with an AMD CPU and Nvidia GPU.
- Finding duplicate entries in game INI files will no longer cause CLASSIC to crash.

*DISCLAIMER*
This is just a reflection of my copy of the code and may or may not make it into the final build.

7.20
*NEW FEATURES*
- CLASSIC now automatically creates backups of your game's main EXE files.
- CLASSIC now automatically checks for F4SE updates from the official website.
- Added hash checks for Script Extender files from the VR version of the game.
- Added the Address Library file check (required for Script Extender and some mods).
- CLASSIC now checks if given folder for the INI path actually exists before adding it.
- Added options to Backup / Restore / Remove files from *ENB, Reshade and Vulkan Renderer*
[These options are located under the new tab in the CLASSIC interface. See Readme PDF for details].
- All invalid crash logs and file backups are now stored and separated into *CLASSIC Backup* folder.

*CHANGES*
- *Crash Logs Scan* is now ~25% faster.
- Improved visuals of interface popup boxes.
- Re-centered a few misaligned interface elements.
- Updated BethINI link to the new BethINI PIE version.
- Additional fixes for Fallout 4 VR file and folder paths detection.
- Converted CLASSIC Readme to PDF with better formatting and more info.
- Fixed crash log files not being excluded from general log files error search.
- Fixed incorrect detection of Script Extender file copies during *Game Files Scan*.
- Fixed an issue where certain plugins were not detected under *Possible Plugin Suspects*.

7.10
*NEW FEATURES*
- CLASSIC will now extract required files from *CLASSIC Data.zip* if they are not found.
- Default *Fallout4Custom.ini* settings are now accessible through *CLASSIC FO4.yaml*
[These settings will be auto generated if Fallout4Custom.ini doesn't already exist.]

*CHANGES*
- The CLASSIC interface has a brand new look.
- Fixed *AttributeError* in the mod_ini_config().
- Fixed some minor formatting bugs for *-AUTOSCAN.md* files.
- Fixed incorrect generation of Fallout 4 VR file and folder paths.
- Updated *CLASSIC Readme* with explanations for all of the new features.
- CLASSIC now keeps AUTOSCAN report files in the same folder with their crash logs.
- Changed the file structure, now all required files are organized inside *CLASSIC Data* folder.
[Please report if it still fails to generate your Fallout 4 VR file and folder paths in CLASSIC FO4VR.yaml]

7.07 | "Everything Everywhere All At Once" Update
*NEW FEATURES*
- CLASSIC will automatically check for its own updates every 7 days.
- CLASSIC will warn you if MS OneDrive is overriding your Documents folder location.
- CLASSIC will automatically grab all crash log files from the Script Extender folder.
- CLASSIC will play a short notification sound once crash logs and game file scans are done.
- Various CLASSIC settings were moved to YAML files for much easier access and editing.
- Various CLASSIC functions and tasks are now automatically logged to *CLASSIC Journal.log*
- Extended scan support for crash logs from new and old Buffout 4 versions.
- Extended compatibility and features for Virtual Reality (VR) version of the game.
- *VR Mode* setting that will prioritize scanning files from the VR version of the game.
- *Simplify Logs* setting that removes some useless and redundant lines from crash log files.
- *Show FID Values* setting that will look up FormID values for Possible FormID Suspects.
- Papyrus Log monitoring built into the GUI. Also plays a warning sound when things go bad.
- Buttons for quick access to the DDS Texture Scanner, Wrye Bash and BethINI Nexus pages.
- Ability to scan all mod files from your Staging Mods Folder to detect these issues:
	> Check if DDS texture file dimensons are not divisible by 2 (Ex. 1024 x 1025)
	> Check if texture files are in the wrong format (TGA or PNG instead of DDS)
	> Check if sound files are in the wrong format (MP3 or M4A instead of XWM or WAV)
	> Check which mods have custom precombine / previs data (so you can load them after PRP)
	> Check which mods have custom animation file data (to narrow down Animation Data Crashes)
	> Check which mods have copies of Script Extender files (to prevent problems and crashes)
- Mod files scan will also move any found fomod and readme files to the CLASSIC Misc folder.
- You can also generate FormID values for all active mods, so AUTOSCAN reports can use them.
- AUTOSCAN reports will now additionally provide the following information:
	> List all mod INI files and settings that have enabled game *VSync*, if any.
	> Show how many times each Possible FormID Suspect appears in the crash log.
	> Warn you if *Fallout4.ini, Fallout4Prefs.ini or Fallout4Custom.ini* become corrupted.
	> Notify you when Buffout 4 fixes in the TOML config file get changed or disabled.
	> Show an additional warning if you went over the Plugin Limit (254 esm/esp).

*CHANGES*
- Complete code rewrite that will make all future versions much more stable and expandable.
- *Game Corruption Crash* renamed to *Animation Data Crash*, crash info has been updated.
- Several code optimizations thanks to [evildarkarchon] on GitHub, plus many bugs squashed.
- Added few redundant / irrelevant errors to the internal exclusion list so they are ignored.