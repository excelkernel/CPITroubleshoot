# CPImagined client Setup and Troubleshooting
Setup and Trobleshoot guide for CPImagined.


So, many CPImagined players had some difficulty intsalling client, and i decided to write a quick installation guide. 
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
### Installation via WINE:
1. Intall [Homebrew](https://brew.sh/).
2. Install [Wine](https://www.winehq.org/)
3. Install [Winetricks](https://github.com/Winetricks/winetricks)
4. Head to CPI website and download any client version under _Windows_ section. Portable is recommended to avoid problems.
5. Extract content of .zip archive using The Unarchiver.
6. Launch terminal and start Winetricks (``` sh winetrickks ```).
7. Choose _Default Wineprefix_ option.
8. Choose _Run an arbitrary excutable (.exe/.msi/.msu)_ option.
9. Run .exe file that you just exctracted in Finder pop-up.
10. Proceed with installation if you did prefer to use _Installer_ option.
11. Voila. CPI client on your Mac, installed via Wine. Meanigless time waste, since Portable client is avaiable for MacOS.

