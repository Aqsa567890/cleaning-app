# 🌍 International Cleaning Service App

The **International Cleaning Service App** is a mobile application that provides professional cleaning services for homes, businesses, and specialized cleaning needs such as pesticide control. The app connects users with verified service providers for efficient and hassle-free cleaning solutions.

## 🚀 Features

✅ Book cleaning services with ease  
✅ Multiple cleaning options:  
   - 🏠 **Home Cleaning**  
   - 🦟 **Pest Control & Pesticide Cleaning**  
   - 🏢 **Commercial Cleaning**  
   - 🚗 **Vehicle & Outdoor Cleaning**  
✅ Secure online payments  
✅ Service provider verification  
✅ Real-time service tracking  

## 🛠️ Technologies Used

- **Development Platform:** Android Studio  
- **Programming Language:** Java  
- **Backend:** [Node.js / Firebase / Django] (Specify your choice)  
- **Database:** [MySQL / Firebase]  
- **Payment Gateway:** [Stripe / PayPal]  

## 🏗️ Installation

1. Clone the repository:  
   ```bash
   git clone https://github.com/yourusername/cleaning-service-app.git
   cd cleaning-service-app
Open the project in Android Studio.

Sync dependencies using Gradle.

Configure environment variables (API keys, database settings).

Build and run the project on an emulator or a real device.

📌 Usage
Sign up or log in to the app.

Select a cleaning service.

Schedule an appointment.

Make a secure payment.

Track your service in real time.
📜 License
This project is licensed under the MIT License.
🌍 Location API Integration
The app utilizes Google Maps API for real-time location tracking, service area coverage, and navigation.

🔧 API Setup Instructions
Get an API Key from Google Maps Platform

Go to Google Cloud Console.

Create a new project or select an existing one.

Navigate to APIs & Services > Library.

Enable the following APIs:

Maps SDK for Android

Places API

Geocoding API

Directions API

Go to Credentials and generate an API Key.

Add the API Key to Your Project

In AndroidManifest.xml, add:

xml
Copy
Edit
<meta-data
    android:name="com.google.android.geo.API_KEY"
    android:value="YOUR_API_KEY_HERE"/>
Using Google Maps in Your App

Add dependencies in build.gradle:

gradle
Copy
Edit
implementation 'com.google.android.gms:play-services-maps:18.1.0'
implementation 'com.google.android.gms:play-services-location:21.0.1'
Load Google Maps in activity_maps.xml:

xml
Copy
Edit
<fragment
    android:id="@+id/map"
    android:name="com.google.android.gms.maps.SupportMapFragment"
    android:layout_width="match_parent"
    android:layout_height="match_parent"/>
Initialize the map in MapsActivity.java:

java
Copy
Edit
public class MapsActivity extends FragmentActivity implements OnMapReadyCallback {
    private GoogleMap mMap;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_maps);
        SupportMapFragment mapFragment = (SupportMapFragment) getSupportFragmentManager()
                .findFragmentById(R.id.map);
        mapFragment.getMapAsync(this);
    }
    @Override
    public void onMapReady(GoogleMap googleMap) {
        mMap = googleMap;
        LatLng serviceArea = new LatLng(40.7128, -74.0060); // Example: New York
        mMap.addMarker(new MarkerOptions().position(serviceArea).title("Service Location"));
        mMap.moveCamera(CameraUpdateFactory.newLatLngZoom(serviceArea, 12));
    }
}
