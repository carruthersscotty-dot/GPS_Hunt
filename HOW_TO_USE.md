# How to Use the GPS Hunt App

## Overview
The GPS Hunt app is a location-based game where participants use their GPS-enabled devices to navigate to predefined waypoints. The app provides real-time tracking, leaderboards, and administrative tools for managing games.

## Setup Instructions
### 1. Create a Firebase Project
1. Go to the [Firebase Console](https://console.firebase.google.com/).
2. Click on **Add project** and give it a name (e.g., `gps-hunt`).
3. Follow the prompts to create the project.

### 2. Configure Firebase
1. In the Firebase Console, go to **Project Settings → General**.
2. Under **Your apps**, click on the web icon (`</>`).
3. Register your app and follow instructions to get your Firebase configuration.
4. Update `config.js` with your Firebase configuration details:
    ```javascript
    const GPS_HUNT_CONFIG = {
      apiKey: "YOUR_API_KEY",
      authDomain: "YOUR_AUTH_DOMAIN",
      projectId: "YOUR_PROJECT_ID",
      storageBucket: "YOUR_STORAGE_BUCKET",
      messagingSenderId: "YOUR_MESSAGING_SENDER_ID",
      appId: "YOUR_APP_ID",
      managePassword: "YOUR_MANAGE_PASSWORD"
    };
    ```

## User Guide
### Player Interface (`index.html`)
1. Open `index.html` in a web browser.
2. Start the game by clicking on **Start** or **Join Game** and entering the provided game ID.
3. The app will use your device's GPS to track your position relative to the waypoints.
4. Follow the compass and distance indicators to reach each waypoint.
5. Once you arrive at a waypoint, click **Submit Location** to confirm.
6. Your progress is displayed on the leaderboard in real-time.

### Leaderboard (`leaderboard.html`)
1. Open `leaderboard.html` in a web browser.
2. The leaderboard displays all teams' positions and distances to the next waypoint.
3. Teams are ranked based on their proximity to the current waypoint.
4. Refresh the page to see updated rankings.

## Admin Guide
### Logging In
1. Open `admin.html` in a web browser.
2. Enter the management password to access admin features.

### Creating a New Game
To create a new game, follow these steps:
1. **Log in** to the admin interface using the management password.
2. Navigate to the **Create Game** section.
3. **Enter Game Details** such as **Name**, **Description**, and an optional **Join Code**.
4. **Add Waypoints**: Click on **Add Waypoint** and enter the coordinates (latitude, longitude) for each waypoint. You can also add clues or descriptions for each waypoint to enhance the game experience.
5. **Save the Game**: Once all waypoints are added and details are confirmed, click **Save Game** to finalize the creation of your new game.

### Managing Games
1. Log in to the admin interface.
2. Select a game from the list of active games.
3. Use the edit function to modify waypoints, clues, or other details by clicking on **Edit Game**.
4. Delete games that are no longer needed by selecting **Delete Game** and confirming the deletion.

## Technical Details
### Frontend
- HTML, CSS, and JavaScript files manage the user interface and game logic.
- Pages include `index.html`, `leaderboard.html`, `admin.html`, `edit.html`, and `manage.html`.

### Backend
- Firebase Realtime Database stores game data, team positions, and other information.

### Key Components
- **game.js**: Core game logic including GPS handling, distance calculations, and Firebase integration.
- **firebase.js**: Manages Firebase connections and data synchronization.
- **style.css**: Styles all web pages for consistency and user experience.
- **admin.html**, `edit.html`, `manage.html`: Admin interfaces to create, edit, and manage games.

## Troubleshooting
### GPS Accuracy Issues
- Ensure your device's GPS is enabled and accurate.
- Check for obstructions that may affect GPS signal strength.

### Network Latency
- Real-time updates via Firebase may be affected by network latency. Ensure a stable internet connection.