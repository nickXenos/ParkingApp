# 🚗 ParkFinder – Android App

ParkFinder is an Android application that helps users find available parking spots around Thessaloniki, book and pay for the spot, and navigate to it, simulating a real-world parking experience.

---

## 📱 Features

- 🗺️ **Google Maps Integration**: View all nearby parking spots with color-coded markers (🟢 Available / 🔴 Full).
- ✅ **Booking System**: Tap an available spot, choose the duration, and mark it as reserved.
- 🔁 **Real-Time Updates**: Booked spots become unavailable and are updated live.
- ⏳ **Automatic Reset**: Spots become available again after the booking time passes.
- 📍 **Navigation Support**: Opens Google Maps with driving directions from user location to the selected parking spot.
- 📦 **Local Database**: Uses Room to store parking data persistently on the device.
- 🔔 **Notifications**: Reminder sent when navigating with Google Maps, allowing quick return to the app.

---

## 🧠 Architecture Overview

### Project Structure

com.example.parkfinder
├── MainActivity.kt # Main logic, maps UI, booking, navigation
├── AppDatabase.kt # Room database setup
├── ParkingSpot.kt # Data class for parking spot entity
├── ParkingSpotDao.kt # DAO for database queries
└── res/layout/activity_main.xml # Main app layout with buttons, map, info panel


---

## 🏗️ Tech Stack

- **Language**: Kotlin
- **UI**: Google Maps API, XML Layout
- **Database**: [Room Persistence Library](https://developer.android.com/jetpack/androidx/releases/room)
- **Navigation**: Google Maps Intent API
- **Architecture**: MVVM-lite with DAO, Database, and UI separation

---

## 🛠️ How It Works

### Parking Spots

- 100 dummy parking spots are generated randomly around Thessaloniki.
- Each has a title, availability (`✅ Available` or `❌ Full`), distance, and coordinates.
- Stored in Room DB.

### Booking Flow

1. User taps an **available** marker and a booking dialog appears.
2. User chooses a **duration** (1h, 2h, ...).
3. Status becomes `❌ Full` and parking spot changes to `Booked for X hours`.
4. A handler reverts the spot to `✅ Available` after the selected time.

### Navigation

- Pressing "Navigate" opens Google Maps and starts turn-by-turn navigation.
- The route is from user location to the spot.

---

## 🧪 Screenshots

<img src="screenshots/map_view.png" width="300" />
<img src="screenshots/booking_dialog.png" width="300" />
<img src="screenshots/navigation.png" width="300" />

---

## 📦 Setup Instructions

1. Clone the repository:
bash
git clone https://github.com/yourusername/parkfinder.git 

2. Open with Android Studio.
3. Enable Google Maps API in your Google Cloud Console.
4. Add your API key to AndroidManifest.xml:
   <meta-data
    android:name="com.google.android.geo.API_KEY"
    android:value="YOUR_API_KEY_HERE" />
5. Run on a physical device or an emulator.

---

📋 Requirements:

Android Studio Bumblebee or later
Android API Level 29+
Google Play Services
Internet access for map/navigation

---

💡 Future Improvements:
Firebase for cloud syncing
User login & history
Payment integration (Stripe, Google Pay)
Real-time availability using sensors

---

👤 Authors:
Xenos Nikolaos Sarantis – Developer


