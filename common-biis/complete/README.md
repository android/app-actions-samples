# App Actions Common BII sample


## Description
This sample Android app manages items on to-do lists. Users can add items to
the to-do lists, search for items by category, and view information about
completed tasks. By implementing
[App Actions](https://developer.android.com/guide/app-actions/overview),
we allow the user to call upon our application to fulfill supported
[built-in intents (BIIs)](https://developer.android.com/reference/app-actions/built-in-intents)
in the [Common category](https://developer.android.com/reference/app-actions/built-in-intents/common).


This sample supports the following BIIs:
* `actions.intent.OPEN_APP_FEATURE`: Opens a specific feature in the app based
on the user query.
* `actions.intent.GET_THING`: Search and filter within the app using keywords.


This sample uses [Android Intents](https://developer.android.com/guide/components/intents-filters)
for fulfillment.

_Note_: This sample application is a fork of the
[Android to-do sample](https://github.com/android/architecture-samples).


![alt-text](../media/to-do-demo.gif "App Actions Demo")

## Codelab Available
For detailed instructions on using this sample, use the `starter` directory
and refer to
[Extend an Android app to Google Assistant with App Actions (Level 2)](https://codelabs.developers.google.com/codelabs/appactions-2)
codelab for instructions.

## How to use this sample
Clone or download the project to your preferred location. Then, import and modify the project with
the following steps:

1. In Android Studio, select **Open an existing Android Studio project** from the initial screen
or go to **File > Open**.
2. Select `complete/` directory 
3. Change the `applicationId` in [app/build.gradle](app/build.gradle) to the `applicationId` of
one of your draft or published apps in the Google Play Console.

    ```groovy
    android {
        defaultConfig {
            // This ID uniquely identifies your app on the device and in Google Play
            applicationId "PUT_YOUR_APPLICATION_ID_HERE"
        }
    }
    ```

4. Sync files, manually sync by going to File > Sync Project with Gradel Files
5. Change the two (2) `android:targetPackage` in
[app/src/main/res/xml/shortcuts.xml](app/src/main/res/xml/shortcuts.xml) to the `applicationId` in
6. your [app/build.gradle](app/build.gradle).

    ```xml
    <capability android:name="actions.intent.GET_THING">
        <intent
            android:targetPackage="PUT_YOUR_APPLICATION_ID_HERE"
            >
        </intent>
    </capability>
    ```

    ```xml
    <capability android:name="actions.intent.OPEN_APP_FEATURE">
        <intent
            android:targetPackage="PUT_YOUR_APPLICATION_ID_HERE"
            >
        </intent>
    </capability>
    ```

7. In Android Studio, find the root directory of the sample.
8. Select the `build.gradle` file.
9. Follow the instructions presented by the IDE.

Then, you can try the App Actions by following these steps:

1. Build and run the sample on your physical test device (**Run "app"**).
2. Open the App Actions test tool (**Tools > Google Assistant > App Actions Test Tool**).
3. Click **Create Preview**. Once your preview is created, the test tool window updates to display
information about BIIs found in your `shortcuts.xml` file.

After preview has been created:
1. Select the BII you want to test, either GET_THING or OPEN_APP_FEATURE.
2. Update parameter to relative content:
  - `GET_THING` -> `shoes`
  - `OPEN_APP_FEATURE` -> `active`
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
