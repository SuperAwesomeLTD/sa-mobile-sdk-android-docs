Add the SDK through Gradle
==========================

The simplest way of adding the Android Publisher SDK to your Android Studio project is to download the AAR library through Gradle.

The first step is to include the following Maven repository in your module's **build.gradle** file (usually the file under MyApplication/app/):

.. code-block:: shell

    repositories {
        maven {
            url  'http://dl.bintray.com/gabrielcoman/maven'
        }
    }

Next you can to add the full SDK as a dependency. The **full** version will contain everything you
need in order to load and display banner, interstitial and video ads as well as the 3rd party `Moat Analytics <https://moat.com/analytics>`_
module.

.. code-block:: shell

    dependencies {
        compile 'tv.superawesome.sdk.publisher:superawesome:<sdk_version>'
    }

Alternatively, if you want a base version of the SDK, you can declare the following dependency:

.. code-block:: shell

    dependencies {
        compile 'tv.superawesome.sdk.publisher:superawesome-base:<sdk_version>'
    }

This has the same functionality as the full version, but lacks the Moat Analytics module.

Once you've added the Android Publisher SDK, you can access all functionality by including:

.. code-block:: java

    import tv.superawesome.sdk.publisher.*;
