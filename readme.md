
# How to Clone OG Animal Company (Xera Company SDK 1.0)

Build your own version of Animal Company using the XeraCompanySDK
```
CREDITS:

0x11/Xera - Developer and server hoster

Drycheetah - Person who gave me the request logs to be able to recreate the nakama backend
```
---

## 1. ?? Install the Base APK

Download either:

* `0.14.4.apk`
* `Office Update.apk`

Both are available in the `/APKS` folder. Install or prep for decompilation.

---

## 2. ?? Decompile the APK

Use [APKTool](https://github.com/AndnixSH/APKToolGUI) or similar:


---

## 3. ?? Patch the Server URL

* Open `global-metadata.dat` in [MetadataStringEditor](https://github.com/JeremieCHN/MetaDataStringEditor)
* Ctrl+F and search:

  ```
  https://animalcompany.us-east1.nakamacloud.io
  ```
* Replace with:

  ```
  https://ac-xerabackend.pythonanywhere.com
  ```

---

## 4. ?? Inject Your App ID

* Open `assets/bin/data/globalgamemanagers` in **UABEA**
* Ctrl+F `OculusPlatformSettings`
* Click ? **Extract as raw**
* Open that `.dat` file in **HxD**
* Replace the embedded Meta App ID with your own
  (from [developer.oculus.com](https://developer.oculus.com))

---

## 5. ??? Rebrand the Package

Change:

```
woosterGames.animalCompany
```

to your own namespace in:

* `AndroidManifest.xml` + `apktool.yml`

---

## 6. ?? Upload to Meta

* Sign in to your Oculus developer account
* Build and sign your APK
* Upload it to Quest Store

#  #STOPKILLINGGAMES
