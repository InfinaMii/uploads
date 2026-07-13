# --- Installing the operating system ---

## -- Creating a Live USB --
The process for creating a live Fedora USB is pretty simple compared to some other distros.<br>
Fedora Media Writer can be downloaded from (the Fedora GitHub page)[https://github.com/FedoraQt/MediaWriter/releases/latest]. This is a GUI tool that lets you pick a version of Fedora to download, and will write it to an **empty** USB drive.<br>
Make sure to select **Fedora KDE Plasma Desktop** instead of **Fedora Workstation** in the drop-down if you want a Windows-like experience (rather than the default macOS-like one).<br>
Once it is done, your USB drive can be used to reboot into Fedora.
<br/><br/>


## -- Booting from the USB drive --
If you don't already have an operating system installed (e.g. Windows on the SSD), I believe the computer should automatically boot into the live USB if its inserted due to this being the only available volume?<br>
If it doesn't, you can select it from the BIOS menu. The BIOS menu can be opened by holding the `Esc` key whilst the computer boots, and once it opens there should be a menu on the bottom right that allows you to select which device to boot into (in this instance the Fedora/USB device).<br>
This will enter you into a menu that says something similar to "Start Fedora 44" and "Test this media and start Fedora 44". These both do essentially the same thing, with one doing extra checks to make sure the USB is set up properly. I usually just pick "Start Fedora 44".
<br/><br/>


## -- Installing Fedora --
Once you're in the desktop environment, it should bring up a prompt to install Fedora to the computer.<br>
This is pretty simple so I'm sure you can figure this part out, you basically select your language, date/time, and then pick which drive to install to.<br>
Since you're building a new computer (with no files already on it) you can just tell it to erase the entire drive, and it should ask you to reboot once it is done.<br>

When it reboots, make sure to go through the little welcome guide it gives you, since one of the pages asks you if you would like enable third party repositories (which will make many more apps available from the built-in "discover" app store).
<br/><br/>


# --- Installing Apps ---
Below I've listed the apps that you were interested in installing, as well as what different types of apps there are:
<br/><br/>

## -- System commands --
These are commands that can be entered into the system terminal (on KDE Plasma this is Konsole) to install apps:
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
 
All of these programs will appear in the Discover store anyways, but I think it would be useful to use the terminal for these so that you know roughly how it works.
<br/><br/>


## -- Apps from Flathub Store --
These will appear in the built-in app store, Discover.<br>
Some websites will also have a Flathub button that will open the correct page in Discover for you.<br>

I would recommend going to the Settings tab and clicking Make Default on the right so that Flatpak apps appear first in the list.<br>

- Spotify
- Discord (or Vesktop if you want themes/plugins)
- Prism Launcher
- Krita
- Audacity
- Ryujinx
- Dolphin Emulator
- Inkscape
- OBS Studio
- VLC

You can also install add-ons for apps such as Blender and VLC by finding their page on the store and clicking "Add-ons" at the top.
<br/><br/>


## -- Apps from elsewhere (e.g. GitHub) --
These won't show up in the app launcher so I'd create a shortcut for them (see below)<br>
Standalone apps can come in multiple formats:
<br/><br/>

### - AppImages -
These are single files that contain all of the app's data, rather than coming as a .zip file.<br>
They end with a `.appimage` extension and can be double-clicked to run.

- [khinsiderdownloader](https://github.com/weespin/KhinsiderDownloader/releases)
<br/><br/>

### - Other installable packages (rpm, deb, etc.) -
Sometimes, you'll be given a list of other formats to select from (such as .deb, .rpm, or .nix).<br>
The correct file for Fedora is the one ending in `.rpm`, and if given an option you'll want to select the "x86" or "x64" version (arm64 and aarch versions are for devices with mobile processors).<br>
Once the download finishes, you can then double-click on this file and it will allow you to install it using the Discover store app.
<br/><br/>

### - Loose files (.zip, .tar.gz) -
This is a .zip or .tar.gz file that containing the application and its data.<br>
Both .tar.gz and .zip files can be extracted by dragging them towards empty space in the file manager, or right clicking and selecting "Extract To..."<br>
The executable within it doesn't usually have an icon or extension, for example Stoat's file is just called "stoat-desktop".

- [CTDM](https://github.com/MatteoPrampolini/CTDM/releases)
- [Stoat](https://github.com/stoatchat/for-desktop/releases/)
<br/><br/>

### - Whatever is going on with Track Studio -
Track Studio doesn't provide a Linux executable at all, but can be run by using the command `dotnet TrackStudio.dll` within the folder.<br>
You should probably create a shortcut and set the `Exec=` property to `dotnet path/to/TrackStudio.dll` to make it easier to launch.

- [Track Studio](https://github.com/MapStudioProject/Track-Studio/releases)
<br/><br/>

### - Windows apps -
Windows apps can be opened similarly to Track Studio, running them with the command `wine path/to/program.exe`.<br>
You should also be able to open them by double-clicking the .exe file.

For some apps, you'll need to configure setting or install extra dependencies (such as directx runtime) in order for them to run properly.<br>
This can be done either by downloading the Windows versions of these dependencies separately and running them the same way you would on Windows, or if you need to change something more specifically, using `winetricks` from the terminal.<br>
I would typically recommend using an alternative for most things, but if there's a Windows app that can't be replaced it might work through Wine.

- [Switch Toolbox](https://github.com/KillzXGaming/Switch-Toolbox/releases/tag/Final)
- [BrawlBuilder](https://github.com/mogzol/BrawlBuilder/releases/latest)
<br/><br/>


## -- Other app considerations --
These are some other things that you mentioned which I thought I would go over:
<br/><br/>

### - Office apps (Word, PowerPoint etc.) -
The two main choices (to my knowledge) are LibreOffice and OnlyOffice:
- LibreOffice comes with the most features, and has a customisable interface that is less familiar/modern
- OnlyOffice has less features but aims to match Microsoft Office in its appearance and feature set<br>
Both will be able to open any files you'd want to open, so it's mainly down to preference. (onlyoffice apparently added an optional ai tab but it seems like if you don't sign in with an api key it can't do anything)
They're also both on Flathub, so you'll be able to get them from the package manager.
<br/><br/>

### - FTP client -
On Linux, typically you don't need a separate app to access FTP devices - this is something that your file manager can do already.<br>
On KDE Plasma, you can go to the Network tab and type `ftp://ip.address` into the file path bar (for example `ftp://192.168.7.29`), and it will open the FTP folder natively.<br>
You can then right click in an empty spot and select "Add to Places" to pin this to the sidebar on the left.
<br/><br/>


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



