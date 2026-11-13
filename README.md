# Dallas

Dallas is an offline-first personal finance and small-business tracker built with Expo and React Native. It displays amounts in Kenyan shillings (KES).

## Features

- Home dashboard with current running balance and recent activity
- Income and expense records with dates, descriptions, categories and optional references
- Daily hotel sales tracker with room/table, service, payment method and M-Pesa reference fields
- Daily, weekly and monthly category budgets
- Savings goals and contributions
- Debt tracking, partial payments and payment history
- Recurring income and expense reminders with manual posting of due items
- Monthly summaries with PDF and CSV-style exports
- Custom categories
- Optional 4–6 digit PIN and device biometric unlock

## Data and privacy

Transaction and finance records are stored on the device using AsyncStorage. The optional PIN is stored using Expo SecureStore. Dallas does not currently sync data to a cloud account or connect directly to Safaricom Daraja; M-Pesa payments and receipt codes are entered manually. Keep an exported copy of important records when changing or resetting phones.

## Development

Requirements: Node.js 22, Java 17 and Android build tools (the GitHub Actions workflow installs the CI requirements).

```bash
npm install
npx expo start
```

To build a release APK locally after generating the native Android project:

```bash
npx expo prebuild --platform android
cd android
./gradlew assembleRelease
```

The GitHub Actions workflow validates the Expo Android bundle, generates the native Android project, builds the release APK and uploads it as the `Dallas-Android-APK` artifact.

## Quality notes

The CI build verifies that the JavaScript bundle exports and that the Android release build completes. This is not a substitute for testing on a physical Android device. Before production use, verify PIN and biometric behavior, data retention, exports, date handling, and all finance calculations on the target phone.
