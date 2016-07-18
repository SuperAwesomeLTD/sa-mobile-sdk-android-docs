Integrate the SDK
=================

**Note**: This document assumes:

* an Android Studio project called **AndroidDemo**
* containing a single activity called **MainActivity**
* and a manifest file called **AndroidManifest**

Add the SDK through Gradle
^^^^^^^^^^^^^^^^^^^^^^^^^^

The simplest way of installing the AwesomeAds SDK in Android Studio is to download the AAR library through Gradle.

Just include the following in your module's **build.gradle** file (usually the file under MyApplication/app/):

.. code-block:: shell

    repositories {
        maven {
            url  "http://dl.bintray.com/gabrielcoman/maven"
        }
    }

    dependencies {
        compile 'tv.superawesome.sdk:sa-sdk:<sdk_version_android>'
    }

Add the SDK as a JAR library
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

If you're running an environment which does not support Gradle, then you'll need to add the SDK manually.


1) Download the following jar files:

 * `saadloader.jar <https://github.com/SuperAwesomeLTD/sa-sdk-build-repo/blob/master/android_build/saadloader.jar?raw=true>`_
 * `sanetwork.jar <https://github.com/SuperAwesomeLTD/sa-sdk-build-repo/blob/master/android_build/sanetwork.jar?raw=true>`_
 * `saevents.jar <https://github.com/SuperAwesomeLTD/sa-sdk-build-repo/blob/master/android_build/saevents.jar?raw=true>`_
 * `sajsonparser.jar <https://github.com/SuperAwesomeLTD/sa-sdk-build-repo/blob/master/android_build/sajsonparser.jar?raw=true>`_
 * `samodelspace.jar <https://github.com/SuperAwesomeLTD/sa-sdk-build-repo/blob/master/android_build/samodelspace.jar?raw=true>`_
 * `sasession.jar <https://github.com/SuperAwesomeLTD/sa-sdk-build-repo/blob/master/android_build/sasession.jar?raw=true>`_
 * `sautils.jar <https://github.com/SuperAwesomeLTD/sa-sdk-build-repo/blob/master/android_build/sautils.jar?raw=true>`_
 * `savastparser.jar <https://github.com/SuperAwesomeLTD/sa-sdk-build-repo/blob/master/android_build/savastparser.jar?raw=true>`_
 * `savideoplayer.jar <https://github.com/SuperAwesomeLTD/sa-sdk-build-repo/blob/master/android_build/savideoplayer.jar?raw=true>`_
 * `sawebplayer.jar <https://github.com/SuperAwesomeLTD/sa-sdk-build-repo/blob/master/android_build/sawebplayer.jar?raw=true>`_
 * `sa-sdk-<sdk_version_android>.jar <https://github.com/SuperAwesomeLTD/sa-sdk-build-repo/blob/master/android_build/sa-sdk-<sdk_version_android>.jar?raw=true>`_

And add them as library dependencies in your Android Studio or Eclipse project.

2) Download `sa-sdk-res.zip <https://github.com/SuperAwesomeLTD/sa-sdk-build-repo/blob/master/android_build/sa-sdk-res.zip?raw=true>`_ and unzip it.

You'll find two folders inside:

* drawable: containing SDK PNG files; copy the PNG files inside your projects' **drawable** folder
* layout: containing SDK layout XML files; copy the XML files inside your projects' **layout** folder

3) Add the following items in your AndroidManifest file, under the Application tag:

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

4) Add the following permissions to your AndroidManifest.xml file:

.. code-block:: xml

    <uses-permission android:name="android.permission.INTERNET"/>
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />

5) At the end you'll also need to add Google Play Services as a dependency to the project, either as a JAR or through Gradle.
