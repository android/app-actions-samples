# App Actions Fitness BII sample

## Description 
This is a sample Fitness application that allows displaying workout information as well as starting
and stopping a workout. By implementing [App Actions](https://developer.android.com/guide/app-actions/overview),
we allow the user to call upon our application to fulfill supported
[built-in intents (BIIs)](https://developer.android.com/reference/app-actions/built-in-intents) in the
[fitness category](https://developer.android.com/reference/app-actions/built-in-intents/health-and-fitness).


This sample supports the following BIIs:
* `actions.intent.START_EXERCISE`: Open the app and start an exercise session.
* `actions.intent.STOP_EXERCISE`: Open the app and stops the current exercise session.


This sample uses [Andriod Intents](https://developer.android.com/guide/components/intents-filters) for fulfillment.

_Note_: This sample application is a fork of the [Android to-do sample](https://github.com/android/architecture-samples).


![alt-text](media/demo.gif "App Actions Demo")

## Codelab Available
For detailed instructions on using this sample, use the `starter` directory
and refer to
[Extend an Android app to Google Assistant with App Actions](https://codelabs.developers.google.com/codelabs/appactions) codelab.

## How to use this sample

Clone or download the project to your preferred location. Then, import the project and modify the project with the following steps:

1. In Android Studio, select **Open an existing Android Studio project** from the initial screen
or go to **File > Open**.
2. Select `complete/` directory
3. Change the `applicationId` in [app/build.gradle](app/build.gradle) to the `applicationId` of one of your draft or published apps in the Google Play Console.

    ```groovy
    android {
        defaultConfig {
            // This ID uniquely identifies your app on the device and in Google Play
            applicationId "PUT_YOUR_APPLICATION_ID_HERE"
        }
    }
    ```
4. Sync files, manually sync by going to File > Sync Project with Gradel Files.
5. Change the two (2) `android:targetPackage` in [app/src/main/res/xml/shortcuts.xml](app/src/main/res/xml/shortcuts.xml) to the `applicationId` in your [app/build.gradle](app/build.gradle).

    ```xml
    <capability android:name="actions.intent.START_EXERCISE">
        <intent
            android:targetPackage="PUT_YOUR_APPLICATION_ID_HERE"
            >
        </intent>
    </capability>
    ```

    ```xml
    <capability android:name="actions.intent.STOP_EXERCISE">
        <intent
            android:targetPackage="PUT_YOUR_APPLICATION_ID_HERE"
            >
        </intent>
    </capability>
    ```

6. In Android Studio, find the root directory of the sample.
7. Select the `build.gradle` file.
8. Follow the instructions presented by the IDE.
9. Install [Google Assistant plugin for Android Studio](https://developer.android.com/guide/app-actions/test-tool)


Then, you can try the App Actions by following these steps:

1. Build and run the sample on your physical test device (**Run "app"**).
2. Open the App Actions test tool (**Tools > Google Assistant > App Actions Test Tool**).
3. Click **Create Preview**. Once your preview is created, the test tool window updates to display
information about BIIs found in your `shortcuts.xml` file.

After preview has been created:
1. Select the START_EXERCISE BII to test.
2. Update parameter to relative content.
  - `Running`
  - `Hiking`
  - `Biking`
3. Click on **Run App Actions**.


## Contribution guidelines

If you want to contribute to this project, be sure to review the
[contribution guidelines](CONTRIBUTING.md).

We use [GitHub issues](https://github.com/android/app-actions-samples/issues) for
tracking requests and bugs, please get support by posting your technical questions to
[Stack Overflow](https://stackoverflow.com/questions/tagged/app-actions).

Report [general issues with App Actions features](https://issuetracker.google.com/issues/new?component=617864&template=1257475)
or [make suggestions for additional built-in intents](https://issuetracker.google.com/issues/new?component=617864&template=1261453)
through our public issue tracker.

## Resources

* [App Actions Overview](https://developer.android.com/guide/app-actions/overview)
* [Built-in Intents reference](https://developer.android.com/reference/app-actions/built-in-intents)
* [App Actions Test Tool](https://developer.android.com/guide/app-actions/test-tool)
* [Codelab](https://developers.google.com/assistant/app/codelabs)
* [Other samples](https://developers.google.com/assistant/app/samples)

## License
```
Copyright 2022 Google LLC

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   https://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
