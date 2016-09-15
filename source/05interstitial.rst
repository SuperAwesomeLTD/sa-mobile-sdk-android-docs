Interstitial Ads
================

The following block of code creates and loads an interstitial ad:

.. code-block:: java

    public class MainActivity extends Activity {

        @Override
        protected void onCreate (Bundle savedInstanceState) {
            super.onCreate (savedInstanceState);
            setContentView (R.layout.activity_main);

            // to display test ads
            SAInterstitialAd.enableTestMode ();

            // lock orientation to portrait or landscape
            SAInterstitialAd.setOrientationPortrait ();

            // ask users to add two numbers when clicking on an ad
            SAInterstitialAd.enableParentalGate ();

            // start loading ad data for a placement
            SAInterstitialAd.load (30473);
        }
    }

Once you've loaded an ad, you can also display it:

.. code-block:: java

    public void onClick (View view) {

        // check if ad is loaded
        if (SAInterstitialAd.hasAdAvailable (30473)) {

            // display the ad
            SAInterstitialAd.play (30473, MainActivity.this);
        }
    }
