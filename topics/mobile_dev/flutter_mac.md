# Flutter SDK Installation Guide (macOS) — Non-Technical Step-by-Step

This guide will help you install Flutter on **macOS** and run your first sample app on the **iOS Simulator** or an **Android Emulator**.  
It is written for beginners, no prior coding experience required.

---

## 0. Before You Start
- A Mac running macOS (recent version recommended)
- Internet access
- About 30–60 minutes of time
- (Optional) An Apple ID (required later if you want to publish apps)

---

## 1. Install Homebrew (Package Manager)
Homebrew makes it easy to install software.

1. Open **Terminal** (Applications → Utilities → Terminal)
2. Paste this command and press **Enter**:
   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```
3. Follow prompts, enter your Mac password if asked.

To test:
```bash
brew --version
```

---

## 2. Install Flutter SDK
With Homebrew installed, run:
```bash
brew install --cask flutter
```

To confirm:
```bash
flutter --version
```

If you don’t want to use Homebrew:  
- Download Flutter ZIP for macOS from the official site  
- Extract it somewhere (e.g., `~/development/flutter`)  
- Add Flutter to PATH in your shell config (see below)

---

## 3. Add Flutter to PATH (if not using Homebrew)
1. Open Terminal
2. If you use Zsh (default on modern macOS), edit your config:
   ```bash
   nano ~/.zshrc
   ```
3. Add this line (update path if different):
   ```bash
   export PATH="$PATH:$HOME/development/flutter/bin"
   ```
4. Save (CTRL+O, Enter, CTRL+X), then reload:
   ```bash
   source ~/.zshrc
   ```
5. Test:
   ```bash
   flutter --version
   ```

---

## 4. Install Xcode (for iOS Development)
1. Open **App Store**
2. Search for **Xcode**, click **Get** to install
3. After installation, open Terminal and run:
   ```bash
   sudo xcode-select --switch /Applications/Xcode.app/Contents/Developer
   sudo xcodebuild -license
   ```
   (Read license → type `agree`)

This enables iOS builds and the **iOS Simulator**.

---

## 5. Install Android Studio (Optional but Recommended)
1. Download from: [developer.android.com/studio](https://developer.android.com/studio)
2. Open Android Studio
3. Go to **Preferences → Appearance & Behavior → System Settings → Android SDK**
   - Install at least one **SDK Platform** (e.g., Android 14)
   - Install **SDK Tools**: Build-Tools, Platform-Tools, Emulator
4. Go to **Tools → Device Manager → Create Device**
   - Choose Pixel 6 (or similar)
   - Download a system image (if needed)
   - Finish setup, then start the emulator

---

## 6. Check Setup with Flutter Doctor
Run in Terminal:
```bash
flutter doctor
```

If asked, accept Android licenses:
```bash
flutter doctor --android-licenses
```

You should see mostly green checkmarks.

---

## 7. Create and Run Sample App
1. In Terminal:
   ```bash
   cd ~
   flutter create hello_app
   cd hello_app
   ```
2. To run on iOS Simulator:
   - Open Simulator: **Spotlight → Simulator**
   - Then run:
     ```bash
     flutter run
     ```
3. To run on Android Emulator:
   - Start emulator in Android Studio Device Manager
   - Run:
     ```bash
     flutter run
     ```

---

## 8. (Optional) Install Git
Check if Git is already installed:
```bash
git --version
```
If not, install with Homebrew:
```bash
brew install git
```

---

## 9. Update Flutter Later
To get the latest stable Flutter release:
```bash
flutter upgrade
```

---

## Troubleshooting

| Issue | Fix |
|-------|-----|
| `flutter` not recognized | Add Flutter to PATH in `~/.zshrc` |
| iOS Simulator not found | Ensure Xcode is installed; open Simulator app manually |
| Emulator not listed | Start it from Android Studio Device Manager |
| Android licenses not accepted | Run `flutter doctor --android-licenses` |
| Permission denied | Add `sudo` or ensure correct folder permissions |

---

✅ You’ve now installed Flutter and run your first Flutter app on macOS!  
Next, you can open the project in **Cursor editor** or any code editor to start customizing it.
