# Android Configuration

Icons 1- Create your app icon ic_launcher and notification icon ic_notification folders How to generate an app icon?
after you generate icons folder replace the following folders:

> `/mipmap-hdpi` in `/android/app/src/main/res/` folder
`/mipmap-mdpi` in `/android/app/src/main/res/` folder
`/mipmap-xhdpi` in `/android/app/src/main/res/` folder
`/mipmap-xxhdpi` in `/android/app/src/main/res/` folder
`/mipmap-xxxhdpi` in `/android/app/src/main/res/` folder Note:
Must rename app icon `ic_launcher` and notification icon `ic_notification`

### Get Dependencies

And just run the following command

```
flutter pub get
   ```

### Change Package Name

If you want to change the package name following the next steps

1 - Open `/android/app/build.gradle` and change the package name

```    defaultConfig {
        applicationId "<REPLACE WITH YOUR PACKAGE NAME>" // this is the package name
        minSdkVersion 22
        targetSdkVersion 20
        versionCode flutterVersionCode.toInteger()
        versionName flutterVersionName
        testInstrumentationRunner "android.support.test.runner.AndroidJUnitRunner"
    }
```

2- Open `/android/app/src/main/AndroidManifest.xml` , `/android/app/src/profil/AndroidManifest.xml`,
/android/app/src/debug/AndroidManifest.xml` and specify your:

> -YOUR PACKAGE NAME
> YOUR APPLICATION NAME
> YOUR GOOGLE MAPS KEY

### Note:

You can get the Google Maps API key at https://support.smartersvision.com/help-center/articles/7/8/15/google-maps-key
<manifest xmlns:android="http://schemas.android.com/apk/res/android"
package="<YOUR PACKAGE NAME>">

``` <uses-permission android:name="android.permission.INTERNET"/>
    <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION"/>
    <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION"/>

    <!-- io.flutter.app.FlutterApplication is an android.app.Application that
         calls FlutterMain.startInitialization(this); in its onCreate method.
         In most cases you can leave this as-is, but you if you want to provide
         additional functionality it is fine to subclass or reimplement
         FlutterApplication and put your custom class here. -->
    <application
        android:name="io.flutter.app.FlutterApplication"
        android:label="<YOUR APPLICATION NAME>"
        android:icon="@mipmap/ic_launcher">

        <meta-data android:name="com.google.android.geo.API_KEY"
                   android:value="<YOUR GOOGLE MAPS KEY>"/> 
```

3 - Open `/android/app/src/main/kotlin/`<Your Package name folders>`/MainActivity.kt` and change the package name

4- Copy the generated `google-service.json` file in `/android/app/` folder, you can see this video tutorial How to configure
push notifications?