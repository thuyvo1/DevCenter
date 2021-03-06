---
layout: tutorial
title: Adding the MobileFirst Foundation SDK to Android Applications
breadcrumb_title: Android
relevantTo: [android]
weight: 3
---
## Overview
The MobileFirst Foundation SDK consists of a collection of dependencies, available through [Maven Central](http://search.maven.org/), that you can add to your Android Studio project. The dependencies correspond to core functions and other functions:

* **IBMMobileFirstPlatformFoundation** - Implements client/server connectivity, handles authentication and security aspects, resource requests, and other required core functions.
* **IBMMobileFirstPlatformFoundationJSONStore** - Contains the JSONStore framework. For more information, review the [JSONStore for Andoid tutorial](../../using-the-mfpf-sdk/jsonstore/android/).
* **IBMMobileFirstPlatformFoundationPush** - Contains the Push Notifications framework. For more information, review the [Notifications tutorials](../../notifications/).

In this tutorial you will learn how to add the MobileFirst Native SDK using Gradle to either a new or existing Android Studio application. You will also learn how to configure the MobileFirst Server to recognize the application, as well as find information about the MobileFirst configuration files that are added to the project.

> For instruction to manually add the SDK files to a project, [visit the user documentation](http://www-01.ibm.com/support/knowledgecenter/SSHS8R_8.0.0/wl_welcome.html).

**Prerequisites:**

- Android Studio and MobileFirst CLI installed on the developer workstation.  
- MobileFirst Server to run locally, or a remotely running MobileFirst Server
- Make sure you have read the [Setting up your MobileFirst development environment](../../setting-up-your-development-environment/mobilefirst-development-environment) and [Setting up your Android development environment](../../setting-up-your-development-environment/android-development-environment) tutorials.

#### Jump to:

- [Adding the MobileFirst Native SDK](#adding-the-mobilefirst-native-sdk)
- [Updating the MobileFirst Native SDK](#updating-the-mobilefirst-native-sdk)
- [Generated MobileFirst Native SDK artifacts](#generated-mobilefirst-native-sdk-artifacts)
- [Tutorials to follow next](#tutorials-to-follow-next)

## Adding the MobileFirst Native SDK
Follow the below instructions to add the MobileFirst Native SDK to either a new or existing Android Studio project, and registering the application in the MobileFirst Server.

Before starting, make sure the MobileFirst Server is running.  
If using a locally installed server: From a **Command-line** window, navigate to the server's folder and run the command: `./run.sh` in Mac and Linux or `run.cmd` in Windows.

### Creating an Android application
Create an Android Studio project or use an existing one.  

### Adding the SDK

1. In **Android → Gradle Scripts**, select the **build.gradle (Module: app)** file.

2. Add the following lines below `apply plugin: 'com.android.application'`:

    ```xml
    repositories{
        jcenter()
    }
    ```

3. Add the following inside `android`:

    ```xml
    packagingOptions {
        pickFirst 'META-INF/ASL2.0'
        pickFirst 'META-INF/LICENSE'
        pickFirst 'META-INF/NOTICE'
    }
    ```

4. Add the following lines inside `dependencies`:

    ```xml
    compile group: 'com.ibm.mobile.foundation',
    name: 'ibmmobilefirstplatformfoundation',
    version: '8.0.+',
    ext: 'aar',
    transitive: true
    ```

    Or in a single line:

    ```xml
    compile 'com.ibm.mobile.foundation:ibmmobilefirstplatformfoundation:8.0.+'
    ```

5. In **Android → app → manifests**, open the `AndroidManifest.xml` file. Add the following permissions above the **application** element:

    ```xml
    <uses-permission android:name="android.permission.INTERNET"/>
    <uses-permission android:name="android.permission.ACCESS_WIFI_STATE"/>
    ```
6. Add the MobileFirst UI activity next to the existing **activity** element:

    ```xml
    <activity android:name="com.worklight.wlclient.ui.UIActivity" />
    ```

> If a Gradle Sync request appears, accept it.

### Registering the application
1. Open a **Command-line** window and navigate to the root of the Android Studio project.  

2. Run the command:

    ```bash
    mfpdev app register
    ```
    - If a remote server is used, [use the command `mfpdev server add`](../../using-the-mfpf-sdk/using-mobilefirst-cli-to-manage-mobilefirst-artifacts/#add-a-new-server-instance) to add it.

The `mfpdev app register` CLI command first connects to the MobileFirst Server to register the application, followed by generating the **mfpclient.properties** file in the **[project root]/app/src/main/assets/** folder of the Android Studio project, and adding to it the metadata that identifies the MobileFirst Server.

> <span class="glyphicon glyphicon-info-sign" aria-hidden="true"></span> **Tip:** The application registration can also be performed from the MobileFirst Operations Console:    
>
> 1. Load the MobileFirst Operations Console.  
> 2. Click the "New" button next to "Applications" to register a new application and follow the on-screen instructions.  
> 3. Once the application is registered, navigate to the application's **Configuration Files** tab and copy or download the **mfpclient.properties** file. Follow the onscreen instructions to add the file to your project.

### Creating an WLClient instance
Before using any MobileFirst-supplied APIs, create a `WLClient` instance:

```java
WLClient.createInstance(this);
```

**Note:** Creating a `WLClient` instance should only happen once in the entire application lifecycle. It is recommended to use the Android Application class to do it.

## Updating the MobileFirst Native SDK
To update the MobileFirst Native SDK with the latest release, find the release version number and update the `version` property accordingly in the **build.gradle** file.  
See step 4 above.

SDK releases can be found in the SDK's [JCenter repository](https://bintray.com/bintray/jcenter/com.ibm.mobile.foundation%3Aibmmobilefirstplatformfoundation/view#).

## Generated MobileFirst Native SDK artifacts

### mfpclient.properties
Located at the **./app/src/main/assets/** folder of the Android Studio project, this file contains server connectivity properties and is user-editable:

- `wlServerProtocol` – The communication protocol to MobileFirst Server. Either `HTTP` or `HTTPS`.
- `wlServerHost` – The hostname of the MobileFirst Server instance.
- `wlServerPort` – The port of the MobileFirst Server instance.
- `wlServerContext` – The context root path of the application on the MobileFirst Server instance.
- `languagePreference` - Sets the default language for client sdk system messages

## Tutorials to follow next
With the MobileFirst Native SDK now integrated, you can now:

- Review the [Adapters development tutorials](../../adapters/)
- Review the [Authentication and security tutorials](../../authentication-and-security/)
- Review the [Notifications tutorials](../../notifications/)
- Review [All Tutorials](../../all-tutorials)
