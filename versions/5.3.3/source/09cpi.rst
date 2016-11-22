Handle CPI
==========

You can install and use the SuperAwesome SDK as an advertiser as well, if you want to measure your CPI (Cost per Install)
performance.

All you have to do is make sure that the following receiver is registered in your ApplicationManifest.xml file (and it should be automatically added by the
SuperAwesome SDK when you build to Android):

.. code-block:: shell

    <receiver android:name="tv.superawesome.sdk.cpi.SACPI" android:exported="true">
        <intent-filter><action android:name="com.android.vending.INSTALL_REFERRER"/></intent-filter>
    </receiver>
