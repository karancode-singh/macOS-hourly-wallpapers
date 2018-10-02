# macOS-hourly-wallpapers

Applescript for changing the Mac OS X desktop picture hourly based on the time of day


## What the script does
This is an AppleScript that changes your Mac's desktop picture based on the current hour.  Wallpaper changes every hour.

Each hour has a corresponding folder, which is meant to store images for the hour. For example, if it  is 7:13 PM, following wallpaper will be set:

/Users/YOUR_USER_NAME/Pictures/Wallpapers/HourlyWallpapers/19/sunset.jpg

**The script will randomly select an image from the corresponding folder.** 
The image can be in any supported file type, including JPG, GIF and PNG images.


## What's included
- 1 Retro wallpaper in each hour folder
- Script
- README instructions on how to use and set-up


## How to use and set-up

### Folder structure
You need to create `Wallpapers` folder in your `Pictures` folder and place the `HourlyWallpapers` folder in the `Wallpapers` folder you just created.

### Images
Place the images corresponding to the hour of the day in the corresponding hour folder.

### Script file
The script file itself can be located anywhere.
Let's say we keep it in `/Pictures/Wallpapers/HourlyWallpapers/` folder.

The script must be run at specified intervals using automation of some kind.
I have demonstrated the use of in-built crontab.

### Set-up crontab
Open terminal and enter following
`env EDITOR=nano crontab -e`

Now in the nanoeditor in terminal window enter
`*/10 * * * * /usr/bin/osascript /Users/YOUR_USER_NAME/Pictures/Wallpapers/HourlyWallpapers/wallpaper.scpt`
This set-up makes the script run every 10 minutes

Save by `^+O`.  Close nano by `^+X`

Check that the crontab is set by entering the following in terminal
`crontab -l`


*This work is motivated by https://github.com/pipwerks/OS-X-Wallpaper-Changer and I would love to credit the author of the original script. The original script can be found in the URL mentioned*
