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


# Imp Commands
- adb shell pm list packages (This will show package names )
- adb shell pm path com.example.myapp ( this will show the path of com.example.myapk )
- apktool d <apk_file> ( To disassemble apk files )
- apktool b <decompiled_folder> ( To Reassemble apk files )
- jadx -d <destination> <source_apk> ( To disassemble apk files ,U can’t reassemble apk files using jadx)


# JADX (Java Decompiler)
- Purpose: Decompiles APKs to Java source code
- Output: Java .java files
- Use Case: Reverse engineering apps to analyze their logic

## Features:
Extracts .dex (Dalvik Executable) files from an APK
Converts .dex to Java source code
Allows easy browsing of decompiled Java classes
Provides a GUI (jadx-gui) for easier exploration
Best for: Reading and analyzing app logic (not for modification)
(jadx -d output_folder app.apk)

# APKTool (Smali Decompiler & Rebuilder)
- Purpose: Decompiles APKs to Smali code & resources, allowing modification and rebuilding
- Output: Smali (.smali) files, XML resources, and app structure
- Use Case: Modifying, repackaging, and re-signing APKs

## Features:

Extracts AndroidManifest.xml and other XML resource files
Converts .dex to Smali code (Android bytecode)
Can modify and recompile APKs
Rebuilds APKs after modifications
Best for: Modifying APKs, patching apps, and translating apps
Limitation: Smali is harder to read than Java.
(apktool d app.apk -o output_folder  # Decompile)
(apktool b output_folder -o new.apk  # Recompile)
