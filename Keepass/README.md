# Keepass and GDrive

Keep Keepass DB in sync with google drive backup, syncs on every DB save.

Inspired by the [Synchronizing with Dropbox](https://keepass.info/help/kb/trigger_examples.html#dbsync) trigger example.

## Dependencies

- [rclone](https://rclone.org/drive/)
- [KeePass2](https://keepass.info/help/v2/setup.html)

## Setup

Create two local copies of your Keepass DB, one that rclone will use and another for Keepass.
Let's call them: `RCLONE.kdbx` and `Keepass.kdbx`

Open `Keepass.kdbx` in Keepass navigate to triggers and add a trigger on **Saved database file**, in the actions add the following:

1. **Change trigger on/off state** state `off` and trigger name leave empty
2. **Execute command line/URL** file/url: `rclone` and arguments: `copy GDrive:RCLONE.kdbx /path/to/your/rclone/db`
3. **Synchronize active database with file/URL** file/url: `/path/to/your/rclone/db`
4. **Execute command line/URL** file/url: `rclone` and arguments: `copy /path/to/your/rclone/db GDrive:`
5. **Change trigger on/off state** state `on` and trigger name leave empty

On DB save this trigger will:

1. Disable trigger
2. Pull latest file from GDrive to `RCLONE.kdbx`
3. Sync open DB `Keepass.kdbx` with `RCLONE.kdbx`, both files are modified to be in sync
4. Push updated `RCLONE.kdbx` to GDRIVE
5. Reenable trigger

## Auto Type on Linux

1. Config global auto-type shortcut. Add this line to i3 config: `bindsym $mod+Ctrl+A exec keepass2 --auto-type`
2. Add [TitleURL](https://addons.mozilla.org/en-US/firefox/addon/url-in-title/) to firefox. Allows keepass to match url by window title
3. Inside the window just hit the shortcut and credentials are auto typed


## Keepass configuration file
Copy `KeePass.config.xml` into `~/.config/KeePass/`


## Integration with Android

Install [Keepass2Android Password Safe](https://play.google.com/store/apps/details?id=keepass2android.keepass2android&hl=en_GB) and open the GDrive file directly, sync will be automatic.
