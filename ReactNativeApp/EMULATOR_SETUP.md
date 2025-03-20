# Setting Up Emulators for React Native Development

This guide will help you set up emulators to test your React Native application on both Android and iOS platforms.

## Android Emulator Setup

### Prerequisites
- Android Studio installed
- JDK 11 or newer

### Steps to Set Up Android Emulator

1. **Install Android Studio**
   - Download and install Android Studio from [developer.android.com](https://developer.android.com/studio)

2. **Install Required SDK Components**
   - Open Android Studio
   - Go to Tools > SDK Manager
   - In the "SDK Platforms" tab, select the Android versions you want to support (recommended: Android 11 or newer)
   - In the "SDK Tools" tab, make sure the following are installed:
     - Android SDK Build-Tools
     - Android Emulator
     - Android SDK Platform-Tools
     - Google Play services
   - Click "Apply" to install the selected components

3. **Set Up a Virtual Device**
   - In Android Studio, go to Tools > AVD Manager
   - Click "Create Virtual Device"
   - Select a device definition (e.g., Pixel 4)
   - Select a system image (e.g., Android 11 or newer)
   - Configure the AVD with desired settings
   - Click "Finish" to create the virtual device

4. **Start the Emulator**
   - In the AVD Manager, click the play button next to your virtual device
   - Wait for the emulator to start up completely

5. **Run Your React Native App**
   - From your React Native project directory, run:
   ```
   npx react-native run-android
   ```

## iOS Simulator Setup (macOS only)

### Prerequisites
- Mac computer with macOS
- Xcode installed

### Steps to Set Up iOS Simulator

1. **Install Xcode**
   - Download and install Xcode from the Mac App Store
   - Open Xcode and accept the license agreement
   - Install additional required components if prompted

2. **Install Command Line Tools**
   - Open Xcode
   - Go to Preferences > Locations
   - Select the most recent version from the Command Line Tools dropdown

3. **Select a Simulator**
   - Open Xcode
   - Go to Xcode > Preferences > Components
   - Install the iOS simulator versions you want to use

4. **Run Your React Native App**
   - From your React Native project directory, run:
   ```
   npx react-native run-ios
   ```
   - Alternatively, you can specify a simulator:
   ```
   npx react-native run-ios --simulator="iPhone 14"
   ```

## Troubleshooting

### Common Issues with Android Emulator

- **Emulator is slow**: Enable hardware acceleration in your BIOS/UEFI settings
- **ADB not found**: Make sure Android SDK Platform-Tools are installed and added to your PATH
- **App crashes immediately**: Check logcat for error details using `adb logcat`

### Common Issues with iOS Simulator

- **Simulator not starting**: Try resetting the simulator via Simulator > Reset Contents and Settings
- **Build errors**: Make sure CocoaPods is installed and you've run `pod install` in the ios directory
- **"Command not found"**: Ensure you have the React Native CLI installed globally

## Useful Commands

- Check connected devices: `adb devices`
- Install app on Android: `npx react-native run-android`
- Install app on iOS: `npx react-native run-ios`
- Start Metro server: `npx react-native start`
- Clear Metro cache: `npx react-native start --reset-cache`
- Run on a specific Android device: `npx react-native run-android --deviceId=<device-id>`
- Run on a specific iOS simulator: `npx react-native run-ios --simulator="<simulator-name>"`