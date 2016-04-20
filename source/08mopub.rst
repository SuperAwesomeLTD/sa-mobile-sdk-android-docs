Integrate with MoPub
====================

If you already have MoPub ads serving in your app, but want to integrate SuperAwesome as well,
without having to directly use the AwesomeAds SDK, you can follow the steps below:

1) Add the SuperAwesome MoPub adapters to your app:

Download the `samopub.jar <https://github.com/SuperAwesomeLTD/sa-mobile-sdk-android-docs/raw/master/source/res/samopub.jar>`_ archive, which you'll need to add to your project, in order to add three adapters classes:

  * `SuperAwesomeBannerCustomEvent.java <https://raw.githubusercontent.com/SuperAwesomeLTD/sa-mobile-sdk-android/master/demo/samopub/src/main/java/com/mopub/sa/mobileads/SuperAwesomeBannerCustomEvent.java>`_
  * `SuperAwesomeInterstitialCustomEvent.java <https://raw.githubusercontent.com/SuperAwesomeLTD/sa-mobile-sdk-android/master/demo/samopub/src/main/java/com/mopub/sa/mobileads/SuperAwesomeInterstitialCustomEvent.java>`_
  * `SuperAwesomeRewardedVideoCustomEvent.java <https://raw.githubusercontent.com/SuperAwesomeLTD/sa-mobile-sdk-android/master/demo/samopub/src/main/java/com/mopub/sa/mobileads/SuperAwesomeRewardedVideoCustomEvent.java>`_

If you don't want to use the samopub.jar file, you can download each .java file and add it to your project individually. You'll need to place them in a folder hierarchy as **com/mopub/sa/mobileads**, inside your **/app/src/main/java** folder.

2) Setup a MoPub custom network

From your MoPub admin interface you should create a `New Network`

.. image:: img/IMG_07_MoPub_1.png

From the next menu, select `Custom Native Network`

.. image:: img/IMG_07_MoPub_2.png

You'll be taken to a new page. Here select the title of the new network

.. image:: img/IMG_07_MoPub_3.png

And assign custom inventory details for Banner, Interstitial and Video ads:

.. image:: img/IMG_07_MoPub_4.png

3) Assign custom event classes for your MoPub ads:

There are

* for Banner Ads: **com.mopub.sa.mobileads.SuperAwesomeBannerCustomEvent**
* for Interstitial Ads: **com.mopub.sa.mobileads.SuperAwesomeInterstitialCustomEvent**
* for Rewarded Video Ads: **com.mopub.sa.mobileads.SuperAwesomeRewardedVideoCustomEvent**

Notice these are identical to the names of the files you downloaded in step one.

4) Assign custom event data as JSON:

.. code-block:: shell

    {
    	"placementId": 5692,
    	"isTestEnabled": true,
    	"isParentalGateEnabled": true,
        // only for video
        "shouldShowCloseButton": false,
        "shouldAutomaticallyCloseAtEnd": true,
        "shouldLockOrientation": true,
        "lockOrientation": "LANDSCAPE" or "PORTRAIT"
    }
