Banner Ads
==========

The following block of code creates and loads a banner ad.

In your layout:

.. code-block:: xml

    <tv.superawesome.sdk.publisher.SABannerAd
        android:id="@+id/mybanner"
        android:layout_width="match_parent"
        android:layout_height="100dp"/>

In your activity or fragment:

.. code-block:: java

    public class MainActivity extends Activity {

        // define a SABannerAd
        private SABannerAd bannerAd = null;

        @Override
        protected void onCreate (Bundle savedInstanceState) {
            super.onCreate (savedInstanceState);
            setContentView (R.layout.activity_main);

            // get the banner from the layout
            bannerAd = (SABannerAd) findViewById (R.id.mybanner);

            // to display test ads
            bannerAd.enableTestMode ();

            // set configuration to production
            bannerAd.setConfigurationProduction ();

            // set background color as transparent
            bannerAd.setColorTransparent ();

            // start loading ad data for a placement
            bannerAd.load (30471);
        }
    }

Once you've loaded an ad, you can also display it:

.. code-block:: java

    public void onClick (View view) {

        // check if ad is loaded
        if (bannerAd.hasAdAvailable ()) {

            // display the ad
            bannerAd.play (MainActivity.this);
        }
    }

These are the default values:

============= =============
Parameter     Value
============= =============
Configuration Production
Test mode     Disabled
Background    Gray
============= =============

.. warning:: All instances of SABannerAd **must** have an Android ID assigned.
             Avoiding to correctly set one either in your XML layout or in code will cause the banner to crash with an exception.
