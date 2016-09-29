Game Wall
=========

The following block of code creates and loads a GameWall ad:

.. code-block:: java

    public class MainActivity extends Activity {

        @Override
        protected void onCreate (Bundle savedInstanceState) {
            super.onCreate (savedInstanceState);
            setContentView (R.layout.activity_main);

            // to display test ads
            SAGameWall.enableTestMode ();

            // ask users to add two numbers when clicking on an ad
            SAGameWall.enableParentalGate ();

            // start loading ad data for a placement
            SAGameWall.load (88888, MainActivity.this);
        }
    }

Once you've loaded an ad, you can also display it:

.. code-block:: java

    public void onClick (View view) {

        // check if ad is loaded
        if (SAGameWall.hasAdAvailable (88888)) {

            // display the ad
            SAGameWall.play (88888, MainActivity.this);
        }
    }
