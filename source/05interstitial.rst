Interstitial Ads
================

The following block of code creates and loads an interstitial ad:

.. code-block:: java

    public class MainActivity extends Activity {

        @Override
        protected void onCreate (Bundle savedInstanceState) {
            super.onCreate (savedInstanceState);
            setContentView (R.layout.activity_main);

            // Enabling test mode will load
            // one of our test ads
            // By default it is disabled
            SAInterstitialAd.enableTestMode ();

            // The parental gate requires users to
            // perform a simple math operation when
            // clicking on an ad
            SAInterstitialAd.enableParentalGate ();

            // You can also specify a certain
            // orientation for your interstitial ad
            SAInterstitialAd.setOrientationPortrait ();

            // Finally you can start the loading
            // process by telling the SDK to load an
            // ad for a certain placement
            SAInterstitialAd.load (30473);
        }
    }

Once you've loaded an ad, you can also display it:

.. code-block:: java

    public void onClick (View view) {

        // It's good practice to check first
        // if there is an ad available
        if (SAInterstitialAd.hasAdAvailable (30473)) {

            // if all is OK you may play the ad
            SAInterstitialAd.play (30473, MainActivity.this);
        }
    }
