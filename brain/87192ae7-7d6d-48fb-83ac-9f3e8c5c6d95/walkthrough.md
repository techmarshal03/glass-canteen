# Walkthrough: GlassCanteen Web Application

We have successfully built and verified **GlassCanteen**, an end-to-end, high-fidelity web application solving the fundamental bottlenecks of Indian college canteens. It features an ultra-premium, white-themed "Liquid Glass" (iOS 27 glassmorphic) UI with backdrop blurs, elastic physics transitions, and moving color blobs.

---

## 📸 UI Design & Layout Mockup

The application features a responsive split-screen (perfect for desktop faculty presentations) that syncs student actions and kitchen cooking status in real-time, backed by a voice soundbox announcement system:

![GlassCanteen Liquid UI Mockup](file:///C:/Users/Raja/.gemini/antigravity/brain/87192ae7-7d6d-48fb-83ac-9f3e8c5c6d95/glass_canteen_mockup_1786890579520.jpg)

---

## 🛠️ Key Features & Solved Scenarios

We have implemented precise features for each of the four target canteen problems:

### 1. Peak Rush Hour (Queue Management)
- **Live Crowd Occupancy Meter:** A dynamic meter that updates based on the current number of active cooking orders, giving students a warning (e.g., *"Peak Dinner Rush - 25 min wait"* vs *"Low Crowd - 5 min wait"*).
- **Aesthetic Liquid Progress Bar:** Visual occupancy meter with smooth gradient animations and glowing overlays.

### 2. Menu Complexity (Awareness)
- **Real-Time Stock Counters:** Products show in-stock quantities or toggle to a beautiful, translucent "Sold Out" state.
- **Categorized Navigation:** Tabs for Breakfast, Meals, Snacks, and Drinks, complete with search, rating metrics, spice scales, and veg-only filter toggles.
- **Synchronized Inventory Controls:** Toggling an item as "Sold Out" on the Canteen Staff portal instantly locks out orders on the Student menu in real-time.

### 3. Payment Congestion (UPI Congestion Bypass)
- **UPI Gateway Failure Simulator:** To simulate real-world cellular range bottlenecks under metal canteen roofs, checking out via UPI fires a loading sequence, followed by a simulated network timeout error.
- **Pre-Paid Wallet Converter:** Upon a UPI gateway timeout, the app offers an educational bypass banner allowing students to instantly add funds to their in-app wallet and complete the order. Transactions via the Canteen Wallet complete in 1.2 seconds.

### 4. Online Scheduling & Offline Collection
- **Break Slot Selection:** Students can schedule orders during class breaks (e.g. *01:15 PM Lunch Break*).
- **Arrive-to-Cook Check-In Lock:** To prevent cold food and waste, scheduled orders stay locked in queue. The kitchen only starts cooking once the student arrives at the canteen and taps **📍 Check-In (I'm at Canteen)** on their tracking screen.
- **CryptoCache Offline QR Code:** Orders generate a local secure QR pickup token. Even if cell network is completely dead inside the canteen hall, students can show their screen token to the counter.

---

## 🔊 Faculty Highlight: Paytm-style Soundbox Simulator
Using the built-in browser **SpeechSynthesis API**, the Canteen Staff portal features an automated announcer. Turn on the volume, and as you change order states, the app speaks aloud:
- Student Check-In: *"Token 125 checked in! Chef has started cooking."*
- Staff marks preparing: *"Token 125 is now preparing."*
- Staff marks ready: *"Pay attention! Token 125 is ready for collection!"*
- Recharge wallet: *"Recharge of rupees 500 received in your canteen wallet."*

---

## 🚀 Build Verification & Running

### Verification Results
1. **Production Build:** Successfully bundled and compiled:
   - Command: `npm run build`
   - Exit Code: `0`
   - Output Assets: JS bundle (`246.69 kB`) and CSS stylesheet (`7.55 kB`).
2. **Active Server:** A background dev server has been launched:
   - Address: [http://localhost:5173/](http://localhost:5173/)

### How to Run Locally
If you want to view, run, or edit the source files:
- The codebase is situated in the directory: [canteen-app](file:///C:/Users/Raja/.gemini/antigravity/scratch/canteen-app)
- To start the dev server manually if stopped, run:
  ```powershell
  cd canteen-app
  npm run dev
  ```
