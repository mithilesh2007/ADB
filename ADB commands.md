# What is ADB
- ADB (Android Debug Bridge) is a command-line tool that allows developers and power users to communicate with an Android device from a computer.

ADB follows a client-server architecture with three components:
-- Client – The computer that sends commands (adb devices, adb install, etc.).
-- Server – A background process on the computer that manages communication.
-- Daemon (adbd) – A service running on the Android device that executes commands.

# Basic ADB commands 
- adb devices (shows the connected devices)
- adb install myapp.apk (adb install myapp.apk)
- adb uninstall com.example.myapp (uninstalls the apk)
- adb shell am start -n com.example.myapp/.MainActivity (A shell session is an interactive command-line environment where you can execute commands on a system. In the context of Android Debug Bridge (ADB), a shell session allows you to run commands directly on an Android device or emulator from your computer.)
- adb logcat (helps to debug app crashes)
- adb -s deviceName shell (opens the shell session for that particular device )
- adb shell getprop ( shows all the properties of the devices )
- adb push fileName /sdcard (so it pushes the file to the sdcard ) 
- adb pull fileName /path ( so it basically pulls the file from the path )
- adb exec-out screencap -p > ./pic.png ( exec-out ends the output to your computer , screencap is a built-in Android command to take a screenshot, -p means to save it in the png file )
- adb shell screenrecord "/sdcard/vidfile.mp4" ( it records the screen and saves the file in vidfile.mp4 )
- adb shell input tap 738 1695 ( this command basically taps on that specific cordinate  )
- adb shell input keyevent 4 ( this command clicks the back button in our device "4" is the std key event for back button . STD key events: https://stackoverflow.com/questions/7789826/adb-shell-input-events )
