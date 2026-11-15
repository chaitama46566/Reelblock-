# ReelBlock (Android starter project)

ReelBlock is a native Android starter app that attempts to detect likely Instagram Reels screens using Android Accessibility Services and navigate back.

## Important limitations
- Instagram does not offer a public API for selectively disabling Reels.
- Instagram's accessibility labels and layouts change frequently.
- This is a best-effort prototype, not a guaranteed blocker. The detector may miss Reels or occasionally misidentify a screen.
- The current implementation uses a conservative text heuristic and presses Android Back when it sees a likely Reel screen. It does not overlay or modify Instagram.
- It does not log in to Instagram, inspect private account data, or transmit screen text.

## Build
1. Install Android Studio (current stable) and Android SDK Platform 35.
2. Open this folder in Android Studio.
3. Allow Gradle sync to finish.
4. Select **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
5. Install the generated debug APK on your own Android device.

## Enable
1. Open ReelBlock.
2. Tap **Open Accessibility Settings**.
3. Find **ReelBlock Reels detector** and enable it.
4. Return to ReelBlock and tap **Refresh status**.
5. Open Instagram and test cautiously. Turn the switch off if normal screens are being blocked.

## Privacy
All detection runs locally. The app only reads accessibility labels from Instagram while its service is enabled. No data is sent to a server.

## Next development steps
- Test against the current Instagram version and collect false-positive/false-negative results.
- Add a user-configurable allowlist and an optional manual block screen.
- Add PIN protection using Android's secure local credential APIs.
- Add a persistent notification explaining when the accessibility service is active.
