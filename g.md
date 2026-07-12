# --- Installing the operating system ---

## -- Creating a Live USB --
The process for creating a live Fedora USB is pretty simple compared to some other distros.<br>
Fedora Media Writer can be downloaded from (the Fedora GitHub page)[https://github.com/FedoraQt/MediaWriter/releases/latest]. This is a GUI tool that lets you pick a version of Fedora to download, and will write it to an **empty** USB drive.<br>
Make sure to select **Fedora KDE Plasma Desktop** instead of **Fedora Workstation** in the drop-down if you want a Windows-like experience (rather than the default macOS-like one).<br>
Once it is done, your USB drive can be used to reboot into Fedora.

## -- Booting from the USB drive --
If you don't already have an operating system installed (e.g. Windows on the SSD), I believe the computer should automatically boot into the live USB if its inserted due to this being the only available volume?<br>
If it doesn't, you can select it from the BIOS menu. The BIOS menu can be opened by holding the `Esc` key whilst the computer boots, and once it opens there should be a menu on the bottom right that allows you to select which device to boot into (in this instance the Fedora/USB device).<br>
This will enter you into a menu that says something similar to "Start Fedora 44" and "Test this media and start Fedora 44". These both do essentially the same thing, with one doing extra checks to make sure the USB is set up properly. I usually just pick "Start Fedora 44".

## -- Installing Fedora --
Once you're in the desktop environment, it should bring up a prompt to install Fedora to the computer.<br>
This is pretty simple so I'm sure you can figure this part out, you basically select your language, date/time, and then pick which drive to install to.<br>
Since you're building a new computer (with no files already on it) you can just tell it to erase the entire drive, and it should ask you to reboot once it is done.<br>

When it reboots, make sure to go through the little welcome guide it gives you, since one of the pages asks you if you would like enable third party repositories (which will make many more apps available from the built-in "discover" app store).


# --- Installing Apps ---
Below I've listed the apps that you were interested in installing, as well as what different types of apps there are:

## -- System commands --
These are commands that can be entered into the system terminal (on KDE Plasma this is Konsole) to install apps.
You probably won't need to use these (all apps will appear in Discover) but in the case that you do:<br>
`sudo dnf install firefox gnome-disks`

`sudo` = admin (will ask for password)<br>
`dnf install` = package manager, install<br>
`firefox gnome-disks` = example of apps to install

These are the apps that I would like you to install using this method:
- Dotnet Runtime 8.0: `dotnet-runtime-8.0`
  - Used for running Track Studio
- Steam: `steam`
  - Steam's flatpak can have issues with recognising controllers/accessing files, so I like to install the official one
- Wine: `wine` and `winetricks`
  - Used for opening and configuring Windows applications respectively


## -- Apps from Flathub Store --
These will also appear in the Discover app

Spotify<br>
Discord (or Vesktop if you want themes/plugins)<br>
Prism Launcher<br>
Krita<br>
Audacity<br>
Ryujinx<br>
Dolphin Emulator<br>
Inkscape<br>
OBS Studio<br>
VLC<br>


## -- Apps from elsewhere (e.g. GitHub) --
These won't show up in the app launcher so I'd create a shortcut for them (see below)<br>
Standalone apps can come in multiple formats:

### - AppImage -
These are single files that contain all of the app's data, rather than coming as a .zip file.<br>
They end with a `.appimage` extension and can be double-clicked to run.

- [khinsiderdownloader](https://github.com/weespin/KhinsiderDownloader/releases)

### - Loose files (.zip) -
This is a .zip file containing the application and its data.<br>
The executable within it doesn't usually have an icon or extension,

- [CTDM](https://github.com/MatteoPrampolini/CTDM/releases)
- [Stoat](https://github.com/stoatchat/for-desktop/releases/)

### - Whatever is going on with Track Studio -
Track Studio doesn't provide a Linux executable at all, but can be run by using the command `dotnet TrackStudio.dll` within the folder.<br>
You should probably create a shortcut and set the `Exec=` property to `dotnet path/to/TrackStudio.dll` to make it easier to launch.

- [Track Studio](https://github.com/MapStudioProject/Track-Studio/releases)

### - Windows apps -
Windows apps can be run similarly to Track Studio, running them with the command `wine path/to/program.exe`.<br>
You should also be able to open them by double-clicking the .exe file.

For some apps, you'll need to configure setting or install extra dependencies (such as directx runtime) in order for them to run properly.<br>
This can be done either by downloading the Windows versions of these dependencies separately and running them the same way you would on Windows, or if you need to change something more specifically, using `winetricks` from the terminal.

- [Switch Toolbox](https://github.com/KillzXGaming/Switch-Toolbox/releases/tag/Final)


# --- App launcher shortcuts (desktop entries) ---

For some apps, app launcher / "start menu" shortcuts won't be created automatically for you - this is where desktop entries come in.<br>
Desktop entries are text files that live in `/home/username/.local/share/Applications/`, and are named things like "discord.desktop".<br>

Here's a basic desktop file to use as a template:

```
[Desktop Entry]

Type=Application

# App name
Name=My App

# App description
Comment=My app is really cool, it does this...

# Path to the app's executable / command to run
Exec=/home/myuser/Applications/MyApp

# Path to this app's icon (png, jpg, svg etc.)
# If this isn't a path, it will look in the current icon pack instead
Icon=my-app
 
# The app launcher / "start menu" categories this will be sorted into
Categories=Education;Games;Development;

```

Note that if a folder contains spaces you need to put quotes around the entire path (e.g. "~/Documents/My Folder").<br>
If you want to edit an existing app, you can either copy its file from `/usr/share/Applications/` to here, or simply right click it from the app launcher and select "edit".



