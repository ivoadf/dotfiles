# Integration between Keepass and GDrive

Using rclone: https://rclone.org/drive/

Using KeePass2 App

Add trigger on application close 
``` rclone copy path_to_keypass_db GDrive: ```

Trigger on application start 
``` rclone copy GDrive:KeePassDB.kdbx path_to_keypass_dir ```

Integrations with chrome:
[CKP](https://chrome.google.com/webstore/detail/ckp-keepass-integration-f/lnfepbjehgokldcaljagbmchhnaaogpc)

Integration with Android: [KeePassDroid](https://play.google.com/store/apps/details?id=com.android.keepass&hl=en)

Integration with Firefox:
[KeePass Tusk](https://subdavis.com/Tusk/)
