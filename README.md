# Darktide Mod Settings Merger

A simple browser-based tool for exporting and importing selected Warhammer 40,000: Darktide mod settings.

The tool reads the `mods_settings` section from Darktide's `user_settings.config` file and lets you choose which individual mod settings to export or merge. This makes it easier to share mod configurations without overwriting another player's unrelated game settings such as graphics, keybinds, audio, or other personal preferences.

## Open the tool

[Open Darktide Mod Settings Merger](https://artmos.github.io/darktide-mod-settings-merger)

## What it does

* Exports selected mod settings from `mods_settings`
* Imports selected mod settings into an existing `user_settings.config`
* Replaces settings only for mods you select
* Adds selected mods if they do not already exist in the target file
* Leaves all other user settings untouched
* Runs entirely in your browser
* Does not upload files anywhere

## What it does not do

* It does not edit your Darktide settings file automatically
* It does not merge graphics, audio, keybinds, or other game settings
* It does not merge `mod_manager_settings`
* It does not require PowerShell, Python, or any external program

## How to use

### Export mod settings

1. Open the tool.
2. Select your current `user_settings.config`.
3. The tool will list all detected mods inside `mods_settings`.
4. Select the mods you want to export.
5. Click **Export selected mods**.
6. Download the generated `darktide_mod_settings.config` file and share it.

### Import / merge mod settings

1. Open the tool.
2. Select your current `user_settings.config`.
3. Select or paste a shared `darktide_mod_settings.config` file.
4. The tool will list all shared mods.
5. Select the mods you want to import.
6. Click **Create merged config**.
7. Download the generated `user_settings.config`.
8. Back up your original file, then replace it with the merged file.

## Darktide settings file location

For the Steam version, the file is usually located at:

```txt
%AppData%\Fatshark\Darktide\user_settings.config
```

For the Microsoft Store / Game Pass version, the file is usually located at:

```txt
%AppData%\Fatshark\MicrosoftStore\Darktide\user_settings.config
```

## Safety notes

Close Darktide before replacing `user_settings.config`.

Always make a backup of your original file before replacing it. The tool is designed to preserve unrelated settings, but keeping a backup is still recommended.

## Shared file format

The exported file contains only selected entries from the `mods_settings` section.

Example:

```txt
mods_settings = {
    "A la Mode" = {
        alm_open_setup = false
    }
}
```

The import tool can also accept loose mod entries without the surrounding `mods_settings` block:

```txt
"A la Mode" = {
    alm_open_setup = false
}
```

## License

This project is licensed under the MIT License. You are free to fork, modify, and redistribute it.
