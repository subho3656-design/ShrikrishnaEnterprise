# Shri Krishna Enterprise — Offline Android Billing (v1.0 source)

A native Android Java project for a single-phone, offline billing workflow.

## Included in this build
- Local SQLite database (no login, cloud, server, or internet required for normal use)
- Customer creation and customer list
- Product catalogue with product code, selling price, GST rate, and stock quantity
- Single-product invoice creation with quantity validation
- GST amount and invoice total calculation
- Stock deduction in the same SQLite transaction as invoice saving
- Saved invoice history and sales total dashboard
- Bluetooth Classic paired-device selection and basic ESC/POS receipt output
- 58mm / 80mm paper selection setting
- Minimum Android API 23 (Android 6.0)

## Business information configured
- Shri Krishna Enterprise
- Hatiara 30C Busstand, Ghosh para, Kolkata - 700157
- Phone: 8910491316

## Important limitations — read before using for real billing
This is a functional starter/MVP source project, not a certified accounting or GST-compliance product and not a complete My BillBook replacement.
- The invoice screen currently supports one product line per invoice. Multi-item cart, discounts, round-off, payment modes, returns/credit notes, supplier/purchase module, expense tracking, customer balances/ledger, PDF/share/export, backup/restore, PIN lock, and invoice numbering controls are not yet implemented.
- The receipt printer code uses Bluetooth Classic SPP and basic ESC/POS. BLE-only or vendor-specific printers may not work. Verify with your exact printer before relying on it.
- GST is calculated as one entered rate on the product's taxable value. It does not yet split CGST/SGST/IGST, validate GSTIN, or generate a legally reviewed tax invoice. Confirm invoice format and tax treatment with your accountant before business use.
- No data is uploaded. Android app data can be lost if the app is uninstalled or phone storage is cleared. Export/restore is a future feature.
- This source has not been compiled or device-tested in this workspace. The APK is therefore not included; a successful Android SDK build and physical printer test are still required.

## Build an APK
1. Install Android Studio on a Windows, Mac, or Linux computer.
2. Extract this ZIP.
3. In Android Studio choose **Open** and select the extracted `ShriKrishnaEnterprise` folder (the folder containing `settings.gradle.kts`).
4. Allow Gradle sync. Install Android SDK Platform 35 and Build Tools if prompted.
5. Select **Build → Build Bundle(s) / APK(s) → Build APK(s)**.
6. Android Studio should create the debug APK at `app/build/outputs/apk/debug/app-debug.apk` after a successful build.
7. Install the APK on the phone. Pair the printer in Android Settings → Bluetooth, then select it in the app's Printer tab.

## Technical
- Android Gradle Plugin 8.7.3
- Java source; no third-party runtime libraries
- SQLiteOpenHelper local database
- compileSdk 35, targetSdk 35, minSdk 23
- Application ID: `in.shrikrishnaenterprise.billing`
