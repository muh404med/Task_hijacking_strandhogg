# Task Hijacking (StrandHogg) PoC

This repository demonstrates the **Android Task Hijacking** vulnerability (closely related to the **StrandHogg** vulnerability). It contains two APK files designed to show how a malicious application can hijack the task of a legitimate application to display a phishing interface or steal sensitive data.

## 📂 Repository Contents

* **`SuperSecureApp.apk` (The Victim):** A vulnerable Android application configured with a weak `launchMode` and `taskAffinity`.
* **`HackedApp.apk` (The Attacker):** A Proof of Concept (PoC) malicious application designed to exploit the vulnerability in the victim app.

## ⚙️ Technical Details

The vulnerability exists because the victim application declares the following attributes in its `AndroidManifest.xml`:

```xml
<activity
    android:name=".MainActivity"
    android:launchMode="singleTask"
    android:taskAffinity="com.zombie.ssa" />
