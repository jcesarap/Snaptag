# SNAPTAG

* `/app` - To change look, feel and operations.
  * `app/src/` Source code and resources
  * `src/main/java` file-browsing logic or UI handling.
  * `src/main/res/` 
    * `layout/` for screen designs
    * `values/strings.xml` for text
  * `app/build.gradle` if you need adding new libraries or change version number.
* `/art`
  * Changing app icons, folder icons...
* Build and project configuration
  * `settings.gradle`: Tells Gradle which modules to include in the project (in this case, just `:app`).
  * `build.gradle` (root): Sets up build plugins and tools that apply globally across the whole project.
  * `gradle.properties`: Configuration tweaks for the build engine (like allocating RAM to the compiler).
  * `signing.gradle` & `signing.properties.example`: Controls how the final app is cryptographically signed so it can be installed on a phone or uploaded to an app store. To sign your own builds, you would copy the example file to `signing.properties` and fill in your private key details.
  * `gradlew` & `gradlew.bat`: Scripts used to build the app from a terminal (e.g., running `./gradlew assembleDebug` to build a test APK) without needing Android Studio open.

* Utilities
  * `/mime`: A file manager needs to know that a `.mp4` is a video and a `.pdf` is a document. This folder handles custom MIME type mappings that standard Android might miss.
    * *To change:* If you want the app to recognize a new, rare file extension, you would add it to `android.extensions` and run `generate-code.sh` to update `MimeTypeMapCompat.kt`.
* `/utils`: Maintenance tools for the developer.
* `import-translations.sh`: Used by the developer to pull in crowd-sourced translations from platforms like Crowdin.
* `generate-custom-themes.sh`: Automates the creation of the various Material Design color palettes used across the app.
* `/fastlane`: Automation metadata. This allows the developer to automatically upload app screenshots, release notes, and final APK packages directly to F-Droid or the Google Play Store with a single command.

## Pending

* `Please avoid conflict with the Play/F-Droid version of this app. App stores cannot update apps signed with a different certificate, so you can either ship an APK that's signed by me (or F-Droid) so that users will be able to update it on Play/F-Droid, or fork this project and rename the package name when you need to sign the APK with a different certificate and potentially making other changes.` 

## License

    Copyright (C) 2018 Hai Zhang

    This program is free software: you can redistribute it and/or modify
    it under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    This program is distributed in the hope that it will be useful,
    but WITHOUT ANY WARRANTY; without even the implied warranty of
    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
    GNU General Public License for more details.

    You should have received a copy of the GNU General Public License
    along with this program.  If not, see <https://www.gnu.org/licenses/>.
