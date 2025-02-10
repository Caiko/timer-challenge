# ⏳ Timer Challenge - React App

## 📚 Overview

Timer Challenge is a **React-powered** interactive timing application that allows users to **start, stop, and reset a countdown timer**. The app provides real-time feedback based on the user's ability to estimate time and stop the timer accurately. It uses **React hooks**, **Refs**, and **Portals** to manage timers and modals efficiently.

---

## 🚀 Features

- **Dynamic Timer** - Users can start and stop a countdown.
- **Ref-Based Modal** - Uses `useRef` and `useImperativeHandle` to control modals.
- **React Portals** - The `ResultModal` component is rendered outside the main DOM hierarchy.
- **State Management** - Uses `useState` for tracking time.
- **Component Reusability** - Modular component design.
- **Real-time Score Calculation** - Displays performance based on stopping accuracy.

---

## 💻 Technologies Used

- **React** - Core library for UI components.
- **Vite** - Fast build tool for modern frontend apps.
- **JavaScript (ES6)** - Modern JavaScript features.
- **CSS** - Styling for a clean UI.
- **React Portals** - Modal rendering outside the root DOM tree.

---

## 📸 Project Preview

![image](https://github.com/user-attachments/assets/9f414fce-0dd9-438c-bb7c-e71a0b773183)
![image](https://github.com/user-attachments/assets/e665ad73-ad06-4f84-8b28-909033133ee3)


---

## 📂 Project Structure

```
timer-challenge/
├── src/
│   ├── assets/                 # Static assets (icons, images, etc.)
│   ├── components/             # Reusable UI components
│   │   ├── Player.jsx          # Handles user name input
│   │   ├── ResultModal.jsx     # Modal component for results
│   │   ├── TimerChallenge.jsx  # Timer logic and UI
│   ├── App.jsx                 # Main application component
│   ├── index.css               # Global styles
│   ├── main.jsx                # Entry point for React
├── public/                     # Public assets
├── index.html                   # Main HTML template
├── vite.config.js               # Vite configuration
├── package.json                 # Dependencies and scripts
├── README.md                    # Project documentation
└── .gitignore                    # Files to ignore in Git
```

---

## 💾 Installation & Setup

### 1️⃣ Clone the Repository

```sh
git clone https://github.com/Caiko/timer-challenge.git
cd timer-challenge
```

### 2️⃣ Install Dependencies

```sh
npm install
```

### 3️⃣ Run the Development Server

```sh
npm run dev
```

Then open [**localhost:5173**](http://localhost:5173) in your browser (default Vite port).

---

## 🛠️ Component Breakdown

### **1️⃣ TimerChallenge.jsx**

- Handles the countdown timer logic.
- Uses `useRef()` to manage the interval.
- Calls `ResultModal` when the timer stops.

```jsx
const timer = useRef();
const dialog = useRef();
const [timeRemaining, setTimeRemaining] = useState(targetTime * 1000);

if (timeRemaining <= 0) {
  clearInterval(timer.current);
  dialog.current.open();
}
```

---

### **2️⃣ ResultModal.jsx**

- Uses `React.createPortal()` to render outside the main DOM.
- Uses `useImperativeHandle()` to expose modal methods.
- Displays the user’s score and remaining time.

```jsx
useImperativeHandle(ref, () => ({
  open() {
    dialog.current.showModal();
  },
}));
```



