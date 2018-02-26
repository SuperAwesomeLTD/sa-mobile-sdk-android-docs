Add the SDK through Gradle
==========================

The simplest way of installing the AwesomeAds SDK in Android Studio is to download the AAR library through Gradle.

The first step is to include the following Maven repository in your module's **build.gradle** file (usually the file under MyApplication/app/):

.. code-block:: shell

    repositories {
        maven {
            url  'http://dl.bintray.com/gabrielcoman/maven'
        }
    }

Next you need to add the SuperAwesome Android SDK as a dependency. This will contain everything you need in order to load and display banner, interstitial and video ads.

.. code-block:: shell

    dependencies {
        compile 'tv.superawesome.sdk:superawesome:<sdk_version>'
    }

Once you've integrated the SuperAwesome SDK, you can access all functionality by including the SuperAwesome library:

.. code-block:: java

    import tv.superawesome.*;
