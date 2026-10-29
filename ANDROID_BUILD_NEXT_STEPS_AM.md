# YAYKOB ABVM EXIT MASTER — Android Build Preparation

## Added in this revision
- Capacitor Android app identity: `com.yaykob.abvmexitmaster`
- App display name: `YAYKOB ABVM EXIT MASTER`
- Improved service-worker cache version and offline app-shell fallback.

## Important status
This is still source code, not an APK. The current app depends on a Caffeine/Internet Computer backend for course data and authentication. The service worker can cache the app shell and static assets, but it does **not** make backend-dependent course content fully offline. Do not sell this build as a completed offline app yet.

## Android packaging (requires Node.js and Android build tools)
1. Install dependencies with the repository's prescribed `pnpm` workflow.
2. In `src/frontend`, add Capacitor packages compatible with the project's Node/Vite setup: `@capacitor/core`, `@capacitor/cli`, and `@capacitor/android`.
3. Build the web app so `src/frontend/dist` is generated.
4. Run Capacitor sync and add the Android platform.
5. Open the generated Android project in Android Studio and build a signed APK.
6. Before distribution, implement bundled local course data and a real activation/license backend, then test offline behavior and license expiry.

The build steps above have not been run in this environment; no APK is included in this ZIP.

## Build checker script
Run `./build-android-check.sh` on a computer that has Node.js, pnpm, Java, Android SDK, and Android Studio installed. It reports missing tools before attempting the build. This script is a helper; it does not itself produce a finished APK in an environment without those tools.
