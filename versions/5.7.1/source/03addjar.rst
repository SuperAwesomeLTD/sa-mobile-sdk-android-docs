Add the SDK as a JAR library
============================

If you're running an environment which does not support Gradle, then you'll need to add the SDK manually.

You can download one of two zip archives:

1) `SuperAwesomeSDK-<sdk_version>.Android.full.jars.zip <https://github.com/SuperAwesomeLTD/sa-sdk-build-repo/blob/master/package/aa_android/<sdk_version>/SuperAwesomeSDK-<sdk_version>.Android.full.jars.zip?raw=true>`_

2) `SuperAwesomeSDK-<sdk_version>.Android.base.jars.zip <https://github.com/SuperAwesomeLTD/sa-sdk-build-repo/blob/master/package/aa_android/<sdk_version>/SuperAwesomeSDK-<sdk_version>.Android.base.jars.zip?raw=true>`_

Once downloaded and extracted, you can follow these steps:

The archives will contain a number of .jar files, representing the components of the SDK that you'll need to add to the **lib** folder in your Android project.

Then, add the following items in your *AndroidManifest.xml* file, under the Application tag:

.. code-block:: xml

    <activity android:name="tv.superawesome.sdk.views.SAVideoAd"
              android:label="SAVideoAd"
              android:theme="@android:style/Theme.Black.NoTitleBar.Fullscreen"
              android:configChanges="keyboardHidden|orientation|screenSize"></activity>

    <activity android:name="tv.superawesome.sdk.views.SAInterstitialAd"
              android:label="SAInterstitialAd"
              android:theme="@android:style/Theme.Black.NoTitleBar.Fullscreen"
              android:configChanges="keyboardHidden|orientation|screenSize"></activity>

    <activity android:name="tv.superawesome.sdk.views.SAAppWall"
              android:label="SAAppWall"
              android:theme="@android:style/Theme.Black.NoTitleBar.Fullscreen"
              android:screenOrientation="portrait"
              android:configChanges="keyboardHidden|orientation|screenSize"></activity>

    <service  android:name="tv.superawesome.lib.sanetwork.asynctask.SAAsyncTask$SAAsync"
              android:exported="false"
              android:permission="tv.superawesome.sdk.SuperAwesomeSDK"/>

    <receiver android:name="tv.superawesome.lib.sacpi.SACPI"
              android:exported="false"
              android:permission="tv.superawesome.sdk.SuperAwesomeSDK">
              <intent-filter>
                <action android:name="com.android.vending.INSTALL_REFERRER"/>
              </intent-filter>
    </receiver>

This will register two new activities, one service and one receiver for your application, all needed by the SDK.

Also, add the following permissions to your AndroidManifest.xml file:

.. code-block:: xml

    <uses-permission android:name="android.permission.INTERNET"/>
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />

At the end you'll also need to add Google Play Services as a dependency to the project, either as a .jar or through Gradle.

Once you've integrated the SuperAwesome SDK, you can access all functionality by including the SuperAwesome library:

.. code-block:: java

    import tv.superawesome.*;
