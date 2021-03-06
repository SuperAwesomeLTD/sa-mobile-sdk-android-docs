Parental gate
=============

The Parental gate is an optional UI element you can add to your ad placements so that when a user clicks on an ad he is
presented with a popup asking him to solve a simple math sum.

Its role is to prevent very young users from simply clicking on an ad and instead ask their parents for guidance.

You can enable it like so:

.. code-block:: java

  //
  // enable Parental gate on one banner placement
  mybanner.enableParentalGate();

  //
  // enable Parental gate on all interstitial ads
  SAInterstitialAd.enableParentalGate();

  //
  // enable Parental gate on all video ads
  SAVideoAd.enableParentalGate();

The final result will look something similar to this:

.. image:: img/IMG_06_ParentalGate.png

These are the default values:

============= ========
Parameter     Value
============= ========
Parental gate Disabled
============= ========
