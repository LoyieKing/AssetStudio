# Changelog

## v0.17.2.0 [27-08-2023]
- [GUI] Improved Scene Hierarchy tab
   - Added "Related assets" item to the context menu (https://github.com/aelurum/AssetStudio/issues/7)
- [GUI] Added app.manifest for net472 build 
   - Added long paths support (win10 v1607+)
   - Fixed blurring at high DPI with scaling
- [CLI] Fixed sprite export in sprite only mode
- Made some changes to motion list for live2d models
   - Motion list is now sorted
   - Motions divided into groups (each motion is a separate group)
   - Motion names are used as group names
- Updated dependencies
- Made some other minor fixes and improvements

## v0.17.1.0 [12-07-2023]
#### Breaking Changes
- With the drag&drop fix (https://github.com/aelurum/AssetStudio/commit/2f8f57c1a63893c0b0d2a55349d6cb6d8f8a5a3b), functions `LoadFiles` and `LoadFolder` in AssetsManager have been replaced with one universal function `LoadFilesAndFolders`

#### Changes
- Fixed Texture2DDecoderNative compatibility issue with Linux/macOS (CLI preparation #1)
- Changed image library to ImageSharp (CLI preparation #2)
- Added support for sprites with alpha mask
   - Sprites with alpha mask can now be viewed and exported with transparency
   - Added hotkeys to control display of an alpha mask on the preview tab
   - Added an option to the export settings to enable/disable export with alpha mask as well
   - Prevented texture2D preview options from being changed with hotkeys outside of texture preview (e.g. when some other asset is selected)
- Added image export in WebP format
- Updated FMOD to 0.2.0.22 (CLI preparation #3)
- Added progress info about zip(apk) file loading process
- Added CLI version
- [GUI] Added context menu with "Select all", "Clear selection", "Expand all" and "Collapse all" options to the "Scene Hierarchy" tab
   - Selected objects count is now displayed in the status bar
- [GUI] Improved error handling
- [CLI] Added support for partial assets reading
- [GUI] Added some videoClip info to preview tab
- [GUI] Improved memory usage of image previews
- Disabled Shader support for Unity > 2020
- Added error message for bundles with UnityCN encryption
- Added error message on incorrect format of specified Unity version
- Block alignment fix for Unity 2019.4.X (source: https://github.com/K0lb3/UnityPy/commit/10346b4f02f2dbe0fa707799130c9f83c24f8e24)
- [GUI] Added "About" window
- Fixed cutout glitch in some packed sprites (https://github.com/Perfare/AssetStudio/issues/1015)
- Optimized drawing performance of packed sprites
- [GUI] Improved asset list filtering 
   - Added filter history
   - Added more filtering modes: Include, Exclude, Regex (Name/Container)
- Added grouping option with full container path (https://github.com/Perfare/AssetStudio/issues/815)
   - [GUI] - "container path full (with name)"
   - [CLI] - "containerFull"
- Improved "Restore TextAsset extension name" option 
   - If checked, AssetStudio will first try to find an extension in an asset's name and only then in its container. If no extension is found, ".txt" will be used
- [GUI] Fixed audio player position in maximized window
- [GUI] Improved file and folder loading (drag&drop) 
   - Added support for drag&drop of multiple folders
   - Open/Export dialog can now also use a path taken from drag&drop items
- [GUI] Added showing of progress bar in the taskbar button
- Added option to export Live2D Cubism 3 models

## v0.16.8.1 [25-11-2021]
- Uses System.Drawing lib instead of ImageSharp for process textures
- Added alphanumeric sorting to the column with asset names for more natural presentation of asset list
- Improved "Copy text" option in right click menu, to display what exactly to copy
- Added "Dump selected assets" option to right click menu
- Added 'selected assets count' info to status strip when you select assets
- Added 'exported count / total export count' info to status strip during export
- "Show error message" option on the "Debug" tab has been renamed to "Show all error messages" and is now disabled by default
- "Fixed" an issue with getting stuck during the "Building tree structure" step
- Fixed a bug with listSearch that could make it not work in some conditions
- Fixed a rare bug for resource files with the same name, that caused their data to be overwritten and become incorrect
