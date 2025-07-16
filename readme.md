# ?? **Animal Company Copy Tutorial (Xera Edition)**

**Run your own Animal Company backend using PythonAnywhere + Flask.**

---

## ?? Requirements

* PC with internet
* Patched Animal Company APK
* `game-data-prod.zip` from the version you want to emulate
* A [PythonAnywhere](https://www.pythonanywhere.com/) account (free works)

---

## Step 1: Create a PythonAnywhere Flask App

1. Sign up at [pythonanywhere.com](https://www.pythonanywhere.com/).
2. After verifying your email, go to the **Dashboard**.
3. Click on **"Web"** in the top menu.
4. Click **“Add a new web app”**
5. Choose:

   * **Manual configuration**
   * **Python 3.x**
   * **Flask**
6. Once created, click into your new web app.

---

## ??? Step 2: Upload Your Files

1. Go to the **Files** tab.
2. Navigate to your `home/username/appname` directory.
3. Upload:
   * Your `game-data-prod.zip`
4. Download XeraCompany.py from this repo
5. Copy its contents into your `flask_app.py`.

---

## ?? Step 3: Set File Paths in Code

1. In `flask_app.py`, locate this line:

   ```python
   DB_PATH = "/home/XeraBackend/AnimalCompany/userdata.db"
   ```

2. Replace it with your actual user path.
   Use the **Files tab** to navigate and find your full path.
   Tip: Ctrl+F “DB\_PATH” in the file editor.

3. Do the same for this:

   ```python
   file_path = '/home/XeraBackend/ACmitm/game-data-prod.zip'
   ```

   Set it to match wherever you uploaded the zip. Usually something like:

   ```python
   file_path = '/home/yourusername/flask_app/game-data-prod.zip'
   ```

---

## ?? Step 4: Set Photon App IDs (Optional but Recommended)

1. Inside your Flask code, locate the `hi13` dictionary:

   ```python
   "photonAppID": "183b6ceb-...",
   "photonVoiceAppID": "0206e8b5-..."
   ```
2. Replace these with your own Photon Realtime and Voice App IDs from the [Photon Dashboard](https://dashboard.photonengine.com).

---

## ?? Step 5: Reload the PythonAnywhere Web App

1. Go back to the **Web** tab on PythonAnywhere.
2. Scroll down and click **Reload**.

If all went well, your backend is now live at:

```
https://yourusername.pythonanywhere.com
```

---

## ?? Step 6: Patch the Animal Company Client

1. Open your `global-metadata.dat` in **MetadataStringEditor**.
2. Ctrl+F and search for:

   ```
   https://a
   ```

   You’ll find URLs like:

   ```
   https://ac.something.nakama.io
   ```
3. Replace every instance with your PythonAnywhere URL:

   ```
   https://yourusername.pythonanywhere.com
   ```

> ?? Make sure you don’t break the length of the string — overwrite exactly.

---

## ?? Step 7: Reinstall and Sideload

1. Uninstall the original Animal Company app from your headset.
2. Sideload the patched APK (you can use SideQuest or ADB).
3. Launch the game and connect.

---

## ?? Optional: App Lab Version for Testing

If you want to upload your version to App Lab:

1. Open the APK with **UABEA**.
2. Find and open `OculusPlatformSettings.asset`.
3. Change the **AppID** to your own (you must register a new app on [developer.oculus.com](https://developer.oculus.com)).
4. Open the APK in **HxD**, search for your PythonAnywhere URL, and confirm it's embedded correctly.

---

## ? You’re Done.

Enjoy hosting your own Animal Company backend.

---

## ?? Final Notes

* This setup does not support multiplayer matchmaking out of the box.
* You can fake more storage endpoints by copying the format in `/v2/storage`.
* The webhook in the code sends logs to Discord — remove it if you don’t want that.

---

Want me to turn this into a GitHub README with file structure + download links + deploy guide? I can format that next.
