UnityGradle
Use Myket Maven Repository in Unity (No VPN)
This repository provides a ready‑to‑use Gradle settings file for Unity Android projects.
It helps avoid common Gradle errors caused by network restrictions by using Myket’s Maven repository.

✅ Requirements
Unity 2021.3 or newer
Android build support installed
Android Gradle Plugin 7+ / 8+
🚀 How to Use
1️⃣ Enable Custom Gradle Templates in Unity
In Unity Editor:

Edit → Project Settings → Player → Android → Publishing Settings
Enable these options:

✅ Custom Main Gradle Template
✅ Custom Launcher Gradle Template
✅ Custom Base Gradle Template
✅ Custom Gradle Properties Template
2️⃣ Add the Gradle File
Download settingsTemplate.gradle from this repository and copy it to:

Assets/Plugins/Android/settingsTemplate.gradle
If the file already exists, merge or replace it with the provided one.

3️⃣ Verify Myket Repository
Make sure this exists in settingsTemplate.gradle:

maven {
    url "https://maven.myket.ir"
}
⚠️ Do NOT remove Unity placeholders like:

**ARTIFACTORYREPOSITORY**
**INCLUDES**
4️⃣ Add Dependencies (Example)
To use a Myket SDK (example: Billing), open:

Assets/Plugins/Android/mainTemplate.gradle
Add your dependency:

dependencies {
    implementation "ir.myket:billing:1.6.2"
}
(Change the version based on Myket documentation.)

✅ Done
Build your Android project normally.
Gradle will now resolve dependencies using Myket Maven, without needing a VPN.

🙌 Thanks
Special thanks to the Myket team for providing a reliable Maven repository for Iranian developers.
