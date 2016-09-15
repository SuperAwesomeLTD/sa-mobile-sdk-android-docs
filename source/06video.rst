Video Ads
=========

The following block of code creates and loads a video ad:

.. code-block:: java

    public class MainActivity extends Activity {

        @Override
        protected void onCreate(Bundle savedInstanceState) {
            super.onCreate (savedInstanceState);
            setContentView (R.layout.activity_main);

            // Enabling test mode will load
            // one of our test ads
            // By default it is disabled
            SAVideoAd.enableTestMode ();

            // The parental gate requires users to
            // perform a simple math operation when
            // clicking on an ad
            SAVideoAd.enableParentalGate ();

            // You can also specify a certain
            // orientation for your interstitial ad
            SAVideoAd.setOrientationLandscape ();

            // You can also enable or disable
            // a close button for the video
            SAVideoAd.disableCloseButton ();

            // Or you can instruct it to not close
            // at the end of the video (if you
            // want to present some kind of reward,
            // for example)
            SAVideoAd.disableCloseAtEnd ();

            // Finally you can start the loading
            // process by telling the SDK to load an
            // ad for a certain placement
            SAVideoAd.load (30479);
        }
    }

Once you've loaded an ad, you can also display it:

.. code-block:: java

    public void onClick (View view) {

        // It's good practice to check first
        // if there is an ad available
        if (SAVideoAd.hasAdAvailable (30479)) {

            // if all is OK you may play the ad
            SAVideoAd.play (30479, MainActivity.this);
        }
    }
