# Web Bluetooth Smart Trainer Controller 🚴

### 🔗 **[Live Demo: 112311.github.io/trainer-control/](https://112311.github.io/trainer-control/)**

A lightweight, modern web application to control any FTMS-compatible smart trainer (Zwift Hub, JetBlack Volt, Wahoo KICKR, etc.) directly from your browser.

**No subscriptions, no accounts, no heavy 3D graphics.** Just you, your bike, and total control over the resistance.

## 🚀 Features

  * **Live Dashboard:** Real-time display of **Power (Watts)**, **Cadence (RPM)**, and **Speed (KPH)**.
  * **Manual Grade Control:** Adjust slope/incline on the fly with large `+` / `-` buttons to simulate hills.
  * **Wheel Circumference Setting:** Select wheel circumference (in millimeters) to improve speed calculations and compatibility with trainers that report/expect wheel size.
  * **Advanced Physics Engine:** Customize the simulation parameters to match your riding style:
      * **Rolling Resistance (Crr):** Simulate different road surfaces (Track, Asphalt, Gravel).
      * **Aerodynamics (Cw):** Adjust for your riding position (TT, Hoods, Upright/MTB).
      * **Wind Simulation:** Add headwind or tailwind to change the resistance curve.
  * **Zero Dependencies:** The entire app is contained in a **single HTML file**.
  * **Privacy Focused:** 100% runs in your browser. No data is sent to the cloud.

## 🛠 Compatibility

### Supported Hardware

This app is built on the **standard Bluetooth FTMS (Fitness Machine Service) protocol**.

  - **Verified Working:** **Zwift Hub** / **Zwift Hub One**
  - **Protocol Compatible:** *The following trainers use the same protocol but have not been individually tested:*
      - JetBlack Volt (V1 & V2)
      - Wahoo KICKR (Core, Snap, Move, V5+)
      - Tacx / Garmin (Neo, Flux)
      - Elite (Suito, Direto)

### Supported Browsers

This app relies on the **Web Bluetooth API**.

  * ✅ **Chrome** (Windows, Mac, Android, Linux)
  * ✅ **Edge** (Windows, Mac)
  * ✅ **Bluefy** (iOS - Web Bluetooth Browser)
  * ✅ **Safari** (Desktop/Mobile)
  * ❌ **Firefox** (Does not support Web Bluetooth yet)

## 📦 How to Use

### Method 1: Use the Live App (Recommended)

Simply visit **[112311.github.io/trainer-control/](https://112311.github.io/trainer-control/)** on a supported browser and click "Connect Trainer".

### Method 2: Run Locally

1.  Download the `index.html` file from this repository.
2.  Open it in Chrome or Edge.
3.  Click **Connect Trainer**.

## ⚙️ Advanced Physics Explained

The app allows you to tweak the **"Set Indoor Bike Simulation Parameters"** (FTMS OpCode `0x11`) and now includes a dedicated wheel circumference setting (FTMS OpCode `0x12`).

  * **Wheel Circumference:** Set the wheel circumference in millimeters (mm) to improve speed/reporting accuracy. The app sends the value using the FTMS "Set Wheel Circumference" command (note: FTMS encodes circumference in 0.1 mm units).
      * *Default:* 2155 mm (700c x 32mm)
  * **Rolling Resistance (Crr):** Adds linear resistance. Higher values feel like "sticky tires" or rough roads.
      * *Default:* 0.0051 (Standard Asphalt).
  * **Aerodynamics (Cw):** Adds exponential resistance based on speed. Higher values feel like hitting a "wall" of air at high speeds.
      * *Default:* 0.51 (75kg rider on a road bike).
  * **Wind Speed:** Simulates air velocity.
      * *Positive:* Headwind (Harder).
      * *Negative:* Tailwind (Easier).

-----

## 🤝 Acknowledgments

This project, including all code and documentation, was generated with the assistance of **Gemini 3**.

## 📝 License

MIT License. Feel free to modify, fork, and use it for your own training setup!
