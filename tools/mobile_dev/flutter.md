# Flutter SDK Installation Guide (Windows) — Non-Technical Step-by-Step

This guide will help you install Flutter on **Windows** and run your first sample app on an **Android Emulator**.  
It is written for beginners, no prior coding experience required.

---

## 0. Before You Start
- A Windows 10/11 laptop with ~10 GB free space
- Internet access
- About 30–60 minutes of time

---

## 1. Create a Folder for Flutter
1. Open **File Explorer**
2. Go to **This PC → Local Disk (C:)**
3. Right-click → **New → Folder**
4. Name it: `src`  
   (Full path will be `C:\src`)

> Why? Flutter works best in a short, simple folder path without spaces.

---

## 2. Download Flutter SDK
1. Open your browser and search: **Flutter SDK Windows download**
2. On the official Flutter site, download the **Windows stable** ZIP file
3. After it downloads, **Right-click → Extract All…**
4. Choose folder **`C:\src`**  
   You should now have: `C:\src\flutter\`

---

## 3. Add Flutter to PATH (So Windows Can Find It)
1. Press **Start**, type: `environment variables`
2. Click: **Edit the system environment variables**
3. In the window, click: **Environment Variables…**
4. Under **User variables**, find **Path** → **Edit**
5. Click **New**, paste:
   ```
   C:\src\flutter\bin
   ```
6. Click **OK** on all windows

---

## 4. Test Flutter Command
1. Press **Start**, open **Windows Terminal** (or **PowerShell**)
2. Type:
   ```
   flutter --version
   ```
3. If you see a version number, Flutter is installed!

---

## 5. Install Android Studio (for Emulator & Tools)
1. Search **Download Android Studio**, install with defaults
2. Open Android Studio
3. Go to **More Actions → SDK Manager**
   - **SDK Platforms tab**: check at least one version (e.g., Android 14)
   - **SDK Tools tab**: ensure these are checked:
     - Android SDK Build-Tools  
     - Android SDK Platform-Tools  
     - Android Emulator
4. Apply & install updates

---

## 6. Create an Android Emulator
1. In Android Studio → **Device Manager**
2. Click **Create Device**
3. Pick a phone (e.g., Pixel 6)
4. Choose a system image (download if needed)
5. Finish setup
6. In Device Manager, click **▶ (Play)** to start the emulator  
   → You will see a virtual Android phone appear!

---

## 7. Check Setup with Flutter Doctor
1. Open **Windows Terminal**
2. Type:
   ```
   flutter doctor
   ```
3. Accept Android licenses if asked:
   ```
   flutter doctor --android-licenses
   ```

Keep running until you mostly see green checkmarks.

---

## 8. (Optional) Install Git
- Download **Git for Windows** and install with defaults  
- Check by typing:
  ```
  git --version
  ```

---

## 9. Create and Run Sample Flutter App
1. In your terminal, type:
   ```
   cd %USERPROFILE%
   flutter create hello_app
   cd hello_app
   ```
2. Make sure your Android emulator is running (from Step 6)
3. Run:
   ```
   flutter run
   ```
4. A sample Flutter app should launch on the emulator!  
   Try tapping the **+** button — the counter increases.

---

## 10. Update Flutter Later
To update to the newest version, type:
```bash
flutter upgrade
```

---

## Troubleshooting

| Issue | Fix |
|-------|-----|
| `flutter` not recognized | Check PATH includes `C:\src\flutter\bin` |
| Emulator not listed | Ensure it’s **running** in Android Studio Device Manager |
| Asked for Android licenses | Run `flutter doctor --android-licenses` |
| Very slow emulator | Use lightweight device image, enable hardware acceleration (Intel HAXM/Hyper-V) |

---

✅ You’ve now installed Flutter and run your very first Flutter app!  
Next, you can open the project in **Cursor editor** or any code editor to start customizing it.
