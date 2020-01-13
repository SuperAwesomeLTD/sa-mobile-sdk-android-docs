Add the SDK as a JAR library
============================

If you're running an environment which does not support Gradle, then you'll need to add the SDK manually.

You can download and extract: `SuperAwesomeSDK-<sdk_version>.Android.full.jars.zip <https://github.com/SuperAwesomeLTD/sa-sdk-build-repo/blob/master/package/aa_android/<sdk_version>/SuperAwesomeSDK-<sdk_version>.Android.full.jars.zip?raw=true>`_

The archive will contain a number of .jar files, representing the components of the SDK that you'll need to add to the **lib** folder in your Android project.

Then, add the following items in your *AndroidManifest.xml* file, under the Application tag:

.. code-block:: xml

    <activity android:name="tv.superawesome.sdk.publisher.SAVideoAd"
              android:label="SAVideoAd"
              android:theme="@android:style/Theme.Black.NoTitleBar.Fullscreen"
              android:configChanges="keyboardHidden|orientation|screenSize"></activity>

    <activity android:name="tv.superawesome.sdk.publisher.SAInterstitialAd"
              android:label="SAInterstitialAd"
              android:theme="@android:style/Theme.Black.NoTitleBar.Fullscreen"
              android:configChanges="keyboardHidden|orientation|screenSize"></activity>

    <activity android:name="tv.superawesome.lib.sabumperpage.SABumperPage"
              android:label="SABumperPage"
              android:configChanges="keyboardHidden|orientation|screenSize"
              android:theme="@android:style/Theme.Holo.Dialog.NoActionBar"
              android:excludeFromRecents="true"/>

This will register three new activities and one service for your application, all needed by the SDK.

Also, add the following permissions to your AndroidManifest.xml file:

.. code-block:: xml

    <uses-permission android:name="android.permission.INTERNET"/>
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />

.. warning:: Please remember to also add **Google Play Services** and an **App Compat** library. These are needed for correct viewability metrics.

.. code-block:: shell

    dependencies {
        implementation 'com.android.support:appcompat-v7:+'
        implementation 'com.google.android.gms:play-services-ads:+'
    }

Once you've integrated the Android Publisher SDK, you can access all functionality by including:

.. code-block:: java

    import tv.superawesome.sdk.publisher.*;
