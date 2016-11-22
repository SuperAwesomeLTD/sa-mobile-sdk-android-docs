App Wall
========

The following block of code creates and loads a GameWall ad:

.. code-block:: java

    public class MainActivity extends Activity {

        @Override
        protected void onCreate (Bundle savedInstanceState) {
            super.onCreate (savedInstanceState);
            setContentView (R.layout.activity_main);

            // to display test ads
            SAAppWall.enableTestMode ();

            // ask users to add two numbers when clicking on an ad
            SAAppWall.enableParentalGate ();

            // enable or disable the android back button
            SAAppWall.enableBackButton ();

            // start loading ad data for a placement
            SAAppWall.load (88888, MainActivity.this);
        }
    }

Once you've loaded an ad, you can also display it:

.. code-block:: java

    public void onClick (View view) {

        // check if ad is loaded
        if (SAAppWall.hasAdAvailable (88888)) {

            // display the ad
            SAAppWall.play (88888, MainActivity.this);
        }
    }
