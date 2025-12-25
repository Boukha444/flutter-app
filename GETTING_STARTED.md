# Getting Started with ISMAGI Shop Flutter Application

Welcome to the ISMAGI Shop Flutter application! This guide will help you set up your development environment, run the application, and understand the project structure.

## Table of Contents
- [Prerequisites](#prerequisites)
- [Setup Instructions](#setup-instructions)
- [Running the App](#running-the-app)
- [App Features Overview](#app-features-overview)
- [Theme Information](#theme-information)
- [Common Tasks](#common-tasks)
- [Troubleshooting](#troubleshooting)
- [Project Structure](#project-structure)
- [Learning Resources](#learning-resources)
- [Development Tips](#development-tips)
- [Getting Started Checklist](#getting-started-checklist)

## Prerequisites

Before you begin, ensure you have the following installed on your system:

- **Flutter SDK** (version 3.0 or higher)
  - Download from [flutter.dev](https://flutter.dev)
  - Ensure the `flutter` and `dart` commands are available in your PATH

- **Dart SDK** (typically bundled with Flutter)
  - Version 3.0 or higher

- **IDE/Editor**
  - Android Studio (recommended) with Flutter and Dart plugins
  - OR Visual Studio Code with Flutter and Dart extensions

- **Platform-Specific Requirements**
  - **Android**: Android SDK 21 or higher, Android Studio
  - **iOS**: Xcode 12 or higher, macOS 10.15+
  - **Web**: Modern web browser

- **Git** for version control

- **Device or Emulator**
  - Android Emulator or physical Android device
  - iOS Simulator or physical iOS device (macOS only)
  - Web browser for web platform

## Setup Instructions

### 1. Clone the Repository

```bash
git clone https://github.com/Boukha444/flutter-app.git
cd flutter-app
```

### 2. Get Flutter and Dart SDKs

Verify installations:
```bash
flutter doctor
```

This command checks your environment and displays a report. Ensure all required components are installed.

### 3. Install Dependencies

```bash
flutter pub get
```

This command downloads all the packages listed in `pubspec.yaml`.

### 4. Configure Platform-Specific Setup

#### Android Setup
```bash
cd android
./gradlew clean
cd ..
```

#### iOS Setup (macOS only)
```bash
cd ios
pod deintegrate
pod install
cd ..
```

#### Web Setup
No additional setup required beyond `flutter pub get`.

### 5. Generate Code (if necessary)

If the project uses code generation (e.g., Freezed, Riverpod):
```bash
flutter pub run build_runner build --delete-conflicting-outputs
```

## Running the App

### Run on Android Emulator/Device
```bash
flutter run
```

Or specify a device:
```bash
flutter run -d <device-id>
```

### Run on iOS Simulator/Device
```bash
flutter run -d <device-id>
```

### Run on Web
```bash
flutter run -d chrome
```

Or Firefox:
```bash
flutter run -d firefox
```

### Run in Release Mode
```bash
flutter run --release
```

### Run with Specific Build Flavor (if configured)
```bash
flutter run --flavor dev -t lib/main_dev.dart
flutter run --flavor prod -t lib/main.dart
```

## App Features Overview

### Core Features
- **Product Catalog**: Browse and search products with detailed information
- **Shopping Cart**: Add, remove, and manage items in your cart
- **User Authentication**: Login and register with secure authentication
- **Order Management**: View order history and track orders
- **User Profile**: Manage personal information and preferences
- **Wishlist**: Save favorite products for later
- **Payment Integration**: Secure checkout with multiple payment options
- **Notifications**: Real-time order updates and promotions

### Additional Features
- **Product Reviews**: Read and write product reviews
- **Filters & Sorting**: Advanced product filtering and sorting options
- **Multi-language Support**: Support for multiple languages
- **Dark Mode**: Theme customization options
- **Responsive Design**: Works seamlessly on phones, tablets, and web

## Theme Information

### Supported Themes
The application supports both light and dark themes:

#### Light Theme
- Primary Color: Defined in `lib/theme/light_theme.dart`
- Clean, bright interface for daytime usage
- High contrast for readability

#### Dark Theme
- Primary Color: Defined in `lib/theme/dark_theme.dart`
- Easy on the eyes for low-light environments
- Reduced blue light emission

### Customizing Themes

1. Navigate to `lib/theme/` directory
2. Edit `light_theme.dart` or `dark_theme.dart`
3. Modify colors, typography, and component styles
4. Restart the app to see changes:
   ```bash
   flutter run --full-restart
   ```

### Theme Configuration
- Theme colors are centralized in theme files
- Material Design 3 principles are followed
- Dynamic color support for Android 12+

## Common Tasks

### Adding a New Page
1. Create a new file in `lib/screens/`
2. Create a `StatelessWidget` or `StatefulWidget`
3. Add route in `lib/routes/app_routes.dart`
4. Update navigation code

### Adding a New Dependency
```bash
flutter pub add package_name
```

To add a dev dependency:
```bash
flutter pub add --dev package_name
```

### Building APK (Android)
```bash
flutter build apk --release
```

Output: `build/app/outputs/flutter-app.apk`

### Building AppBundle (Android)
```bash
flutter build appbundle --release
```

### Building iOS App
```bash
flutter build ios --release
```

### Building Web
```bash
flutter build web --release
```

### Running Tests
```bash
flutter test
```

Run tests with coverage:
```bash
flutter test --coverage
```

### Formatting and Linting
Format code:
```bash
dart format lib/
```

Check for lint issues:
```bash
flutter analyze
```

## Troubleshooting

### Common Issues and Solutions

#### Issue: "flutter: command not found"
**Solution**: Add Flutter to your PATH
- Windows: Add `C:\flutter\bin` to System Environment Variables
- macOS/Linux: Add `export PATH="$PATH:~/flutter/bin"` to `~/.bashrc` or `~/.zshrc`

#### Issue: "No connected devices"
**Solution**: 
- Enable USB debugging on Android device
- Run `flutter devices` to list available devices
- Start an Android Emulator or iOS Simulator

#### Issue: Build fails with "Gradle build failed"
**Solution**:
```bash
cd android
./gradlew clean
cd ..
flutter pub get
flutter run
```

#### Issue: iOS build fails with "Pod install error"
**Solution**:
```bash
cd ios
rm -rf Pods
rm Podfile.lock
pod install
cd ..
flutter run
```

#### Issue: "Version conflict" in pub get
**Solution**: Update dependencies to compatible versions
```bash
flutter pub upgrade
```

#### Issue: Web build not loading resources
**Solution**: Clear build cache
```bash
flutter clean
flutter pub get
flutter run -d chrome
```

#### Issue: Hot reload not working
**Solution**: Full restart the app
```bash
flutter run --full-restart
```

### Getting Help
- Check `flutter doctor` output for specific issues
- Review logs: `flutter run -v`
- Check package documentation for dependency issues
- Visit [Flutter Documentation](https://flutter.dev/docs)

## Project Structure

```
flutter-app/
├── lib/
│   ├── main.dart                 # Application entry point
│   ├── config/                   # Configuration files
│   │   ├── app_config.dart
│   │   └── constants.dart
│   ├── models/                   # Data models
│   │   ├── product_model.dart
│   │   ├── user_model.dart
│   │   └── order_model.dart
│   ├── screens/                  # UI screens/pages
│   │   ├── home_screen.dart
│   │   ├── product_detail_screen.dart
│   │   ├── cart_screen.dart
│   │   ├── checkout_screen.dart
│   │   ├── auth_screen.dart
│   │   └── profile_screen.dart
│   ├── widgets/                  # Reusable widgets
│   │   ├── product_card.dart
│   │   ├── custom_app_bar.dart
│   │   ├── bottom_nav_bar.dart
│   │   └── custom_button.dart
│   ├── services/                 # Business logic & API calls
│   │   ├── api_service.dart
│   │   ├── auth_service.dart
│   │   ├── product_service.dart
│   │   └── cart_service.dart
│   ├── providers/                # State management (Riverpod/Provider)
│   │   ├── auth_provider.dart
│   │   ├── product_provider.dart
│   │   └── cart_provider.dart
│   ├── routes/                   # Navigation routes
│   │   └── app_routes.dart
│   ├── theme/                    # Theme configuration
│   │   ├── light_theme.dart
│   │   ├── dark_theme.dart
│   │   └── app_colors.dart
│   └── utils/                    # Utility functions
│       ├── validators.dart
│       ├── formatters.dart
│       └── helpers.dart
├── assets/                       # Images, fonts, etc.
│   ├── images/
│   ├── icons/
│   └── fonts/
├── test/                         # Unit and widget tests
│   ├── widget_test.dart
│   └── unit_test/
├── pubspec.yaml                  # Dependencies and metadata
├── pubspec.lock                  # Locked dependency versions
├── analysis_options.yaml         # Lint rules
├── README.md                     # Project overview
└── GETTING_STARTED.md           # This file

```

## Learning Resources

### Official Documentation
- [Flutter Official Documentation](https://flutter.dev/docs)
- [Dart Language Guide](https://dart.dev/guides)
- [Flutter Cookbook](https://flutter.dev/docs/cookbook)

### State Management
- [Provider Package](https://pub.dev/packages/provider)
- [Riverpod Documentation](https://riverpod.dev)
- [GetX Documentation](https://github.com/jonataslaw/getx)

### API Integration
- [Dio Package](https://pub.dev/packages/dio) - HTTP client
- [JSON Serialization](https://flutter.dev/docs/development/data-and-backend/json)

### UI/UX
- [Material Design 3](https://m3.material.io)
- [Flutter Pub - UI Packages](https://pub.dev/flutter/packages?q=ui)

### Testing
- [Flutter Testing Guide](https://flutter.dev/docs/testing)
- [Integration Testing](https://flutter.dev/docs/testing/integration-tests)

### Community
- [Flutter Community on GitHub](https://github.com/fluttercommunity)
- [Stack Overflow - Flutter Tag](https://stackoverflow.com/questions/tagged/flutter)
- [Reddit - r/FlutterDev](https://www.reddit.com/r/FlutterDev/)

## Development Tips

### 1. Use Hot Reload for Faster Development
Press `r` in the terminal while `flutter run` is active to hot reload changes without restarting the app.

### 2. Organize Your Code
- Keep related widgets together
- Create separate files for each screen
- Use meaningful file and variable names

### 3. Follow Dart Style Guidelines
```bash
dart format lib/
```

Run this regularly to maintain consistent code style.

### 4. Use Null Safety
Dart's null safety is enabled by default. Always specify nullable (`?`) or non-nullable types:
```dart
String? nullableString;      // Can be null
String nonNullableString;    // Cannot be null
```

### 5. Implement Error Handling
Always wrap API calls and async operations with try-catch:
```dart
try {
  // Your code here
} catch (e) {
  print('Error: $e');
  // Handle error gracefully
}
```

### 6. Use Const Constructors
Use `const` for widgets and objects that don't change:
```dart
const Text('Hello World')
```

### 7. Leverage Widget Composition
Break down large widgets into smaller, reusable components.

### 8. Profile Your App
Use DevTools to identify performance issues:
```bash
flutter run --profile
```

### 9. Use Meaningful Commit Messages
```bash
git commit -m "feat: Add shopping cart functionality"
git commit -m "fix: Resolve payment validation issue"
git commit -m "docs: Update API documentation"
```

### 10. Keep Dependencies Updated
```bash
flutter pub outdated
flutter pub upgrade
```

## Getting Started Checklist

- [ ] **Environment Setup**
  - [ ] Flutter SDK installed
  - [ ] Dart SDK installed
  - [ ] Android Studio/VS Code with extensions installed
  - [ ] `flutter doctor` shows no major issues

- [ ] **Project Cloning & Setup**
  - [ ] Repository cloned locally
  - [ ] `flutter pub get` completed successfully
  - [ ] Platform-specific setup completed (Android/iOS/Web)

- [ ] **First Run**
  - [ ] Emulator/Device connected
  - [ ] App runs successfully with `flutter run`
  - [ ] No console errors or warnings

- [ ] **Exploration**
  - [ ] Reviewed project structure
  - [ ] Located main screens and widgets
  - [ ] Understood the state management approach
  - [ ] Checked theme configuration

- [ ] **Development Environment**
  - [ ] IDE configured with Flutter/Dart plugins
  - [ ] Code formatting set to auto-format on save
  - [ ] Linting enabled for code quality

- [ ] **Understanding Features**
  - [ ] Reviewed app features overview
  - [ ] Tested main user flows
  - [ ] Explored theme switching functionality
  - [ ] Checked responsive design on different screen sizes

- [ ] **Ready for Development**
  - [ ] Run tests: `flutter test`
  - [ ] Analyze code: `flutter analyze`
  - [ ] Create a test branch for your first feature
  - [ ] Start building! 🚀

---

## Need Help?

If you encounter any issues not covered in this guide:

1. Check the [Flutter Documentation](https://flutter.dev/docs)
2. Review existing project issues on GitHub
3. Consult the [Flutter Community](https://flutter.dev/community)
4. Open an issue with detailed information about your problem

Happy coding! 🎉
