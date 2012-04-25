# encFS mini App

## Overview

With [encFS](http://www.arg0.net/encfs) you can create encrypted filesystems. I use it on my Mac for important files
and it works great. But I had to open the Terminal App and do the mounting. I wanted
something simpler, something I can click on!

So I played around with AppleScript and created this simple App. On first start the App
will search for a file `.doencfs.plist` in the users home directory. This is a simple
file in the Apple Property List format:

    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
        <dict>
            <key>mountpoint</key>
            <string>/Users/myuser/mymountpoint/</string>
            <key>rootdir</key>
            <string>/Users/myuser/myencryptedroot/</string>
        </dict>
    </plist>

You can create it in the home directory yourself if you like. If *doencfs* will not find the file,
then it will prompt you to select the encrypted root folder and mountpoint. After that it will
write the `.doencfs.plist` file in your home folder.

If the file is already present or is just created then you will be asked for your *encfs* password
and the directory will be mounted.

You will have to install encFS first. I can recommend the installation with [HomeBrew](http://mxcl.github.com/homebrew/).

## **Important Note**

Please be careful! Do not run it if you already have mounted your encrypted root! It seems that
encFS will just mount it again. I do not know what the consequences will be!
