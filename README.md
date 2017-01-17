# Lock OS X from terminal

I wanted to lock my Mac with a keyboard shortcut, without putting it to sleep. Eg. when compiling something but having to leave the desk. 

In many posts online you see people recommending the keyboard shortcut: "Control-Shift-Power button" which turns off the screen, but this only locks the computer provided you have "Require password immediately". I did not want to change the password timer.

I ended up finding one post on StackExchange ([link](https://apple.stackexchange.com/questions/80058/lock-screen-command-one-liner/123738#123738)) which uses a part of the Keychain Access program to lock the screen. This was the cleanest way I could find. 

## Usage
If you just want to run the command from a terminal, simply write ```./lockscreen```

If you want a keyboard shortcut, do the following: 

1. Place the file ```lockscreen``` somewhere. I have it in a folder called ```Documents/scripts```.
2. Open ```Automator``` and create a new ```Service```. 
3. Add the action ```Run AppleScript``` 
4. In the script window, write: ```do shell script "/path/to/the/file/lockscreen``` and save it with a suitable name.
5. Then go to ```System Preferences > Keyboard > Shortcuts```
6. Under ```Services``` you will find the Automator service. Then you can apply a keyboard shortcut of your liking. I use ```⌘-⌃-⌥-L```.

## Compile yourself
If you don't trust my binary you can compile it from scratch. Download ```main.m``` and simply run the command shown in the StackExchange thread: ```clang -framework Foundation main.m -o lockscreen```

