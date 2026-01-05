This README provides a clear overview of your **Time Arena** clone, explaining how it works, how to set it up, and how the local multi-user authentication system is structured.

---

# ⏳ Time Arena (Local Focus Tracker)

A sleek, offline-capable productivity dashboard designed to help users track their focus sessions with a GitHub-style activity heatmap. Built with a focus on privacy and "deep work" psychology.

## ✨ Features

* **Circular Focus Timer:** A high-intensity "Focus Mode" that hides the dashboard and shows a depleting circular progress ring to maintain urgency.
* **GitHub-Style Heatmap:** A visual 365-day grid that tracks your coding/work sessions. The more you work, the brighter the "glow" of the square.
* **Multi-User Local Auth:** Built-in signup and login system that stores data locally. Multiple users can share the same computer while keeping their statistics separate.
* **Offline First:** No database or internet required. All data is persisted using the browser's `localStorage`.
* **Hurry Mode:** The timer pulses and turns red during the final 10 seconds of a session to trigger focus.

---

## 🚀 Getting Started

Since this project is built using vanilla **HTML, CSS (Tailwind), and JavaScript**, there is no installation required.

1. **Download Files:** Save the provided `index.html` and `history.html` in the same folder.
2. **Open Browser:** Double-click `index.html` to launch the application.
3. **Create Account:** Use the built-in modal to sign up with a local username and password.
4. **Start Focusing:** Select your time, enter your task, and enter "Focus Mode."

---

## 🛠️ Technical Architecture

### Data Persistence

The app uses a keyed `localStorage` system to isolate user data:

* `arena_users`: Stores user credentials and unique IDs.
* `current_user_session`: Tracks which user is currently logged in.
* `sessions_{userID}`: A dedicated array for each user containing their work history.

### Component Logic

* **Timer:** Uses `setInterval` with a calculated `stroke-dashoffset` for the SVG circle to ensure smooth visual depletion.
* **Heatmap:** Dynamically generates 371 `div` elements representing the current year's weeks and days, mapping session durations to specific CSS "glow" levels.

---

## 📂 Project Structure

```bash
/time-arena
│
├── index.html     # Main dashboard, Timer, and Auth Logic
├── history.html   # Yearly Activity Heatmap and Stats
└── README.md      # Project Documentation

```

---

## 🎨 UI & Styling

* **Framework:** Tailwind CSS (via CDN).
* **Theme:** Deep Dark (`#0d0d0d`) with Orange accents (`#f97316`).
* **Animations:** Custom CSS `@keyframes` for "Hurry" pulsing and smooth SVG transitions.

---

## 📝 Usage Tips

* **Test Mode:** Use the "5 Seconds" duration to quickly test how the data saves and how the heatmap updates.
* **Data Safety:** Clearing your browser cache/site data will delete your local accounts and history. For a permanent version, consider wrapping this in an Electron app.

---
