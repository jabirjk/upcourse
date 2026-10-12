# Upcourses

Upcourses is a Flutter learning app for browsing courses, watching lessons, tracking learning progress, and earning certificates. The app uses Firebase services for authentication, data, storage, analytics, and messaging.

## Requirements

- Flutter SDK compatible with Dart `^3.11.0`
- Android Studio and/or Xcode for the mobile platforms
- A Firebase project configured for the platforms you plan to run

## Run locally

```bash
flutter pub get
flutter run
```

Run the automated tests with:

```bash
flutter test
```

## Firebase setup

The checked-in Firebase client configuration is for the original Upcourses Firebase project. To use a different project:

1. Create a Firebase project and register each app platform with the correct application ID or bundle ID.
2. Run `flutterfire configure` to regenerate `lib/firebase_options.dart`.
3. Replace the platform configuration files as needed, such as Android's `android/app/google-services.json` and iOS's `ios/Runner/GoogleService-Info.plist`.
4. Review `database.rules.json`, `firestore.rules`, and `storage.rules` before deploying any rules. Set up your Firebase CLI project locally with `firebase use --add`; no default Firebase project is configured in this copy.

Firebase client API keys and app IDs identify the project; they are not server credentials. Restrict API keys appropriately and secure data with Firebase Security Rules and App Check. Never commit service-account credentials or private signing keys.

## Gemini API configuration

The app has a built-in assistant fallback when no Gemini API key is configured. A key can be supplied for local testing with `--dart-define=GEMINI_API_KEY=...`, but compile-time values are bundled into the app and are not secret. Do not publish a Gemini key in this repository or expose it through client-readable Remote Config. For production, call Gemini through a trusted backend that keeps the key server-side.

## GitHub notes

Generated build output, local machine settings, signing material, and service-account credentials are excluded by `.gitignore`. Before making the repository public, review all Firebase rules and platform client configuration for your intended release.
