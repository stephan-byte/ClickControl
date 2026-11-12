# ClickControl

Android-Projektarchiv und reproduzierbarer Cloud-Build.

## Quellstand

Das versionierte Archiv `ClickControl_Android_v0.1.0.zip` enthält ein Kotlin-/Gradle-Android-Projekt mit:
- `settings.gradle.kts` und `build.gradle.kts`
- `app/build.gradle.kts`
- `app/src/main/AndroidManifest.xml`
- `app/src/main/java/com/jorns/clickcontrol/MainActivity.kt`
- `gradle.properties`

Der Quellcode liegt derzeit noch im ZIP-Archiv. Die GitHub-Actions-Pipeline entpackt dieses Archiv im Build-Job; eine separate Ablage der entpackten Quellen im Repository ist als nächster Wartungsschritt vorgesehen.

## Build

Der Workflow `.github/workflows/android-build.yml`:
1. richtet Java 17 und Android SDK 35 ein,
2. entpackt das versionierte Projektarchiv,
3. führt `testDebugUnitTest` und `assembleDebug` aus,
4. stellt die Debug-APK als Actions-Artefakt bereit.

Lokal kann das Archiv mit Android Studio geöffnet oder nach dem Entpacken mit Gradle gebaut werden. Für einen lokalen Build wird Gradle passend zur Android-Gradle-Plugin-Version benötigt.

## Sicherheit und Status

- Keine Signaturschlüssel oder Zugangsdaten im Repository hinterlegen.
- Der Cloud-Build erzeugt eine Debug-APK; keine Store-Signierung oder Veröffentlichung.
- Ein erfolgreicher Build ist noch kein Nachweis für alle Geräte, Berechtigungen oder Accessibility-/Overlay-Verhaltensweisen.
