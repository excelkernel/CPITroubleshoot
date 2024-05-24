# CPImagined Setup and Troubleshooting
Setup and Trobleshoot guide for CPImagined.


So, some CPImagined players had difficulty intsalling client, and i decided to write a quick installation guide. 
It also has troubleshoot section, if something works not-as-designed after installation.

## Microsoft Windows
### Installer:
1. Head to CPI website and download setup utility, choosing _Installer_ option.
2. Extract content of .zip archive using 7-zip, WinRar or Explorer.
3. Run .exe file as adminstrator (or as usual, but dont forget to confirm executing file via UAC).
4. Proceed the installation.
5. Launch and have fun.
### Portable:
1. Head to CPI website and download client, choosing _Portable_ option.
2. Extract content of .zip archive with 7-zip, WinRar or Explorer.
3. Run .exe file.
4. Log in and waddle around.

## Apple MacOS
### Installer: 
_MacOS installer is currently unavaiable._ 
### Portable:
1. Head to CPI website and download client, choosing _Portable_ option under _MacOS_ section.
2. Get [The Unarchiver](https://apps.apple.com/app/the-unarchiver) from App Store.
3. Extract content of .zip archive using The Unarchiver. _Using built-in MacOS utility breaks client files somehow._
4. Copy app to _Applications_ folder.
5. Here we go.
### Installation via Wine:
1. Intall [Homebrew](https://brew.sh/).
2. Install [Wine](https://www.winehq.org/)
3. Install [Winetricks](https://github.com/Winetricks/winetricks)
4. Head to CPI website and download any client version under _Windows_ section. Portable is recommended to avoid problems.
5. Extract content of .zip archive using The Unarchiver.
6. Launch terminal and start Winetricks (``` sh winetrickks ```).
7. Choose _Default Wineprefix_ option.
8. Choose _Run an arbitrary excutable (.exe/.msi/.msu)_ option.
9. Select .exe file that you just exctracted in Finder pop-up.
10. Proceed with installation if you did prefer to use _Installer_ option.
11. Voila. CPI client on your Mac, installed via Wine. Meanigless time waste, since Portable client is avaiable for MacOS.

## GNU/Linux 
### Installation via Wine:
1. Install [Wine](https://www.winehq.org/).
2. Install [Winetricks](https://github.com/Winetricks/winetricks).
3. Head to CPI website and download any client version under _Windows_ section. Portable is recommended to avoid problems.
4. Extract content of .zip archive using 7-zip, PeaZip or any other archive utility.
5. Lauch terminal and start Winetricks (``` sh winetricks ```).
6. Choose _Default Wineprefix_ option.
7. Choose _Run an arbitrary excutable (.exe/.msi/.msu)_ option.
8. Select .exe file you just extracted on Thunar (or any other file manager) pop-up.
9. Proceed with installation if you did prefer to use _Installer_ option.
10. Open terminal.
11. Create {app-name}.desktop file using vim, nano or any other text editor.
12. Write this in the {app-name}.desktop file:
    ```
    [Desktop Entry]
    Name=App-Name
    Exec=wine "C:\Path\To\File.exe"
    Icon=/path/to/iconfile
    Type=Application
    Categories=Wine
    ```
 _Important: Don't forget to insert needed info instead of placeholders._
13. Save file to Desktop folder and quit.
14. Make it executable:
    ``` 
    chmod +x $USER/Desktop/app-name.desktop
    ```
15. Run, log in and waddle around.

## ChromeOS
### Installing via Wine:
Preparation:
1. Go to settings.
2. Choose Developer Settings.
3. Enable Linux Development Environment.

Actual installation (same steps as GNU/Linux):
1. Install [Wine](https://www.winehq.org/).
2. Install [Winetricks](https://github.com/Winetricks/winetricks).
3. Head to CPI website and download any client version under _Windows_ section. Portable is recommended to avoid problems.
4. Extract content of .zip archive using 7-zip, PeaZip or any other archive utility.
5. Lauch terminal and start Winetricks (``` sh winetricks ```).
6. Choose _Default Wineprefix_ option.
7. Choose _Run an arbitrary excutable (.exe/.msi/.msu)_ option.
8. Select .exe file you just extracted on Thunar (or any other file manager) pop-up.
9. Proceed with installation if you did prefer to use _Installer_ option.


## Pale Moon (for most OCs):
_Important: You need to install Adobe Flash to play via Pale Moon._
### Microsoft Windows and Apple MacOS
1. Head to [Pale Moon](https://www.palemoon.org/) website.
2. Go to Downloads.
3. Pick package for your system and install it.
4. Head to [CPI](https://cpimagined.net/) website.
5. Log in and play.
### GNU/Linux and ChromeOS
1. Open terminal.
2. Install Pale Moon package.
   Arch Linux (requires yay or Aura):
   ``` yay -S palemoon-bin / sudo aura -A palemoon-bin ``` _Important: it is highly recommended to install pre-built binary package (palemoon-bin) instead of source (palemoon), because compiling a web browser is long-and-hard way for your pc._
   Ubuntu and ChromeOS (maybe):
   ```
   sudo apt install curl apt-transport-https -y
   curl -fsSL https://download.opensuse.org/repositories/home:stevenpusser/xUbuntu_22.04/Release.key | gpg --dearmor | sudo tee /etc/apt/trusted.gpg.d/home_stevenpusser.gpg > /dev/null
   echo 'deb http://download.opensuse.org/repositories/home:/stevenpusser/xUbuntu_22.04/ /' | sudo tee /etc/apt/sources.list.d/home:stevenpusser.list
   sudo apt update
   sudo apt install palemoon
   palemoon -v
   ```
   _Note: looks like binary for Ubuntu is not avaiable, and you'll need to compile it... Well, good luck._
3. Head to CPI website, log in, blah-blah.


## Troubleshooting (under construction)
### Microsoft Windows
_Problem: Client shows white screen instead of connecting to site._
> Try to clear cache of client. Hit 'Clear cache' in the top menu.
> If clearing cache doesn't help, try to reinstall client. It is recommended to download it again to be sure that this is not an downloading issue.
> Check your firewall and Defender settings. White-list the client. 
> If nothing here helps (uncommon case), try contacting Jeff in #support channel (CPI Discord).

_Problem: SmartScreen blocks executing._
> That's an signature missing issue. Click 'Advanced' option. Then tab 'Yes' / 'Allow' / 'Execute anyway' button.

_Problem: Defender blocks and/or deletes .exe file._
> White-list .exe file.
> You can also just disable Defender. 'Unsafe' option, but increases system performance and doesn't annoy you with messing up your files.
### Apple MacOS
_Problem: When executing app, 'The application "CPImagined Desktop" can't be opened' shows up._
> You may broke client files, if you extracted .zip archive using MacOS default archive utility. You should use The Unarchiver from App Store.

_Problem: App won't execute. '"CPImagined Desktop" cannot be opened because Apple connot check it for malicious software.'_
> That's an signature missing issue too. To allow executing files without signature, you must allow application downloaded from identified developers in Privacy & Security.
### GNU/Linux
_Problem: .desktop file wont execute._
> You probably forgot to mark it executable. Follow point 14 in GNU/Linux guide.
### General
_Problem: I want to go fullscreen. How to do it?_
> F11 or Fn+F11; but fullscreen is currently unavaiable in client.

_Problem: When i want to log in, it shows '502 Bad Gateway'. What's this?_
> It means server is currently down. Commonly it means that game is being updated.

_Problem: It shows '403 Forbidden'._
> You just headed to restricted area. Leave. __Now.__

_Problem: I forgot my password. How do i recover it?_
> DM Jeff or Sora. 

_Problem: I want to change email. Who should i contact?_
> Nobody, basically. Imagined doesn't use emails, and that's the point why you need to cantact staff when resetting password. But emails are kept in database.

_Problem: I want to wipe out my email from database._
> Contact Jeff.

_Problem: I was banned for saying <needed information here>. What should i do?_
> Contact Jeff.

_Problem: My penguin doesn't show._
> Client or game will forget your penguin after some time, for security reasons. Just re-login.

_Problem: It shows 'Incorrect code' for book codes, even if they're written perfectly._
> Book codes are limited to 5 per hour. Keep it in mind.


