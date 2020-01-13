Initialise the SDK
==================

The first thing you'll need to do after adding the SDK is to initialise it in a custom `Application` subclass in your Android app.

.. code-block:: java

  public class MyApplication extends Application {

    @Override
    public void onCreate() {
      super.onCreate();
      AwesomeAds.init(this, true);
    }
  }


Where the `initSDK` method takes a boolean parameter indicating whether logging is enabled or not.
For production environments logging should be off.
