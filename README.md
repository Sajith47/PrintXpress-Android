# PrintXpress – Native Android App

A digital printing service app for customers in Sri Lanka.  
Built with **Java + XML** in Android Studio.

---

## 📁 Project Structure

```
PrintXpress/
├── app/
│   ├── build.gradle                  ← App dependencies
│   ├── google-services.json          ← ⚠️ REPLACE with your Firebase file
│   └── src/main/
│       ├── AndroidManifest.xml
│       ├── java/com/printxpress/app/
│       │   ├── PrintXpressApp.java   ← Application class
│       │   ├── activities/           ← All screens
│       │   │   ├── SplashActivity.java
│       │   │   ├── LoginActivity.java
│       │   │   ├── RegisterActivity.java
│       │   │   ├── ForgotPasswordActivity.java
│       │   │   ├── MainActivity.java
│       │   │   ├── ProductListActivity.java
│       │   │   ├── ProductDetailActivity.java
│       │   │   ├── CartActivity.java
│       │   │   ├── OrderTrackingActivity.java
│       │   │   ├── ProfileActivity.java
│       │   │   ├── FaqActivity.java
│       │   │   └── fragments/
│       │   │       ├── HomeFragment.java
│       │   │       ├── OrdersFragment.java
│       │   │       └── ProfileFragment.java
│       │   ├── adapters/             ← RecyclerView adapters
│       │   │   ├── BannerAdapter.java
│       │   │   ├── CategoryAdapter.java
│       │   │   ├── ProductAdapter.java
│       │   │   ├── ProductGridAdapter.java
│       │   │   ├── CartAdapter.java
│       │   │   ├── OrderAdapter.java
│       │   │   └── FaqAdapter.java
│       │   ├── models/               ← Data models
│       │   │   ├── Product.java
│       │   │   ├── Category.java
│       │   │   ├── CartItem.java
│       │   │   ├── Order.java
│       │   │   └── User.java
│       │   └── utils/
│       │       ├── SampleData.java
│       │       ├── CartManager.java
│       │       ├── FirebaseHelper.java
│       │       ├── NetworkUtils.java
│       │       ├── FormatUtils.java
│       │       ├── SharedPrefsHelper.java
│       │       └── PrintXpressMessagingService.java
│       └── res/
│           ├── layout/               ← All XML layouts
│           ├── drawable/             ← Shapes, gradients, icons
│           ├── values/               ← colors, strings, dimens, themes
│           ├── color/                ← Color state lists
│           └── menu/                 ← Bottom navigation menu
├── build.gradle                      ← Root build file
├── settings.gradle
└── gradle.properties
```

---

## 🚀 Setup Instructions

### Step 1 – Firebase Setup
1. Go to [https://console.firebase.google.com](https://console.firebase.google.com)
2. Create a new project named **PrintXpress**
3. Add an Android app with package name: `com.printxpress.app`
4. Download `google-services.json`
5. **Replace** `app/google-services.json` with the downloaded file

### Step 2 – Enable Firebase Services
In the Firebase Console, enable:
- **Authentication** → Sign-in method → Email/Password → Enable
- **Firestore Database** → Create database → Start in test mode
- **Storage** → Get started
- **Cloud Messaging** (for push notifications)

### Step 3 – Open in Android Studio
1. Open Android Studio
2. File → Open → Select the `PrintXpress` folder
3. Wait for Gradle sync to complete
4. Run on emulator or physical device (API 24+)

---

## 🔧 Firestore Database Structure

```
users/
  {userId}/
    name: "John Doe"
    email: "john@email.com"
    phone: "+94 77 123 4567"
    profileImageUrl: ""
    fcmToken: "device_token"
    createdAt: Timestamp

orders/
  {orderId}/
    userId: "firebase_uid"
    displayOrderId: "PX2024001"
    status: "PRINTING"
    subtotal: 3600
    deliveryFee: 350
    total: 3950
    deliveryType: "DELIVERY"
    createdAt: Timestamp
    itemCount: 3

design_files/ (Firebase Storage)
  {userId}/
    {orderId}/
      filename.pdf
```

---

## 📱 Screens

| Screen               | File                          |
|----------------------|-------------------------------|
| Splash               | SplashActivity.java           |
| Login                | LoginActivity.java            |
| Register             | RegisterActivity.java         |
| Forgot Password      | ForgotPasswordActivity.java   |
| Home                 | HomeFragment.java             |
| Product List         | ProductListActivity.java      |
| Product Detail       | ProductDetailActivity.java    |
| Cart                 | CartActivity.java             |
| Order Tracking       | OrderTrackingActivity.java    |
| Profile              | ProfileFragment.java          |
| FAQ & Help           | FaqActivity.java              |

---

## 📦 Dependencies

```gradle
// Firebase
implementation platform('com.google.firebase:firebase-bom:32.7.0')
implementation 'com.google.firebase:firebase-auth'
implementation 'com.google.firebase:firebase-firestore'
implementation 'com.google.firebase:firebase-storage'
implementation 'com.google.firebase:firebase-messaging'

// UI
implementation 'com.google.android.material:material:1.11.0'
implementation 'androidx.recyclerview:recyclerview:1.3.2'
implementation 'androidx.cardview:cardview:1.0.0'
implementation 'androidx.viewpager2:viewpager2:1.0.0'

// Images
implementation 'com.github.bumptech.glide:glide:4.16.0'
implementation 'de.hdodenhof:circleimageview:3.1.0'
implementation 'com.tbuonomo:dotsindicator:5.0'
```

---

## 🎨 Brand Colors

| Token           | Hex       | Use                  |
|-----------------|-----------|----------------------|
| primary         | `#1A237E` | Main brand (Indigo)  |
| accent          | `#FF6F00` | CTA buttons (Amber)  |
| background      | `#F5F6FA` | Screen backgrounds   |
| surface         | `#FFFFFF` | Cards                |
| text_primary    | `#1A1A2E` | Headlines            |
| text_secondary  | `#5C6BC0` | Subtitles            |

---

*PrintXpress v1.0 – Made for Sri Lanka 🇱🇰*
