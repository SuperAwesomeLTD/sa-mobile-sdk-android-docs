Video Ads
=========

The following block of code creates and loads a video ad:

.. code-block:: java

    public class MainActivity extends Activity {

        @Override
        protected void onCreate(Bundle savedInstanceState) {
            super.onCreate (savedInstanceState);
            setContentView (R.layout.activity_main);

            // to display test ads
            SAVideoAd.enableTestMode ();

            // ask users to add two numbers when clicking on an ad
            SAVideoAd.enableParentalGate ();

            // lock orientation to portrait or landscape
            SAVideoAd.setOrientationLandscape ();

            // enable or disable the android back button
            SAVideoAd.enableBackButton ();

            // enable or disable a close button
            SAVideoAd.enableCloseButton ();

            // enable or disable auto-closing at the end
            SAVideoAd.disableCloseAtEnd ();

            // start loading ad data for a placement
            SAVideoAd.load (30479, MainActivity.this);
        }
    }

Once you've loaded an ad, you can also display it:

.. code-block:: java

    public void onClick (View view) {

        // check if ad is loaded
        if (SAVideoAd.hasAdAvailable (30479)) {

            // display the ad
            SAVideoAd.play (30479, MainActivity.this);
        }
    }

.. note:: Video ads won't show a close button by default. However, for ads that are longer than 15 seconds, the close button will appear automatically at the 15 second mark.
