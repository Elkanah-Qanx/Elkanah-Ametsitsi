---
icon: mobile-notch
---

# HushSense Software

HushSense is a revolutionary **DePIN (Decentralized Physical Infrastructure Network)** mobile application that transforms every smartphone into a sophisticated urban noise sensor. Built with Flutter, this platform creates the world's most comprehensive real-time noise pollution database while rewarding users for their contributions through gamification and blockchain incentives.

### 🎯 Vision & Mission

### **Vision**

To build the world's largest, most accurate, real-time urban noise map, empowering communities and organizations to create quieter, healthier, and more livable cities.

#### **Mission**

Transform urban noise monitoring through community participation, turning every smartphone user into a citizen scientist contributing to a global noise pollution database.

#### **Core Innovation**

* **Software DePIN Model**: No proprietary hardware required - leverages existing smartphones
* **Gamified Contribution**: Engaging user experience that rewards data collection
* **Privacy-First Architecture**: Users own and control their data through "Honest Data Approach"
* **Dual-Sided Marketplace**: Connects data contributors with data consumers (businesses, municipalities)

### 🏗️ Architecture Overview

lib/\
├── core/                                                                       # Core business logic & services\
│ ├── animations/                                                       # Custom animations & visualizers\
│ ├── constants/                                                         # App constants & configuration\
│ ├── services/                                                           # Core services (Decibel, location, etc.)\
│ ├── theme/                                                              # Material Design 3 theming\
│ ├── utils/                                                                 # Utility functions & helpers\
│ └── widgets/                                                          # Reusable UI components\
├── domain/                                                             # Business logic & data models\
│ └── models/                                                          # Hive-enabled data models\
└── presentation/                                                   # UI & state management\
├── providers/                                                         # Riverpod state management\
├── screens/                                                           # Feature screens & navigation\
└── widgets/                                                          # Screen-specific widgets

#### **Technology Stack**

**Frontend Framework**

* **Flutter 3.24+** - Cross-platform mobile development
* **Dart 3.5+** - Type-safe programming language
* **Material Design 3** - Modern design system with custom HushSense theming

**State Management**

* **Riverpod 2.6+** - Reactive state management with dependency injection
* **Riverpod Annotations** - Code generation for providers

**Backend & Database**

* **Firebase Suite**:
* **Firebase Auth** - User authentication & management
* **Cloud Firestore** - NoSQL database for real-time data
* **Firebase Storage** - File storage for media assets
* **Firebase Messaging** - Push notifications
* **Cloud Functions** - Serverless backend logic

**Local Storage**

* **Hive 2.2+** - Fast, lightweight NoSQL database for offline functionality
* **Shared Preferences** - Simple key-value storage



**Real-Time Services**

*   **Audio Processing**:

    * **noise\_meter 5.0+** - Real-time decibel measurement
    * Custom calibration algorithms for smartphone microphones


*   **Location Services**:

    * **geolocator 13.0+** - GPS positioning
    * **geocoding 3.0+** - Address resolution
    * **google\_maps\_flutter 2.9+** - Interactive mapping


*   **Blockchain Integration**

    * **HashConnect SDK** - Wallet connectivity for Web3 features


* **Additional Features**
  * **Lottie 3.1+** - Vector animations
  * **Flutter Animate 4.5+** - Advanced animations
  * **Shimmer 3.0+** - Loading effects
  * **Connectivity Plus 6.0+** - Network status monitoring

### ✨ Key Features

#### **🎙️ Core Measurement Experience**

* **Real-time decibel meter** with beautiful animated visualizer
* **Active Mode**: 30-second measurement sessions with GPS coordinates
* **Passive Mode**: Background measurements (battery-optimized, opt-in)
* **Multi-device calibration** for consistent readings across smartphones

#### **🗺️ Interactive Noise Map**

* **Heatmap visualization** showing urban sound intensity
* **Venue markers** with average noise levels and user ratings
* **Time-based filtering** (hour, day, week, month)
* **Custom map styling** optimized for noise data visualization

#### **🏢 Facility Check-in System**



* **Venue search** via Places API integration
* **Location-based measurements** at specific venues
* **Qualitative feedback** with tags (#quiet, #lively, #background-music)
* **Higher rewards** for venue-specific data contributions

#### **🎮 Gamification & Rewards**

* **$HUSH Token System** - Rewards for data contributions
* **Achievement badges** and progress tracking
* **Daily streaks** and leaderboards
* **Level progression** with experience points
* **In-app marketplace** for redeeming rewards

#### **📊 Analytics & Insights**

* **Personal dashboard** with contribution statistics
* **Noise trend analysis** over time
* **Health impact indicators** based on noise levels
* **Community impact metrics** for collective contributions

#### **🔒 Privacy & Data Control**

* **Honest Data Approach** - Users own their data
* **Granular privacy settings** for data sharing
* **Data anonymization** and precision reduction options
* **Consent withdrawal** capabilities
* **Transparent data usage** explanations

### 🚀 Getting Started

#### **Prerequisites**

* **Flutter SDK** 3.24.3 or later
* **Dart SDK** 3.5.3 or later
* **Android Studio** (for Android development)
* **Xcode** (for iOS development)
* **Firebase Account** with project configured
* **Hedera Mainnet Account** (for blockchain features)

#### **Installation**

**1.Clone the repository**

```
git clone https://github.com/HushSense/hush-sense-mobile-app.git
cd hush-sense-mobile-app
```

**2.Install dependencies**

```
flutter pub get
```

**3.Configure Firebase**

* Create a new Firebase project at [Firebase Console](https://console.firebase.google.com/)
* Enable Authentication, Firestore, Storage, and Messaging
* Download `google-services.json` (Android) and `GoogleService-Info.plist` (iOS)
* Place configuration files in appropriate directories:
  * Android: `android/app/google-services.json`
  * iOS: `ios/Runner/GoogleService-Info.plist`

**4.Configure Google Maps**

* Get API key from [Google Cloud Console](https://console.cloud.google.com/)
* Enable Maps SDK for Android and iOS
*   Add API key to `android/app/src/main/AndroidManifest.xml`:

    ```
    <meta-data
      android:name="com.google.android.geo.API_KEY"
      android:value="YOUR_GOOGLE_MAPS_API_KEY"/>
    ```

**5.Set up local development**

```
# Generate Hive adapters
flutter pub run build_runner build

# Run code generation
flutter pub run build_runner watch --delete-conflicting-out
```



### 🔧 Development Guidelines

#### **Code Style & Standards**

**File Naming Convention**

* **Screens**: `screen_name_screen.dart` (e.g., `home_screen.dart`)
* **Widgets**: `component_name_widget.dart`
* **Services**: `service_name_service.dart`
* **Models**: `model_name.dart`
* **Providers**: `feature_name_provider.dart`

**Import Organization**

```
// Flutter/Dart imports
import 'package:flutter/material.dart';

// Third-party packages (alphabetical)
import 'package:firebase_auth/firebase_auth.dart';
import 'package:flutter_riverpod/flutter_riverpod.dart';

// Project imports (relative paths)
import '../../core/constants/app_constants.dart';
import '../models/user_profile.dart';
```

**State Management Patterns**

* Use **Riverpod** for all state management
* **StateNotifier** for complex state logic
* **StreamProvider** for real-time data streams
* **FutureProvider** for async operations

#### **Testing Strategy**

**Unit Tests**

```
# Run all tests
flutter test

# Run tests with coverage
flutter test --coverage

# Run specific test file
flutter test test/models/noise_measurement_test.dart
```

**Integration Tests**

```
# Run integration tests
flutter test integration_test/

# Run on specific device
flutter test integration_test/ -d <device_id>
```

#### **Performance Optimization**

**Memory Management**

* Use `const` constructors where possible
* Implement proper `dispose()` methods
* Monitor memory usage with Flutter DevTools
* Use `ListView.builder` for large lists

**Battery Optimization**

* Minimize background location updates
* Use efficient audio processing algorithms
* Implement app lifecycle management
* Optimize map rendering performance

**Network Efficiency**

* Implement offline-first architecture
* Use Firebase offline persistence
* Batch API requests where possible
* Implement intelligent sync strategies

### 🌐 Deployment & Distribution

#### **Android Deployment**

1.  **Build Release APK/AAB**

    ```
    flutter build appbundle --release
    ```
2. **Code Signing**
   * Configure signing in `android/app/build.gradle`
   * Generate upload key and keystore
3. **Play Store**
   * Create app listing on Google Play Console
   * Upload AAB file for review
   * Configure store listing with screenshots and descriptions

#### **iOS Deployment**

1.  **Build Release IPA**

    ```
    flutter build ios --release
    ```
2. **Code Signing**
   * Configure certificates and provisioning profiles
   * Set up App Store Connect
3. **App Store**
   * Create app record in App Store Connect
   * Upload IPA file for review
   * Manage TestFlight beta testing

#### **Continuous Integration**

```
# .github/workflows/ci.yml
name: Flutter CI

on:
  push:
    branches: [ main, develop ]
  pull_request:
    branches: [ main ]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      - uses: flutter-actions/setup-flutter@v2
      - run: flutter pub get
      - run: flutter analyze
      - run: flutter test
```

📄 License

This project is licensed under the Apache License 2.0 - see the [LICENSE](https://github.com/HushSense/hush-sense-mobile-app/blob/main/LICENSE) file for details.

#### **Open Source Contributions**

HushSense is committed to open source development. All contributions are welcome under the following guidelines:

* Code must be original and properly licensed
* Contributions should align with project goals
* Maintainers reserve right to accept/reject contributions
* All contributors must follow the Code of Conduct

\
\


\
