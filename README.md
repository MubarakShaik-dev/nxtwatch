# 🎥 NxtWatch

**credentials

username: rahul
password: rahul@2021**

A modern **React.js** Single Page Application inspired by YouTube, featuring secure authentication, theming, route-based navigation, and real-time video browsing powered by public APIs.

![React](https://img.shields.io/badge/React-18.0.0-blue?logo=react)
![Styled Components](https://img.shields.io/badge/Styled--Components-%23db7093.svg?logo=styled-components&logoColor=white)
![React Router](https://img.shields.io/badge/React%20Router-v6-critical?logo=react-router)
![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-yellow?logo=javascript)
![License](https://img.shields.io/badge/license-MIT-green)

---

## 📑 Table of Contents
1. [Live Demo](#-live-demo)
2. [Features](#-features)
3. [Tech Stack](#-tech-stack)
4. [Screenshots](#-screenshots)
5. [Setup & Installation](#-setup--installation)
6. [API Reference](#-api-reference)
7. [Challenges & Solutions](#-challenges--solutions)
8. [Contributing](#-contributing)
9. [License](#-license)

---

## 🚀 Live Demo

🔗 **[Click here to view the deployed app](https://mubaNxtWatch.ccbp.tech)**

---

## ✨ Features

- 🔐 **Authentication** — Login with username & password, JWT token storage via cookies.
- 🎯 **Protected Routes** — Redirects unauthenticated users to `/login`.
- 🎬 **Video Browsing**  
  - **Home** — Search & browse videos from `https://apis.ccbp.in/videos/all`.
  - **Trending** — View trending videos from `https://apis.ccbp.in/videos/trending`.
  - **Gaming** — Explore gaming content from `https://apis.ccbp.in/videos/gaming`.
  - **Video Details** — Like, dislike, and save videos for later.
- 💾 **Saved Videos** — Persistent list of saved content with empty state view.
- 🌓 **Light/Dark Mode** — Toggleable theme across all pages.
- 🧭 **Seamless Navigation** — Sidebar links, app logo home navigation.
- ⚠️ **Error Handling** — Retry on API failure, loaders for async calls, "No results" views.
- 📱 **Responsive Design** — Works across mobile, tablet, and desktop layouts.

---

## 🛠 Tech Stack

| Category      | Technologies |
|--------------|--------------|
| **Frontend** | React.js, React Router v6, Styled Components |
| **State Mgmt** | React Hooks, Context API |
| **Auth** | JWT with `js-cookie` |
| **Styling** | Styled Components (CSS-in-JS) |
| **API** | CCBP NxtWatch Public API |
| **Others** | Git, npm |

---

## 📸 Screenshots

> **Tip:** Add these screenshots in `/screenshots` folder and update paths.

### **Light Theme - Home Page**
![Light Home](./screenshots/home-light.png)

### **Dark Theme - Trending Page**
![Dark Trending](./screenshots/trending-dark.png)

### **Video Details**
![Video Details](./screenshots/video-details.png)

---

## ⚙️ Setup & Installation

```bash
# 1️⃣ Clone repository
git clone https://github.com/MubarakShaik-dev/nxtwatch.git

# 2️⃣ Navigate into the project folder
cd nxtwatch

# 3️⃣ Install dependencies
npm install

# 4️⃣ Start development server
npm start

credentials

username: rahul
password: rahul@2021


| Endpoint              | Method | Description                              |
| --------------------- | ------ | ---------------------------------------- |
| `/login`              | POST   | Authenticates user and returns JWT token |
| `/videos/all?search=` | GET    | Fetch all videos (searchable)            |
| `/videos/trending`    | GET    | Trending videos                          |
| `/videos/gaming`      | GET    | Gaming category videos                   |
| `/videos/:id`         | GET    | Details of a specific video              |



🧩 Challenges & Solutions
1. JWT Authentication & Route Protection
Challenge:
Ensuring that only authenticated users could access Home, Trending, Gaming, Saved Videos, and Video Details pages.

Solution:
Created a ProtectedRoute component that checks for a valid JWT token stored in cookies (js-cookie). If the token is missing, it redirects the user to the /login route.

2. Theme Synchronization Across Routes
Challenge:
Maintaining light/dark theme consistency across all pages and components without prop-drilling.

Solution:
Implemented a global theme context using React Context API and wrapped the app with ThemeProvider from styled-components. The theme toggle state is stored in Context so it updates instantly everywhere.

3. Debounced Search Functionality
Challenge:
Preventing excessive API calls while typing in the search bar on the Home page.

Solution:
Added a debounce mechanism with setTimeout and useEffect cleanup to trigger API calls only after the user stops typing for a short delay.

4. Error Handling for API Failures
Challenge:
APIs like /videos/all, /videos/trending, and /videos/gaming sometimes fail due to network issues, and the app needed to handle it gracefully.

Solution:
Created a reusable Failure View component with retry buttons. On retry, the failed API function is re-invoked, keeping the user in control.

5. Saved Videos Persistence
Challenge:
Allowing users to save videos and still have them available after a page reload.

Solution:
Stored saved video data in a Context and persisted it using localStorage, ensuring the list is restored whenever the app is reloaded.

6. Responsive Design Across Devices
Challenge:
Making sure the UI looked consistent and functional on mobile, tablet, and desktop layouts.

Solution:
Used styled-components with media queries to create adaptive layouts, ensuring that the sidebar, header, and video grid adjust dynamically to different screen sizes.

