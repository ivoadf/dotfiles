# Integration between Keepass and GDrive

Using rclone: https://rclone.org/drive/

Using KeePass2 App

Add trigger on application close 
``` rclone copy path_to_keypass_db GDrive: ```

Trigger on application start 
``` rclone copy GDrive:KeePassDB.kdbx path_to_keypass_dir ```

## Integration with Android
[KeePassDroid](https://play.google.com/store/apps/details?id=com.android.keepass&hl=en)

## Integration on desktop
Use keepass auto-type functionallity.
- Config global auto-type shortcut. Add this line to i3 config: `bindsym $mod+Ctrl+A exec keepass2 --auto-type`
- Add [TitleURL](https://addons.mozilla.org/en-US/firefox/addon/url-in-title/) to firefox. Allows keepass to match url by window title
- Inside the window just hit the shortcut and password get's filled automatically.
