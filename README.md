SinglePrefs
===============
A small library containing a wrapper/helper for the shared preferences of Android with ability to specify default values at top level

With this library you can initialize the shared preference inside the onCreate of the Application class of your app.

```Java
public class PrefsApplication extends Application {

    @Override
    public void onCreate() {
        super.onCreate();
        // Initialize the Prefs class
        new Prefs.Builder()
                .setContext(this)
                .setMode(ContextWrapper.MODE_PRIVATE)
                .setPrefsName(getPackageName())
                .setUseDefaultSharedPreference(true)
                .setDefaultIntValue(-1)
                .setDefaultBooleanValue(false)
                .setDefaultStringValue(null)
                .build();
    }
}
```

After initialization you can use simple one line method calls like `Prefs.putString(key, string)`, `Prefs.putLong(key, long)` or `Prefs.putBoolean(key, boolean)` to save values to the Shared Preferences anywhere in your app.

Retrieving data from the Shared Preferences can be as simple as `String data = Prefs.getString(key)` now you simply get the String if the Shared Preferences contains the key or the default String value entered. So you don't use those pesky `contains()` checks or `data != null` checks.

# License
```
Copyright 2014 Pixplicity (http://pixplicity.com)

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
