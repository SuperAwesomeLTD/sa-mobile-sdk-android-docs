Configure the SDK
=================

Once you've integrated the SuperAwesome SDK, you can access all functionality by including the SuperAwesome library:

.. code-block:: java

    import tv.superawesome.*;


You also have to make sure you call this at least once:

.. code-block:: java

    SuperAwesome.getInstance().setApplicationContext(getApplicationContext());
