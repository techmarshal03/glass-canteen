# 🍽️ GlassCanteen

A responsive, high-fidelity canteen queue management and online ordering web application tailored to solve real-world bottlenecks in college canteens. Built with a stunning white-themed **"Liquid Glass" (iOS 27 style) UI** featuring backdrop-filters, custom micro-interactions, and elastic animations.

![GlassCanteen UI Mockup](./public/glass_canteen_mockup.jpg)

---

## ⚡ Real-World Problems & Solutions

### 1. Peak Rush Hour (Queue Management)
* **Problem:** Blockages and long counter wait times during lunch/dinner peaks (e.g., 7:00 PM to 8:00 PM).
* **Solution:** A **Live Occupancy Meter** calculated dynamically based on active orders, letting students know the prep queue load (*Low Crowd ~5 min* vs *Peak Rush ~25 min*) before walking to the dining hall.

### 2. Menu Complexity (Real-time Awareness)
* **Problem:** Complex menus and students ordering items that are already out of stock, leading to counter confusion and refund delays.
* **Solution:** Categorized menus with spice meters, allergen tags, and a Veg-only toggle. The **Canteen Kitchen Portal** lets staff toggle stock status (*In Stock* vs *Sold Out*) with one tap, immediately blocking student cart additions.

### 3. Payment Gateway Congestion (UPI Bypass)
* **Problem:** Peak rush coincides with cellular congestion inside metal-roofed canteens, making UPI verification slow or causing transaction timeouts.
* **Solution:** Direct UPI payments include a simulator showing network congestion failures. Students can bypass this issue by pre-loading funds into the **In-App Canteen Wallet** during off-peak hours, allowing checkout in under 1.2 seconds.

### 4. Cold Food & Connectivity bottlenecks
* **Problem:** Scheduled orders prepared early get cold, and dead network zones prevent showing order receipts at pickup.
* **Solution:** **Arrive-to-Cook Locks** hold scheduled preparation until the student clicks **Check-In** on arrival. **CryptoCache QR Tokens** save receipt verification tokens locally on the device, working with absolutely zero cell network.

---

## 🔊 Interactive Speech Announcer (Paytm Soundbox style)
To bridge the gap between digital orders and busy canteen chefs, the app implements the browser's built-in **Web SpeechSynthesis API** to announce kitchen updates out loud:
* *"Token number 102 checked in! Chef has started cooking."*
* *"Pay attention! Token number 102 is ready for collection!"*
* *"Recharge of rupees 500 received in your canteen wallet."*

---

## 🛠️ Technology Stack
* **Bundler:** Vite
* **Frontend Library:** React.js
* **Styling:** Vanilla CSS (using CSS Custom Properties, flexbox, grids, and backdrop-filter blur)
* **Icons:** Lucide React

---

## 📁 Folder Structure
```text
canteen-app/
├── public/
│   └── glass_canteen_mockup.jpg   # Project UI Mockup
├── src/
│   ├── assets/                    # Assets and logos
│   ├── components/                # Modular UI Components
│   │   ├── Dashboard.jsx          # Live rush status, Wallet recharges, Specials
│   │   ├── Menu.jsx               # Categorized stock catalog, search, veg filters
│   │   ├── CartCheckout.jsx       # Checkout flow, UPI simulator, Wallet pay
│   │   ├── OrderTracker.jsx       # Timeline tracker, check-ins, Offline QR code
│   │   └── StaffPortal.jsx        # Canteen queue dashboard & soundbox panel
│   ├── App.jsx                    # State hub and voice announcement controller
│   ├── index.css                  # Core Liquid Glass design system & styling
│   └── main.jsx                   # React mounting node
├── package.json                   # Dependencies and scripts
└── vite.config.js                 # Vite compilation configuration
```

---

## 🚀 Setup & Installation

Follow these steps to run GlassCanteen locally on your machine:

1. **Clone or Download the Repository:**
   ```bash
   git clone https://github.com/your-username/glass-canteen.git
   cd glass-canteen
   ```

2. **Install Dependencies:**
   ```bash
   npm install
   ```

3. **Start the Development Server:**
   ```bash
   npm run dev
   ```
   Open your browser to [http://localhost:5173/](http://localhost:5173/) to view the app!

4. **Build for Production:**
   ```bash
   npm run build
   ```

---

## 🌐 Easy Cloud Deployment

This is a pure frontend Single Page Application (SPA), which makes it highly scalable and **100% free** to host on any of the following platforms:

### ⚡ Vercel / Netlify
1. Connect your GitHub repository.
2. Select **Vite** as the framework template.
3. Configure the build command as `npm run build` and publish directory as `dist`.
4. Click **Deploy**!

### 🐙 GitHub Pages
You can use the `gh-pages` package to publish directly from your console:
1. Install development dependency: `npm install -D gh-pages`
2. Add deploy scripts to `package.json`:
   ```json
   "predeploy": "npm run build",
   "deploy": "gh-pages -d dist"
   ```
3. Run `npm run deploy` to publish!
