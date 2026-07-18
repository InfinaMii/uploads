# Introduction
This is a guide I've put together that goes over the process of setting up Fedora Linux, updating the computer, installing apps from various places, and a few other things (such as where data is stored and how to install themes).<br>

To the top right of the page, there should be a hamburger button that opens up an "Outline" menu.<br>
I would recommend opening this to easily see what things are in this document and to skip to different sections, as well as using Ctrl+F or "Find in Page" to search for specific words.
<br/><br/><br/>


# Installing the operating system

## Creating a Live USB
The process for creating a live Fedora USB is pretty simple compared to some other distros.<br>

Fedora Media Writer can be downloaded from [the Fedora GitHub page](https://github.com/FedoraQt/MediaWriter/releases/latest). This is a program that lets you pick a version of Fedora to download, and will write it to an **empty** USB drive.<br>
Make sure to select **Fedora KDE Plasma Desktop** instead of **Fedora Workstation** in the drop-down if you want a Windows-like experience (rather than the default macOS-like one).<br>

Once it is done, your USB drive can be used to install Fedora on the computer.
<br/><br/>


## Booting from the USB drive
If the computer's SSD is empty, I believe it should automatically boot into the USB due to it being the only available device?<br>
If it doesn't, you can select it from the BIOS menu.<br>

The BIOS menu can be opened by holding the `Esc` key whilst the computer boots, and once it opens there should be a menu on the bottom right to select which device to boot into (in this instance the Fedora/USB device).<br>

This will open a menu that says something similar to "Start Fedora 44" and "Test this media and start Fedora 44".<br>
These both do essentially the same thing, with one doing extra checks to make sure the USB is set up properly. I usually just pick "Start Fedora 44".
<br/><br/>


## Installing Fedora
Once you're in the desktop environment, it should bring up a window to install Fedora to the computer.<br>

This is pretty simple so I'm sure you can figure this part out, you basically select your language, date + time, and then pick which drive to install to.<br>
Since you're building a new computer (with no files already on it) you can just tell it to erase the entire disk.<br>
If it asks, don't bother setting up a root account, as this isn't necessary for a personal computer.<br>

Once it is done, it should say "Successfully Installed" and ask you to reboot the computer.<br>
After logging in, make sure to go through the little welcome guide it gives you, since one of the pages asks you if you would like enable third party repositories (which will make many more apps available from the built-in "Discover" app store).
<br/><br/>


## System Updates
You should probably download updates the first time you install Fedora, as with any operating system.<br>

To do this, first make sure you're connected to wifi (there should be an icon in the taskbar for this).<br>
Next, open up the "Discover" app (the app store), click on the "Updates" tab and select "Update All" in the top-right.<br>

This will update all of your installed apps as well as the system itself.<br>
Once this is done, you can restart your computer to apply any updates to the system. App updates should apply instantly, without needing a restart.
<br/><br/>


# Installing Apps
Below I've listed the apps that you were interested in installing, as well as what different types of apps there are:
<br/><br/>

## System commands
These are commands that can be entered into the system terminal (on KDE Plasma this is Konsole) to install programs, for example:
`sudo dnf install app-one app-two`

`sudo` = admin (will ask for password)<br>
`dnf install` = package manager, install<br>
`app-one app-two` = example of apps to install
<br><br>

These are the apps that I would like you to install using this method:
- Dotnet Runtime 8.0: `dotnet-runtime-8.0`
  - Used for running Track Studio
- Steam: `steam`
  - Steam's flatpak can have issues with recognising controllers/accessing files, so I like to install the official one
- Wine: `wine` and `winetricks`
  - Used for opening and configuring Windows applications respectively
 
All of these programs will appear in the Discover store anyways, but I think it would be useful to use the terminal for these so that you know roughly how it works.<br>
The first time you run a command with `sudo`, it'll give you a brief warning - this is normal, and is there to make sure that you aren't entering anything dangerous by mistake.
<br/><br/>


## Apps from Flathub Store
These will appear in the built-in app store, Discover.<br>
Some websites also have a Flathub button that will open the correct page in Discover for you.<br>

I would recommend going to the Settings tab and clicking Make Default on the right so that Flatpak apps will be suggested first (rather than fedora ones).<br>
If you are having issues with the Flatpak version or would like to install the Fedora-specific version instead, you can always uninstall it and use the drop-down in the top right of the app's page to switch to another version.

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
- awesome calculator

You can also install add-ons for apps such as OBS and VLC by finding their page on the store and clicking "Add-ons" at the top.
<br/><br/>


## Apps from elsewhere (e.g. GitHub)
These won't show up in the app launcher, so I'd create a shortcut for them (see the [App Launcher Shortcuts](#app-launcher-shortcuts-desktop-entries) section below)<br>
Standalone apps can come in multiple formats:
<br/><br/>


### AppImages
These are single files that contain all of the app's data, rather than coming as a .zip file.<br>
They end with a `.appimage` extension and can be double-clicked to run.

- [khinsiderdownloader](https://github.com/weespin/KhinsiderDownloader/releases)
<br/><br/>


### Other installable packages (rpm, deb, etc.)
Sometimes, you'll be given a list of other formats to select from (such as .deb, .rpm, or .nix).<br>
The correct file for Fedora is the one ending in `.rpm`, and if there are multiple choices you'll want to select the "x86" or "x64" version (arm64 and aarch versions are for devices with mobile processors).<br>

Once the download finishes, you can then double-click on this file and it will allow you to install it using Discover.
<br/><br/>


### Loose files (.zip, .tar.gz)
This is a .zip or .tar.gz file that contains the application and its data.<br>
Both .tar.gz and .zip files can be extracted by dragging them towards empty space in the file manager, or right clicking them and selecting "Extract To..."<br>
The application within it doesn't have an icon or extension, for example Stoat's file is just called "stoat-desktop".

- [CTDM](https://github.com/MatteoPrampolini/CTDM/releases)
- [Stoat](https://github.com/stoatchat/for-desktop/releases/)
<br/><br/>


### Whatever is going on with Track Studio
Track Studio doesn't provide a Linux executable at all, but can be run by using the command `dotnet TrackStudio.dll` within the folder.<br>
(right click -> Open Terminal Here)<br>
You should probably create a shortcut and set the `Exec=` property to `dotnet path/to/TrackStudio.dll` to make it easier to launch.

- [Track Studio](https://github.com/MapStudioProject/Track-Studio/releases)
<br/><br/>


### Windows apps
Windows apps can be opened similarly to Track Studio, running them with the command `wine path/to/program.exe`.<br>
You should also be able to open them by double-clicking the .exe file.

For some apps, you'll need to install extra dependencies (such as DirectX Runtime) in order for them to run properly.<br>
This can be done by downloading the Windows versions of these dependencies separately and running them the same way you would on Windows.<br>

I would recommend using an alternative for most things, but if there's a Windows app that can't be replaced it might work through Wine.

- [Switch Toolbox](https://github.com/KillzXGaming/Switch-Toolbox/releases/tag/Final)
- [BrawlBuilder](https://github.com/mogzol/BrawlBuilder/releases/latest)
<br/><br/>


## Other app considerations
These are some other things that you mentioned which I thought I would go over:
<br/><br/>


### Office apps (Word, PowerPoint etc.)
The two main choices (to my knowledge) are LibreOffice and OnlyOffice:
- LibreOffice comes with the most features, and has a customisable interface that is less familiar/modern
- OnlyOffice has less features overall but aims to match Microsoft Office in its appearance and feature set<br>

Both will be able to open any files you'd want to open, so it's mainly down to preference.<br>
&emsp;(onlyoffice apparently added an optional ai tab but it seems like if you don't sign in with an api key it can't do anything)<br>
They're also both on Flathub, so you'll be able to get them from the package manager.
<br/><br/>


### FTP client
On Linux, typically you don't need a separate app to access FTP devices - this is something that your file manager can do already.<br>

On KDE Plasma, you can go to the Network tab and type `ftp://ip.address` into the file path bar (for example `ftp://192.168.7.29`), and it will open the FTP folder natively.<br>
You can also right click in an empty spot and select "Add to Places" to pin this to the sidebar on the left.
<br/><br/>


### DaVinci Resolve
Blackmagic Design, the developers of DaVinci Resolve, haven't created a seamless method of installing it on most Linux distros, as well as not supporting certain video formats unless you pay for the Studio version.<br>
Fortunately, both of these problems are easily solved using the DaVinci Helper app. [There's a guide detailing how to use it here.](https://github.com/H3rz3n/How-install-DaVinci-Resolve-in-Fedora-Linux)
<br/><br/>


### Firefox Extension
You didn't mention this one, but I think you would find it useful.<br>

If you go to the Firefox Add-On Browser, there is an extension called "Plasma Integration" that provides some extra utilities:
- Downloads will show a desktop notification for their progress / when they are completed
- Currently-playing music and videos will show up in the taskbar (this can be disabled)
- Firefox tabs can be searched for through the app launcher / "start menu"
<br/><br/>


# App launcher shortcuts (desktop entries)

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

Note that if a folder's name contains spaces, you need to put quotes around the entire path (e.g. "~/Documents/My Folder").<br>

If you want to edit an existing app, you can either copy its file from `/usr/share/Applications/` to here, or simply right click it from the app launcher and select "Edit Application".
<br/><br/>


# App data directories
On Linux, there are three main locations that apps will store their data/configuration files.<br>
You can think of these sort of like the AppData folders on Windows:<br>

- `/home/username/.var/app/` - this is where Flatpak apps (from the Discover store) usually store their data (e.g. .var/app/org.ryubing.Ryujinx)
- `/home/username/.local/share/` - this is where most other apps will store data (e.g. .local/share/Steam)
- `/home/username/.config/` - a secondary folder that some apps might use to store configuration files
- Firefox stores its data in `/home/username/.mozilla` for some reason. No clue why.

You'll need to turn on hidden files in order to see these folders (unless you want to type them into the path bar instead).<br>
To do this, click on the hamburger menu in the top right of your file explorer, go down to More, View, and then "Show Hidden Files".
<br/><br/>


## Windows app data paths + some Steam games
Windows apps, as well as any Steam games which use the Proton translation layer, will store their data in virtual Windows drives:<br>

- For any .exe files opened using Wine, their data can be found by going to `/home/username/.wine/drive_c/` and then navigating to the place they usually store their data on Windows.<br>

- For Steam games using Proton, their data will be within `/home/username/.local/share/Steam/steamapps/compatdata/[GAME_ID]/pfx/drive_c/`.<br>
To find out what the game's ID is, you can either go to the game's Store page (it will be in the URL), or check the game's shortcut in the app launcher (right click -> Edit Application -> Command-line arguments)
<br/><br/>


# Customisation
The desktop environment, KDE Plasma, is very customisable, with things such as icon packs, title bars, and even the taskbar layout being configurable.<br>
Here is a brief overview of what options are available:<br>

*I'm not including the Windows 7 conversion theme here, as it needs to install several components separately and I think that learning Linux is easier without changing the system this much.*
*I would also recommend getting used to how the desktop works before customising it too heavily e.g. layout changes*
<br/><br/>


## Latest official themes
The latest version of KDE Plasma (Plasma 6.7) comes with new Frutiger Aero style themes, Oxygen and Air.<br>

Fedora 44 comes with Plasma 6.6 (as 6.7 is pretty new), so it doesn't come with these by default.<br>
If you have updated your system already (you can check the version in Settings > About), you can install them by entering the command `sudo dnf install plasma-oxygen` into Konsole.<br>
These will then be available in the "Global Theme" page of the Settings app (see the [Global Theme section](#global-theme) below for more details).
<br/><br/>


## Panel and Widgets Layout
KDE Plasma allows you to edit the layout of the Panel (taskbar) as well as put widgets on the Desktop.<br>

To edit the Desktop, right click and select "Enter Edit Mode".<br>
From here, you can select "Add or Manage Widgets" in the top left, and drag whichever widgets you like onto the Desktop.<br>
These can be placed and resized similar to how you would expect on an Android phone.<br>

To edit the Panel, right-click on it and select "Show Panel Configuration".<br>
From here it acts similarly to the Desktop - you can drag around widgets, hover over things to change their settings, and change the properties of the Panel such as whether it is translucent or opaque, whether it floats, its position and size.<br>
<br/><br/>


## Colors and Themes menu
The following items can be found within the "Colors and Themes" menu of the Settings app:
<br/><br/>


### Global Theme
Global Themes control multiple aspects of the system at the same time, including icons, cursors, window decorations and sounds.<br>

Upon selecting a theme, you also get the option to copy the desktop layout from it. This will re-arrange the task bar and any widgets on the Desktop to match the theme, so don't tick this option unless you're sure you want it.<br>
You can also save your current settings as a Global Theme by selecting the "Save Current Theme" option in the top right, or get new Global Themes using the "Get New" button.
<br/><br/>


### Colors
Here you can set the system accent colors, as well as the color scheme for apps.

You can set the accent color using the buttons at the top, as well as deciding whether this color should be automatically selected from the wallpaper.<br>

Color schemesthe colors that applications will use for things such as the background, text and hyperlinks.<br>
You can edit these by hovering them, pressing the edit icon, editing the desired colors and pressing Save As - though there are so many colors that I find it difficult to know which ones to modify.<br>
You can also get new ones by pressing the "Get New" button in the top right.
<br/><br/>


### Application Style
This determines what things such as check boxes, scroll bars and buttons look like within apps.<br>
You can also press "Configure icons and toolbars" to set whether icons will be shown in menus.<br>

This page is the least interesting of them all but can be important depending on the look you're going for.
<br/><br/>


### Plasma Style
The Plasma style determines how elements of the Plasma desktop will look, such as the panel (or taskbar), the app launcher, and any desktop widgets.
You can get new Plasma styles using the "Get New" button in the top right.
<br/><br/>


### Window Decorations
Window decorations are the bar above the window that holds the minimize, maximize and close buttons.<br>

Here you can select a visual style for these decorations, including new ones using the "Get New" button in the top right.<br>
Additionally, you can rearrange or add buttons to the title bar using the "Configure Titlebar Buttons" option (for example, if you wanted them to be on the left like on macOS)<br>

You can also add borders to your windows using the drop-down in the top-center of the window.
<br/><br/>


### Icons
Pretty self explanatory, here you can select what icons apps will use, as well as getting more using "Get New" as usual.
<br/><br/>


### Cursors
Here you can choose which mouse cursors to use, as well as setting their size.<br>
The "Configure Launch Feedback" button allows you to set what animation plays when an app is launched (by default, its icon will bounce next to the mouse cursor for 5 seconds)<br>
Also has a "Get New" button.
<br/><br/>


### System Sounds
Here you can set what sounds will play with the system? I guess?<br>
For example, the start-up sound, screenshot sound, sounds that play when a pop-up appears.
<br/><br/>


### Splash Screen
This is not the screen that appears when the system boots, but rather the one that shows up after logging in (while the desktop is loading).<br>
Personally I like to keep this set to "Breeze" or "None", as the desktop loads so fast nowadays that you barely see it anyways, and a colorful one popping up for just one second is a bit strange.
<br/><br/>


## Fonts
Fonts can be installed as you would expect, by downloading the desired .ttf or .otf file and double-clicking on it.<br>
You can then change which fonts will be used for the window title, menus, and general apps (as well as their sizes) in the "Text & Fonts" page of the Settings app.
<br/><br/>


## Wallpaper
This is your Wallpaper. You know this. I don't know why I'm putting it here besides that it would feel odd to leave it out.<br>
You can set this in the Wallpaper page in Settings, by right-clicking on the desktop, or by right-clicking on an image and selecting "Set as Wallpaper".<br>

From the Settings page, you can also use the "Get New Plugins" button to install various different types of wallapers, such as shaders, videos, and effects like rain and snow.<br>
<br/><br/>


## Animations + Other Effects
Most animations can be set in the "Animations" page of the Settings app, such as maximize, minimize as well as their speed.<br>
However, there's a second place that animations can be configured from:
<br/><br/>


### Desktop Effects
Desktop Effects can be found within the Window Management page.<br>
These contain default system settings such as making unresponsive windows turn grey, but also has various other fun options:

- Wobbly Windows makes windows move like jelly when you drag them around the screen
- Fall Apart makes windows break into pieces when you close them
Various other effects can be downloaded from the "Get New" button. Note that if you install an Open/Close animation, it will be in the Animations page rather than the Desktop Effects one.
<br/><br/>
