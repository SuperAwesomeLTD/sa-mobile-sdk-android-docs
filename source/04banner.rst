Banner Ads
==========

The following block of code creates and loads a banner ad:

.. code-block:: java

    public class MainActivity extends Activity {

        // define a SABannerAd
        private SABannerAd bannerAd = null;

        @Override
        protected void onCreate (Bundle savedInstanceState) {
            super.onCreate (savedInstanceState);
            setContentView (R.layout.activity_main);

            // make sure to set the application context
            // (at least once)
            SuperAwesome.getInstance ().setApplicationContext (getApplicationContext ());

            // get the banner from the layout
            bannerAd = (SABannerAd) findViewById (R.id.mybanner);

            // Enabling test mode will load
            // one of our test ads
            // By default it is disabled
            bannerAd.enableTestMode ();

            // The parental gate requires users to
            // perform a simple math operation when
            // clicking on an ad
            bannerAd.disableParentalGate ();

            // Finally you can start the loading
            // process by telling the SDK to load an
            // ad for a certain placement
            bannerAd.load (30471);
        }
    }

Once you've loaded an ad, you can also display it:

.. code-block:: java

    public void onClick (View view) {

        // It's good practice to check first
        // if there is an ad available
        if (bannerAd.hasAdAvailable ()) {

            // if all is OK you may play the ad
            bannerAd.play (MainActivity.this);
        }
    }
