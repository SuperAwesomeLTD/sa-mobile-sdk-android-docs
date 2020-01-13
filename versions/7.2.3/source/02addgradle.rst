Add the SDK through Gradle
==========================

The simplest way of adding the Android Publisher SDK to your Android Studio project is to download the AAR library through Gradle.

The first step is to include the following Maven repository in your module's **build.gradle** file (usually the file under MyApplication/app/):

.. code-block:: shell

    repositories {
        maven {
            url  'http://dl.bintray.com/gabrielcoman/maven'
        }
        maven {
           url "http://dl.bintray.com/superawesome/SuperAwesomeSDK"
        }
    }

Next you can to add the SDK as a dependency. This will contain everything you need in order to load and display banner, interstitial and video ads.

.. code-block:: shell

    dependencies {
        implementation 'tv.superawesome.sdk.publisher:superawesome:<sdk_version>'
    }


.. warning:: Please remember to also add **Google Play Services** and an **App Compat** library. These are needed for correct viewability metrics.

.. code-block:: shell

    dependencies {
        implementation 'com.android.support:appcompat-v7:+'
        implementation 'com.google.android.gms:play-services-ads:+'
    }

Once you've added the Android Publisher SDK, you can access all functionality by including:

.. code-block:: java

    import tv.superawesome.sdk.publisher.*;
