Add the SDK as a JAR library
============================

If you're running an environment which does not support Gradle, then you'll need to add the SDK manually.

You can download and extract one of two zip archives:

1) `SuperAwesomeSDK-<sdk_version>.Android.full.jars.zip <https://github.com/SuperAwesomeLTD/sa-sdk-build-repo/blob/master/package/aa_android/<sdk_version>/SuperAwesomeSDK-<sdk_version>.Android.full.jars.zip?raw=true>`_

2) `SuperAwesomeSDK-<sdk_version>.Android.base.jars.zip <https://github.com/SuperAwesomeLTD/sa-sdk-build-repo/blob/master/package/aa_android/<sdk_version>/SuperAwesomeSDK-<sdk_version>.Android.base.jars.zip?raw=true>`_

Each archive will contain a number of .jar files, representing the components of the SDK that you'll need to add to the **lib** folder in your Android project.

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

    <activity android:name="tv.superawesome.sdk.publisher.SAAppWall"
              android:label="SAAppWall"
              android:theme="@android:style/Theme.Black.NoTitleBar.Fullscreen"
              android:screenOrientation="portrait"
              android:configChanges="keyboardHidden|orientation|screenSize"></activity>

    <service  android:name="tv.superawesome.lib.sanetwork.asynctask.SAAsyncTask$SAAsync"
              android:exported="false"
              android:permission="tv.superawesome.sdk.SuperAwesomeSDK"/>


This will register three new activities and one service for your application, all needed by the SDK.

Also, add the following permissions to your AndroidManifest.xml file:

.. code-block:: xml

    <uses-permission android:name="android.permission.INTERNET"/>
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />

At the end you'll also need to add **Google Play Services** as a dependency to the project, either as a .jar or through Gradle.

Once you've integrated the Android Publisher SDK, you can access all functionality by including:

.. code-block:: java

    import tv.superawesome.sdk.publisher.*;
