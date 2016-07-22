Integrate the SDK
=================

**Note**: This document assumes:

* an Android Studio project called **AndroidDemo**
* containing a single activity called **MainActivity**
* and a manifest file called **AndroidManifest**

Add the SDK through Gradle
^^^^^^^^^^^^^^^^^^^^^^^^^^

The simplest way of installing the AwesomeAds SDK in Android Studio is to download the AAR library through Gradle.

Add the SuperAwesome repository
-------------------------------

The first step is to include the following Maven repository in your module's **build.gradle** file (usually the file under MyApplication/app/):

.. code-block:: shell

    repositories {
        maven {
            url  'http://dl.bintray.com/gabrielcoman/maven'
        }
    }

Add the full SuperAwesome SDK
-----------------------------

Next you need to add the full SuperAwesome Android SDK as a dependency. The **full** version will contain everything you
need in order to load and display banner, interstitial and video ads as well as the 3rd party `Moat Analytics <https://moat.com/analytics>`_
module.

.. code-block:: shell

    dependencies {
        compile 'tv.superawesome.sdk:superawesome:<sdk_version_android>'
    }

Add the base SuperAwesome SDK
-----------------------------

Alternatively, if you want a base version of the SDK, you can declare the following dependency:

.. code-block:: shell

    dependencies {
        compile 'tv.superawesome.sdk:superawesome-base:<sdk_version_android>'
    }

This has the same functionality as the full version, but lacks the Moat Analytics module.

Add the SDK as a JAR library
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

If you're running an environment which does not support Gradle, then you'll need to add the SDK manually.

You can download one of two zip archives:

 * `SuperAwesomeSDK-<sdk_version_android>.Android.full.jars.zip <https://github.com/SuperAwesomeLTD/sa-sdk-build-repo/blob/master/package/SuperAwesomeSDK-<sdk_version_android>.Android.full.jars.zip?raw=true>`_
 * `SuperAwesomeSDK-<sdk_version_android>.Android.base.jars.zip <https://github.com/SuperAwesomeLTD/sa-sdk-build-repo/blob/master/package/SuperAwesomeSDK-<sdk_version_android>.Android.base.jars.zip?raw=true>`_

Once downloaded and extracted, you can follow these steps:

Add SDK components
-------------------

The archives will contain a number of .jar files, representing the components of the SDK:

 * saadloader.jar
 * sanetwork.jar
 * saevents.jar
 * sajsonparser.jar
 * samodelspace.jar
 * sasession.jar
 * sautils.jar
 * savastparser.jar
 * savideoplayer.jar
 * sawebplayer.jar
 * superawesome-<sdk_version_android>.jar

Additionally, the **full** version will also contain:

 * samoatevents.jar
 * moatlib.jar

Add them to the **lib** folder in your Android project.

Add resources
-------------

There will also be a **superawesome-res** folder containing two subfolders:

 * drawable: containing SDK PNG files; copy the PNG files inside your projects' **drawable** folder
 * layout: containing SDK layout XML files; copy the XML files inside your projects' **layout** folder

Change manifest file
--------------------

Add the following items in your *AndroidManifest.xml* file, under the Application tag:

.. code-block:: xml

    <activity android:name="tv.superawesome.sdk.views.SAFullscreenVideoAd$SAFullscreenVideoAdActivity"
              android:label="SAFullscreenVideoAd"
              android:theme="@android:style/Theme.Black.NoTitleBar.Fullscreen"></activity>

    <activity android:name="tv.superawesome.sdk.views.SAInterstitialAd$SAInterstitialAdActivity"
              android:label="SAInterstitialAd"
              android:theme="@android:style/Theme.Black.NoTitleBar.Fullscreen"
              android:configChanges="keyboardHidden|orientation|screenSize"></activity>

    <service android:name="tv.superawesome.lib.sanetwork.asynctask.SAAsyncTask$SAAsync" android:exported="false"/>

This will register two new activities and one service for your application, all needed by the SDK.

Also, add the following permissions to your AndroidManifest.xml file:

.. code-block:: xml

    <uses-permission android:name="android.permission.INTERNET"/>
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />

Extra
-----

At the end you'll also need to add Google Play Services as a dependency to the project, either as a .jar or through Gradle.
