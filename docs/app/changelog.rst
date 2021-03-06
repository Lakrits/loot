***************
Version History
***************

Only application history is recorded here. A full history of masterlist changes may be viewed by browsing the GitHub repositories.

0.10.0 - Unreleased
===================

Changed
-------

- LOOT now supports v0.10 of the metadata syntax. This breaks compatibility with existing syntax, which may cause existing user metadata to fail to load. See :doc:`the syntax version history <../metadata/changelog>` for the details.
- The Global Priority toggle button in the metadata editor has been replaced with an input field to reflect the change in syntax for global priorities.
- Added a "Clean Plugin Info" tab to the metadata editor, for editing metadata that identifies a plugin as being clean.
- Added a "Verified clean" icon to plugin cards that is displayed for plugins that are identified as clean.
- All operations triggered from the UI are now processed asynchronously, which may have a minor positive effect on perceived performance.
- Updated Simplified Chinese translation.
- Updated CEF to 3.2785.1466.g80e473e.

Removed
-------

- The metadata syntax documentation from build installers and archives: it is now hosted online at `Read The Docs`_.

.. _Read The Docs: https://loot.readthedocs.io/

Fixed
-----

- Cached plugin CRCs causing checksum conditions to always evaluate to false.
- Data being loaded twice when launching LOOT.
- Updating the masterlist when the user's ``TEMP`` and ``TMP`` environmental variables point to a different drive than the one LOOT is installed on.

0.9.2 - 2016-08-03
==================

Added
-----

- Theming support and the dark theme have been reimplemented and reintroduced.
- Plugin filename and Bash Tag name fields will now autocomplete in the metadata editor.
- The in-game load order indices of active plugins are now displayed in the sidebar.

Changed
-------

- Most URLs now use HTTPS.
- The Danish and French translations have been updated.
- The CEF (3.2743.1442.ge29124d), libespm (2.5.5), Polymer (1.6.0) and Pseudosem (1.1.0) dependencies have been updated to the versions given in brackets.

Fixed
-----

- Error when applying filters on startup.
- Hidden plugin and message counters not updating correctly after sorting.
- An error occurring when the user's temporary files directory didn't exist and updating the masterlist tried to create a directory there.
- The installer failing if LOOT was previously installed on a drive that no longer exists. The installer now always gives the option to change the default install path it selects.
- Startup errors being reported incorrectly and causing additional errors that prevented the user from being informed of the original issue.
- The metadata editor's CRC input field being too short to fully display its validation error message.
- Errors when reading some Oblivion plugins during sorting, including the official DLC.
- Some cases where LOOT would fail to start.
- The conflict filter not including the Unofficial Skyrim Legendary Edition Patch's plugin (and any other plugin that overrides a very large number of records) in results.
- The "not sorted" message reappearing if the load order was sorted twice in one session and cancelled the second time.
- Version numbers where a digit was immediately followed by a letter not being detected.

0.9.1 - 2016-06-23
==================

Added
-----

- Support for Fallout 4's Contraptions Workshop DLC, and the upcoming Vault-Tec Workshop and Nuka-World DLC. Support for the latter two is based on their probable but unconfirmed plugin names, which may be subject to change.

Changed
-------

- The content refresh menu item is now disabled during sorting.
- The conflicts filter toggle buttons have been removed from the plugin card menus, and the filter re-implemented as a dropdown menu of plugin names in the Filters sidebar tab.
- Enabling the conflicts filter now scrolls to the target plugin, which is no longer highlighted with a blue border.
- The layout of the Filters sidebar tab has been improved.
- The CEF (3.2704.1427.g95055fe), and libloadorder (9.4.0) dependencies have been updated to the versions given in brackets.
- Some code has been refactored to improve its quality.

Removed
-------

- Support for Windows Vista.

Fixed
-----

- User dirty metadata being read-only in the metadata editor.
- LOOT incorrectly reading a tag with no name from plugin descriptions containing ``{{BASH:}}``.

0.9.0 - 2016-05-21
==================

Added
-----

- Support for Fallout 4.
- A warning message is displayed in the General Information card if the user has not sorted their load order in the current LOOT session.
- An error message is displayed in the General Information card when a cyclic interaction sorting error is encountered, and remains there until sorting is next attempted.

Changed
-------

- Improve sorting performance by only reading the header when loading game's main master file.
- References to "BSAs" have been replaced with the more generic "Archives" as Fallout 4's BSA equivalents use a different file extension.
- The sorting process now recognises when the sorted load order is identical to the existing load order and informs the user, avoiding unnecessary filesystem interaction.
- The metadata editor has been reimplemented as a single resizeable panel displayed below the plugin card list instead of a separate editor for each plugin card.
- Editable table styling has been improved to more closely align to the Material Design guidelines.
- Minor UI changes have been made to scrollbar and focus outline styling to improve accessibility.
- UI interaction performance has been improved, especially when scrolling the plugin card list.
- The PayPal donation link now points to the PayPal.Me service, which has a more polished UX and lower fees.
- LOOT's settings file handling has been reimplemented, fixing crashes due to invalid settings values and allowing missing settings to use their default values.
- Plugin version string extraction has been reimplemented, improving its accuracy and maintainability.
- Plugin CRC, file and version condition evaluation has been optimised to use cached data where it exists, avoiding unnecessary filesystem interaction.
- The French and Danish translations have been updated.
- The installer now only creates one shortcut for LOOT in the Start menu, following Microsoft guidelines.
- A lot of code has been refactored and improved to increase its quality.
- The Boost (1.60), CEF (3.2623.1401.gb90a3be), libespm (2.5.2), libgit2 (0.24.1), libloadorder (9.3.0) and Polymer (1.4) dependencies have been updated to the versions given in brackets.

Removed
-------

- The Flattr donation link.
- The experimental theming support, as its implementation was incompatible with Polymer 1.2's styling mechanisms.

Fixed
-----

- Redate Plugins attempted to redate plugins that were missing, causing an error.
- LOOT would not launch when run by a user with a non-ASCII local application data path.
- Sorting processed priority value inheritance throughout the load order incorrectly, leading to some plugins being positioned incorrectly.
- The conflict filter displayed only the target plugin when enabled for the first time in a session.
- The behaviour of the search functionality was inconsistent.
- Duplicate messages could be displayed under certain circumstances.
- Opening the metadata editor for one plugin displayed the metadata for another plugin under certain circumstances.
- Changing the current game quickly could leave the UI unresponsive.
- Applying a filter then scrolling the plugin card list would display some cards with no content.
- Plugin cards would disappearing when jumping to a plugin card near the bottom of the load order using the sidebar.
- Clicking on a disabled element in a dropdown menu would cause the menu to close.
- The UI font size was too large, due to a misunderstanding of the Material Design guidelines.
- Attempting to build native Linux and 64-bit executables produced errors. Such builds are unsupported and no official builds are planned.

0.8.1 - 2015-09-27
==================

Added
-----

- Checks for safe file paths when parsing conditions.

Changed
-------

- Updated Chinese translation.
- Updated Boost (1.59.0), libgit2 (0.23.2) and CEF (branch 2454) dependencies.

Fixed
-----

- Crash when loading plugins due to lack of thread safety.
- The masterlist updater and validator not checking for valid condition and regex syntax.
- The masterlist updater not working correctly for Windows Vista users.

0.8.0 - 2015-07-22
==================

Added
-----

- Support for loading custom user interface themes, and added a dark theme.

Changed
-------

- Improved detail of metadata syntax error messages.
- Improved plugin loading performance for computers with weaker multithreading capabilities (eg. non-hyperthreaded dual-core or single-core CPUs).
- LOOT no longer displays validity warnings for inactive plugins.
- LOOT now displays a more user-friendly error when a syntax error is encountered in an updated masterlist.
- Metadata syntax support changes, see the metadata syntax document for details.
- LOOT's installer now uses Inno Setup instead of NSIS.
- LOOT's installer now uninstalls previous versions of LOOT silently, preserving user data, instead of displaying the uninstaller UI.
- Updated German and Russian translations.
- Updated libgit2 to v0.23.0.

Fixed
-----

- "Cannot read property 'push' of undefined" errors when sorting.
- Many miscellaneous bugs, including initialisation crashes and incorrect metadata input/output handling.
- Metadata editors not clearing unsaved edits when editing is cancelled.
- LOOT silently discarding some non-unique metadata: an error message will now be displayed when loading or attempting to apply such metadata.
- Userlist parsing errors being saved as general messages in the userlist.
- LOOT's version comparison behaviour for a wide variety of version string formats. This involved removing LOOT's usage of the Alphanum code library.

0.7.1 - 2015-06-22
==================

Added
-----

- Content search, accessible from an icon button in the header bar, and using the Ctrl-F keyboard shortcut.
- "Copy Load Order" feature to main menu.

Changed
-------

- LOOT now uses versioned masterlists, so that new features can be used without breaking LOOT for users who haven't yet updated.
- Moved content filter into Filters sidebar tab. The Ctrl-F keyboard shortcut no longer focusses the content filter.
- Checkbox-toggled filters now have their last state restored on launch.
- Darkened background behind cards to increase contrast.
- Updated French translation.

Fixed
-----

- LOOT UI opening in default browser on launch.
- "No existing load order position" errors when sorting.
- Message filters being ignored by plugin cards after navigating the list.
- Output of Bash Tag removal suggestions in userlists.
- Display of masterlist revisions where they were wrongly interpreted as numbers.

0.7.0 - 2015-05-20
==================

Added
-----

- Danish and Korean translations.
- If LOOT can't detect any installed games, it now launches to the settings dialog, where the game settings can be edited to allow a game to be detected.
- A "Copy Content" item in the main menu, to copy the plugin list and all information it contains to the clipboard as YAML-formatted text.
- A "Refresh Content" item in the main menu, which re-scans plugin headers and updates LOOT's content.
- LOOT is now built with High DPI display support.
- Masterlist updates can now be performed independently of sorting.
- A "First-Time Tips" dialog will be displayed on the first run of any particular version of LOOT.
- Attempting to close LOOT with an unapplied sorted load order or an open plugin editor will trigger a confirmation dialog.
- Support for GitHub Flavored Markdown in messages, minus features specific to the GitHub site, such as @mentions and emoji.
- Support for message content substitution metadata syntax in the masterlist.
- Display of LOOT's build revision has been added to the "About" dialog.
- Plugin location metadata can now be added through the user interface.
- A content filter, which hides plugins that don't have the filter text present in their filenames, versions, CRCs, Bash Tags or messages.

Changed
-------

- New single-window HTML5-based interface and a new icon, based on Google's Material Design.

  - LOOT now parses the masterlist and plugin headers on startup, and the resulting content is displayed with the plugins in their current load order.
  - Each plugin now has its own editor, and multiple editors can be opened at once.
  - Drag 'n' drop of plugins from the sidebar into metadata editor tables no longer requires the conflicts filter to be enabled.
  - CRCs are calculated during conflict filtering or sorting, so are notdisplayed until either process has been performed.
  - The "View Debug Log" menu item has been replaced with a "Open Debug Log Location" menu item to make it easier to share the file itself.
  - Debug logging control has been simplified to enable/disable, replacing the "Debug Verbosity" setting with an "Enable Debug Logging" toggle.
  - Changes to game settings now take immediate effect.
  - Masterlist updating now exits earlier if the masterlist is already up-to-date.
  - Masterlist revisions are now displayed using the shortest unique substring that is at least 7 characters long.
  - Making edits to plugin metadata before applying a calculated load order no longer causes LOOT to recalculate the load order. Instead, the displayed load order is applied, and the metadata edits will be applied the next time sorting is performed.
  - All references to "UDRs" have been replaced by the more technically-correct "Deleted References" term.
  - The "Hide inactive plugin messages" filter has been replaced by a "Hide inactive plugins" filter.
  - Copied metadata is now wrapped in BBCode ``[spoiler][code]...[/code][/spoiler]`` tags for easier pasting into forum posts.
  - The Summary and General Messages cards have been combined into a General Information card.

- Sorting performance improvements.
- Updated Boost (1.58.0), libgit2 (0.22.2) and libloadorder dependencies.

Removed
-------

- Messages with multiple language strings can no longer be created through the user interface. User-added multiple-language messages will be converted to single-language strings if their plugin's editor is opened then closed using the "OK" button.
- The "Copy Name" menu item has been removed, as plugin names can now be selected and copied using ``Ctrl-C``.
- As LOOT no longer generates reports, it doesn't save them either.

Fixed
-----

- The ``settings.yaml`` included with the installer was very old.
- Inactive incompatibilities were displayed as error messages. They are now displayed as warnings.
- Masterlist entries that matched the same plugin were not being merged. Now one exact match and any number of regex matches will be merged.
- Masterlist updating failed when a fast-forward merge was not possible (eg. when remote has been rebased, or a different repository is used). Such cases are now handled by deleting the local repository and re-cloning the remote.
- Masterlist updating failed when the path to LOOT's folder included a junction link.
- Masterlists would not 'update' to older revisions. This can be useful for testing, so now they can do so.
- Crashes when trying to read corrupt plugins and after masterlist update completion.
- LOOT would crash when trying to detect a game installed to a location in which the user does not have read permissions, now such games are treated as not being installed.
- Plugins with non-ASCII description text would cause ``codecvt to wstring`` errors.
- LOOT would accept any file with a ``.esp`` or ``.esm`` extension as a plugin. It now checks more thoroughly, by attempting to parse such files' headers.
- LOOT would only detect Skyrim plugins as loading BSAs. Plugins for the other games that also load BSAs are now correctly detected as such.
- Depending on the plugins involved, sorting could produce a different load order every time it was run. Sorting now produces unchanging load orders, using existing load order position where there is no reason to move a plugin.

0.6.1 - 2014-12-22
==================

Added
-----
- German translation.
- The Large Address Aware flag to the LOOT executable.

Changed
-------
- Updated Boost (1.57.0), wxWidgets (3.0.2) and libloadorder (6.0.3) dependencies.
- The game menu is now updated when the settings window is exited with the "OK" button.
- Updated Russian translation.
- Updated Brazilian Portuguese translation.

Fixed
-----

- Default Nehrim registry entry path.
- Messages in the wrong language being selected.
- LOOT windows opening off-screen if the screen area had been changed since last run.
- Read-only ``.git`` folders preventing repository deletion.
- Unnecessary plugins in cyclic dependency error messages.
- Bash Tag suggestions displaying incorrectly.
- The current game can no longer be deleted from the settings window.
- Plugin metadata being lost when the settings window was exited with the "OK" button, leading to possible condition evaluation issues.
- A blank report bug when running on systems which don't have Internet Explorer 11 installed.
- Reports appearing empty of all content when no global messages are to be displayed.

Security
--------

- Updated libgit2 to 0.21.3, which includes a fix for a critical security vulnerability.


0.6.0 - 2014-07-05
==================

Added
---------

- Display of masterlist revision date in reports.
- Report filter for inactive plugin messages.
- The number of dirty plugins, active plugins and plugins in total to the report summary.
- A find dialog to the report viewer, initiated using the ``Ctrl-F`` keyboard shortcut.
- LOOT's windows now remember their last position and size.
- Command line parameter for selecting the game LOOT should run for.
- Finnish translation.

Changed
-------

- Unified and improved the metadata editors launched during and outside of sorting.

  - The metadata editor now resizes more appropriately.
  - The mid-sorting instance hides the requirement, incompatibility, Bash Tags, dirty info and message lists.
  - Both instances now have a conflict filter, priority display in their plugin list and drag 'n' drop from the plugin list into whatever metadata lists are visible.
  - The mid-sorting instance also hides the load after entry edit button, and the button to add new entries (so drag 'n' drop is the only available method of adding entries).
  - The metadata editor now displays plugins with user edits using a tick beside their name, rather than bolding their name text.
  - Plugins that have been edited in the current instance have their list entry text bolded.
  - Checkboxes have been added to set whether or not a priority value is "global". The UI also now displays the priority value used in comparisons (ie. with the millions and higher digits omitted).
  - A right-click menu command for clearing all user-added metadata for all plugins has been added to the metadata editor.

- Missing master/requirement and incompatibility errors are downgraded to warnings if the plugin in question is inactive.
- Masterlist update errors have been made more user-friendly.
- If an error is encountered during masterlist update, LOOT will now silently delete the repository folder and attempt the update again. If it fails again, it will then report an error.
- Masterlist update now handles repository interaction a lot more like Git itself does, so should be less error-prone.
- Cyclic dependency error messages now detail the full cycle.
- LOOT's report now uses a static HTML file and generates a javascript file that is dynamically loaded to contain the report data. This removes the PugiXML build dependency.
- Debug log message priorities adjusted so that medium verbosity includes more useful data.
- Updated dependencies: libgit2 (v0.21.0), wxWidgets (v3.0.1), libloadorder (latest), libespm (latest).

Removed
--------

- Support for Windows XP.
- Support for loading BOSS masterlists using the API. This was a leftover from when LOOT was BOSSv3 and backwards compatibility was an issue.
- The ability to open reports in an external browser. This was necessitated by the changes to report generation.
- The MSVC 2013 redistributable requirement.
- The "None Specified" language option is no longer available: English is the new default.

Fixed
-----

- The uninstaller not removing the Git repositories used to update the masterlists.
- Miscellaneous crashes due to uncaught exceptions.
- Plugin priorities are now temporarily "inherited" during sorting so that a plugin with a low priority that is made via metadata to load after a plugin with a high priority doesn't cause other plugins with lower priorities to be positioned incorrectly.
- The default language is now correctly set to English.
- Defaults for the online masterlist repository used for Nehrim.
- Endless sorting loop that occurred if some user metadata was disabled.

0.5.0 - 2014-03-31
==================

- Initial release.
