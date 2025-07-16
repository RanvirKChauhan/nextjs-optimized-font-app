# Android Barcode Scanner Application

A comprehensive Android application built with Java that provides barcode scanning functionality, database storage, history management, and email reporting capabilities.

## Features

- **Real-time Barcode Scanning**: Uses CameraX and ML Kit for accurate barcode detection
- **Database Storage**: SQLite database to store all scanned barcodes with timestamps
- **History Management**: View, search, and filter scanned barcode history
- **Email Reporting**: Send detailed reports via email with selected date ranges
- **Modern UI**: Material Design with dark/light theme support
- **Flash Support**: Toggle flash for scanning in low-light conditions
- **Multiple Barcode Types**: Supports QR Code, Code 128, Code 39, EAN-13, UPC-A, and more

## Supported Barcode Types

- QR Code
- Code 128
- Code 39
- Code 93
- Codabar
- EAN-13
- EAN-8
- ITF
- UPC-A
- UPC-E
- PDF417
- Data Matrix
- Aztec

## Project Structure

```
android-barcode-scanner/
├── app/
│   ├── src/main/
│   │   ├── java/com/barcodescanner/
│   │   │   ├── MainActivity.java          # Main scanning interface
│   │   │   ├── HistoryActivity.java       # History management
│   │   │   ├── EmailActivity.java         # Email reporting
│   │   │   ├── Barcode.java               # Data model
│   │   │   ├── DatabaseHelper.java        # SQLite operations
│   │   │   └── BarcodeAdapter.java        # RecyclerView adapter
│   │   ├── res/
│   │   │   ├── layout/                    # All UI layouts
│   │   │   ├── values/                    # Strings, colors, themes
│   │   │   └── drawable/                  # UI drawables
│   │   └── AndroidManifest.xml            # App permissions and activities
│   ├── build.gradle                       # App-level build configuration
│   └── proguard-rules.pro                 # ProGuard rules
├── build.gradle                           # Project-level build configuration
├── settings.gradle                        # Project settings
└── README.md                             # This file
```

## Prerequisites

- Android Studio Arctic Fox (2020.3.1) or later
- Android SDK 34 or later
- Java 8 or later
- Minimum Android API 24 (Android 7.0)

## Setup Instructions

1. **Clone or Download the Project**
   ```bash
   git clone [repository-url]
   cd android-barcode-scanner
   ```

2. **Open in Android Studio**
   - Launch Android Studio
   - Select "Open an existing Android Studio project"
   - Navigate to the project directory and select it

3. **Sync Project**
   - Android Studio will automatically sync the project
   - If not, click "Sync Now" in the notification bar

4. **Build the Project**
   - Click "Build" → "Make Project" or press Ctrl+F9

5. **Run on Device/Emulator**
   - Connect an Android device or start an emulator
   - Click "Run" → "Run 'app'" or press Shift+F10

## Permissions Required

The app requires the following permissions:
- **Camera**: For barcode scanning
- **Internet**: For email functionality
- **Storage**: For database operations

## Usage Guide

### 1. Scanning Barcodes
- Launch the app
- Point the camera at any barcode
- The barcode will be automatically detected and saved
- View the scanned result at the bottom of the screen

### 2. Viewing History
- Tap "View History" to see all scanned barcodes
- Use search to find specific barcodes
- Filter by Today, This Week, or All Time
- Tap on any barcode to view details
- Long press for options (Copy, Delete)

### 3. Sending Email Reports
- Tap "Send Email" from the main screen
- Enter recipient email address
- Select date range (Today, Week, All Time, or Custom)
- Preview the data before sending
- Tap "Send Email" to generate and send the report

### 4. Managing Data
- Clear individual barcodes from history
- Clear all history using the floating action button
- Data persists until manually cleared

## Database Schema

The app uses SQLite with the following schema:

**Table: barcodes**
- `id` (INTEGER PRIMARY KEY AUTOINCREMENT)
- `barcode_value` (TEXT) - The actual barcode data
- `barcode_type` (TEXT) - Type of barcode (QR_CODE, CODE_128, etc.)
- `scan_date` (DATETIME) - Timestamp of scan
- `additional_info` (TEXT) - Optional additional information

## Building from Command Line

```bash
# Build debug APK
./gradlew assembleDebug

# Build release APK
./gradlew assembleRelease

# Install on connected device
./gradlew installDebug
```

## Troubleshooting

### Camera Permission Issues
- Ensure camera permission is granted in app settings
- Check if device has a camera

### Email Not Working
- Ensure an email client is installed
- Check internet connection
- Verify email address format

### Build Issues
- Clean and rebuild: `Build → Clean Project`
- Invalidate caches: `File → Invalidate Caches and Restart`
- Check Android SDK is properly configured

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

This project is open source and available under the MIT License.

## Support

For issues or questions, please open an issue on the project repository.
