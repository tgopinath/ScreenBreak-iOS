# Screen Break for iPhone

A native SwiftUI shell (WKWebView, iOS 17+) around the live web app at https://screen-break-nine.vercel.app, generated from the
[Kolam iOS shell template](https://github.com/tgopinath/kolam-design-system/tree/main/ios/shell-template).
Inside this app the page switches to Apple's Human Interface Guidelines look (Kolam iOS kit: large titles,
Liquid Glass tab bar, back + inline title, haptics); in Safari or any other browser it keeps its own web look.
Web app source: https://github.com/tgopinath/screen-break

<img src="screenshots/today.jpg" width="200" alt="Today"> <img src="screenshots/stats.jpg" width="200" alt="Statistics"> <img src="screenshots/settings.jpg" width="200" alt="Settings">

Break reminders use in-app prompts and sounds inside the shell (WKWebView has no web notifications); the macOS/Windows desktop app in the web repo has native notifications.

## Run it

```sh
xcodebuild -project ScreenBreak.xcodeproj -scheme ScreenBreak \
  -destination 'platform=iOS Simulator,name=iPhone 17 Pro' -derivedDataPath build CODE_SIGNING_ALLOWED=NO build
```

Then install `build/Build/Products/Debug-iphonesimulator/ScreenBreak.app` with `xcrun simctl install booted …`.
Debug builds accept `-KolamStartURL "<url>"` (open another route) and `-KolamJS "<line>"` (run one line of
JavaScript after the first load) on `simctl launch`, for screenshots.
Installing on other people's iPhones needs TestFlight or the App Store (Apple Developer Program).
