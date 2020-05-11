---
layout: post
title: How to survive with Flutter Installation
description: A whacky documentation.
summary:  A whacky documentation.
tags: [documentation, technical]
---

It is not hard to build a simple native mobile Android app on Linux. But installation of [Kotlin](https://developer.android.com/studio) and [Flutter](https://flutter.dev/) is very tricky. For me, it takes up to 3 days, 15-page of documentation for 1 hour of tutorial. What a relentless effort.

Here is my whacky documentation for common issues. Hope it will help you with the first steps for Ubuntu 18.04/ 20.04, especially as an Android starter.


# The good

**Highly recommendation:**
*  Ideally, your setup for `Java` should be version 8. Check the Java version by
    ```
    sudo update-alternatives --config java

    ```
    If you don’t have any version, try:
    ```
    sudo apt install openjdk-8-jdk-headless
    ```

    And remember to set up in .bashrc. For example
    ```
    export $JAVA_HOME= /usr/lib/jvm/java-8-openjdk-amd64
    ```

*   Install Android Studio (Kotline) from the website, not the snap provided by App Store in ubuntu.



![](https://emmablogimg.s3.amazonaws.com/2020-05-11-kotlin-and-flutter/image11.png )



# The bad & ugly

Most of issues in the below is related to `flutter doctor -v`, a command to diagnose issues of running `flutter`.


### **Set up a direct path for flutter**

Description is after installing from source, you can not call `flutter doctor`

Solution

Open your `.bashrc` or `.profile` to add an absolute file path of `flutter/bin`

```

export PATH="$PATH:/path/to/flutter/bin"

```

Then, run

```

. ~/.profile

```

Or

```

. ~/.bashrc

```

This will help an update be effective for the next command.


### **Android SDK not found at this location.**

Try

```

sudo apt install android-sdk

```


### **Unable to locate Android SDK**

Description

```

[✗] Android toolchain - develop for Android devices

    ✗ Unable to locate Android SDK.

      Install Android Studio from: https://developer.android.com/studio/index.html

      On first launch it will assist you in installing the Android SDK components.

      (or visit https://flutter.dev/docs/get-started/install/linux#android-setup for detailed instructions).

      If the Android SDK has been installed to a custom location, set ANDROID_SDK_ROOT to that location.

      You may also want to add it to your PATH environment variable.

```

Solution**:**

Add these line into your `~/.bashrc`

```

export ANDROID_SDK_ROOT=/usr/lib/android-sdk

export ANDROID_HOME=$ANDROID_SDK_ROOT

export PATH=$ANDROID_SDK_ROOT/cmdline-tools/tools/bin:$PATH

```


### **Flutter requires Android SDK 28 and the Android BuildTools 28.0.3**

```    

  To update using sdkmanager, run:

        "/usr/lib/android-sdk/tools/bin/sdkmanager" "platforms;android-28" "build-tools;28.0.3"

      or visit https://flutter.dev/docs/get-started/install/linux#android-setup for detailed instructions.

```


### **Issue of sdk manager with `java.lang.IllegalArgumentException`**

```

 at com.android.sdklib.tool.sdkmanager.SdkManagerCliSettings.&lt;init>(SdkManagerCliSettings.java:428)

        at com.android.sdklib.tool.sdkmanager.SdkManagerCliSettings.createSettings(SdkManagerCliSettings.java:152)

        at com.android.sdklib.tool.sdkmanager.SdkManagerCliSettings.createSettings(SdkManagerCliSettings.java:134)

        at com.android.sdklib.tool.sdkmanager.SdkManagerCli.main(SdkManagerCli.java:57)

```

The problem is `sdkmanager`. Seem like my problem is an inconsistent of build-tools of the previous version installed by Ubuntu and the zip file downloaded from the website → fix


### **Issue with sdk manager: Failed to read or create install properties file**

Try to search for `chmod 777` or `chmod 775`


### **Android license status unknown.**

```

     Try re-installing or updating your Android SDK Manager.

      See https://developer.android.com/studio/#downloads or visit visit https://flutter.dev/docs/get-started/install/linux#android-setup for detailed instructions.

```

Try to solve by Android studio or `sdk`



![](https://emmablogimg.s3.amazonaws.com/2020-05-11-kotlin-and-flutter/image1.png )



### **Android licenses not accepted**

Description

```

[!] Android toolchain - develop for Android devices (Android SDK version 29.0.3)

    ✗ Android licenses not accepted.  To resolve this, run: flutter doctor

      --android-licenses

```

Solution

Run `flutter doctor --android-licenses` and accept `Y` for all terms.

You might enter a warning `Warning: File /home/emma/.android/repositories.cfg could not be loaded..` which makes all `Y` not recorded.


### **STILL can not accept all licenses**

```

Warning: File /home/emma/.android/repositories.cfg could not be loaded..        

```

Try create that file

```

mkdir -p .android && touch ~/.android/repositories.cfg

```

If it does not work, let us try to make sure you have Java 8 and SDKmanager, and try

```

Sudo yes | sdkmanager --liscenses

```


### **ANOTHER TIME, STILL NOT**

Go to android studio and check
```
sudo update-alternatives --config java

unset JAVA_OPTS
```

At line 31 of your file im `/path/to/android-sdk/cmdline-tools/latest/bin/sdkmanager`

```

DEFAULT_JVM_OPTS='"-Dcom.android.sdklib.toolsdir=$APP_HOME" -XX:+IgnoreUnrecognizedVMOptions'

```

Check your JAVA

```

sudo /usr/lib/android-sdk/cmdline-tools/latest/bin/sdkmanager --licenses

```

At the end, try this [https://stackoverflow.com/questions/54287619/could-not-find-or-load-main-class-java-se-ee-while-running-sdkmanager-licenc](https://stackoverflow.com/questions/54287619/could-not-find-or-load-main-class-java-se-ee-while-running-sdkmanager-licenc)


![](https://emmablogimg.s3.amazonaws.com/2020-05-11-kotlin-and-flutter/image6.png )



### A forever waiting

Description

`Waiting for another flutter command to release the startup lock…`

Solution

Try

```

rm ~/development/flutter/bin/cache/lockfile

```


### **Flutter plugin not installed; this adds Flutter specific functionality.**

```

flutter config --android-studio-dir /usr/bin/android-studio

```


![](https://emmablogimg.s3.amazonaws.com/2020-05-11-kotlin-and-flutter/image13.png)


![](https://emmablogimg.s3.amazonaws.com/2020-05-11-kotlin-and-flutter/image14.png )



### **Dart plugin not installed; this adds Dart specific functionality.**

[https://dart.dev/get-dart](https://dart.dev/get-dart)


![](https://emmablogimg.s3.amazonaws.com/2020-05-11-kotlin-and-flutter/image9.png )


Go to the Android studio and fill it with the flutter sdk and restart.


![](https://emmablogimg.s3.amazonaws.com/2020-05-11-kotlin-and-flutter/image3.png )


Still not work,

I tried the not `sudo` mode for Android and restart the studio.


### **Failed to read or create install properties file**

Try

```
sudo chmod 777 directory
```


### **Android license status unknown when trying to accept licenses.**

 ```

Android license status unknown.

      Try re-installing or updating your Android SDK Manager.

      See https://developer.android.com/studio/#downloads or visit visit

      https://flutter.dev/docs/get-started/install/linux#android-setup for

      detailed instructions.

```

While `flutter doctor --android-licenses -v` due to `Java`

```

Error: Could not find or load main class java.se.ee

```

Try:

```

unset JAVA_OPTS

```

Run

```

/path/to/sdkmanager --update

```


### **No devices found**

Create an emulator by going to android studio. Look at the top of the user interface and search for the icon


![](https://emmablogimg.s3.amazonaws.com/2020-05-11-kotlin-and-flutter/image12.png )


Choose create a new device by the following steps:


![](https://emmablogimg.s3.amazonaws.com/2020-05-11-kotlin-and-flutter/image7.png )


![](https://emmablogimg.s3.amazonaws.com/2020-05-11-kotlin-and-flutter/image8.png )


![](https://emmablogimg.s3.amazonaws.com/2020-05-11-kotlin-and-flutter/image4.png )


Restart and IDE and check the below box



![](https://emmablogimg.s3.amazonaws.com/2020-05-11-kotlin-and-flutter/image5.png )



![](https://emmablogimg.s3.amazonaws.com/2020-05-11-kotlin-and-flutter/image2.png )


# Done!

Some take-away:

*   Java 8 is still the king in the ecosystem despite the latest version 11 was released 6 years behind.
*   Highly recommend using `Maven` or `Bazel` to deploy any source code. At least it will help you deal with problems with dependencies much less painfully.
*   For developer software in Linux, it is better to install from source code than `snap` distributed in the App Store.
