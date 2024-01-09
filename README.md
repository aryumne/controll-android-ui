#### APPIUM ON WINDOWS
This program has only ever been tested on windows. So, If you want to running on Linux or MAC, probably you need some adjustment.

### PREPARATION 
Follow the instructions below if using a real device unless. For using android studio, see the documentation for details "https://appium.io/docs/en/2.4/quickstart/".
## 1. INSTALL APPIUM AS GLOBAL VARIABLE
1. run this command "npm i -g appium".
2. run this command run the appium "npx appium -a 127.0.0.1 -p 4723" and you will see the first line of output" like below:

    [Appium] Welcome to Appium v2.0.0
    etc...

## 2. INSTALL SDK COMMAND LINE TOOLS ANDROID, AND SET ENVIRONMENT ON WINDOWS
1. Download SDK Command line tools only on https://developer.android.com/studio#command-line-tools-only for windows.
2. extract the .zip file and you get "cmdline-tools" folder.
3. make sure you have "Android\sdk\" folder in "C:\Users\erlia\AppData\Local" folder. otherwise, you have to create that folder.
4. copy the "cmdline-tools" folder to "C:\Users\your-pc-name\AppData\Local\Android\sdk" folder.
5. in "cmdline-tools" folder, make a folder called "latest". and move all the folders and files in the "cmdline-tools" folder except the "latest" folder to the "latest" folder. the folder structure looks like this:
    -sdk
        -cmdline-tools
            -latest
                -bin
                -lib
                -etc
6. open "edit the systems environtmen variables", in "System variables" edit Path key, and add new path like this "C:\Users\your-pc-name\AppData\Local\Android\sdk\cmdline-tools\latest\bin", save and close. if your are not doing this step, you can not run "sdkmanager" command in any path except in the cmdline-tools\latest\bin folder.
7. open terminal or Windows powershell. run this command (sdkmanager "platform-tools" "build-tools;34.0.0"). Notes: the build-tools version (34.0.0) is latest version (exclude RC) when this program was created.
8. if the command has been successfully runned, you will get new folder in your Android\sdk\ folder like this:
    -sdk
        -cmdline-tools
        -build-tools
        -platform-tools
        -etc
9. install the Java JDK, you can download on this page "https://adoptium.net/en-GB/temurin/releases/. make sure you download the JDK (.msi extention) and not the JRE. after download, install the the jdk file.
9. Next, open "edit the systems environtmen variables" again, in "System variables":
    - add key "ANDROID_HOME" with value "C:\Users\your-pc-name\AppData\Local\Android\sdk";
    - add key "JAVA_HOME" with the value is path of jdk installed for example: "C:\Program Files\Java\jdk-21";
    - edit Path key, and add new path like this "C:\Users\your-pc-name\AppData\Local\Android\sdk\platform-tools";

## 3. SETUP THE REAL DEVICE TO DEBUGGING MODE (ANDROID PHONE)
Set it up for development and enable USB Debugging mode. follow the instructions on this page "https://developer.android.com/studio/debug/dev-options"
    

## 4. CONNECT THE PC TO THE ANDROID DEVICE
1. make sure the android devices has been enabled usb debugging mode.
2. connect the pc to the device using usb cable or others.
3. in terminal windows, run command "adb devices", if the device are connected, it will be showing the id device below "List of devices attached".

## 5. INSTALL THIS PROGRAM
1. clone the repository
2. In the path of repository, and run "npm install" command.
3. make sure you have connected the real device, and appium has already runned. 
4. run "npm start" command.