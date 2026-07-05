<h1 align="center">
Travel Ranker
</h1>

<h2 align="center">Create a trip destination tier list.</h2>

<div align="center">

_A client-side web app for ranking bucket-list destinations, planning trips, and logging where you've been._

</div>

***

## 📋 Table of Contents

- [Overview](#-overview)
  - [Features](#features)
- [Quick Start](#-quick-start-local-development)
  - [Prerequisites](#prerequisites)
  - [Setup Instructions](#setup-instructions)
- [Usage](#️-usage)
- [Technologies Used](#️-technologies-used)
- [Security Notes](#-security-notes)
- [Troubleshooting](#-troubleshooting)
- [Contributing](#-contributing)
- [Disclaimer](#️-disclaimer)

## 📄 Overview

Travel Ranker is a client-side web application for organizing, ranking, and tracking travel destinations. It combines a drag-and-drop tier list, a trip matcher that scores destination pairings by distance and season, and a history log with both list and horizontal timeline views for trips you've actually taken.

All data — destinations, ratings, images, and trip history — is stored locally in your browser via `localStorage`, so there's no backend, no account, and no data leaving your device. This makes it ideal for travelers who want a fast, private way to rank where they want to go and keep a record of where they've been.

### Features

- **Tier List Ranking:** Drag and drop destinations between S/A/B/C/D/F tiers to rank your bucket list, with per-tier ordering preserved via drag reordering.
- **Destination Profiles:** Add destinations with a name, preferred season, cost rating (1–5), photo, geocoded location, and category ratings across food, weather, entertainment, culture, and relaxation.
- **Trip Matcher:** Pick a home base destination and see other destinations scored and ranked by geographic proximity (haversine distance) and season compatibility.
- **Visited Tracking:** Mark destinations as visited with a visual badge on their card.
- **History Log:** Record trips with a date, star rating, and written summary, linked back to the destination.
- **Dual History Views:** Toggle between a classic list view and a horizontal, scrollable timeline view showing trip thumbnails plotted chronologically.
- **Image Uploads:** Attach and auto-resize destination photos client-side before storing them as compressed data URLs.
- **Geocoding:** Look up coordinates for a destination or home base by place name using the OpenStreetMap Nominatim API.
- **Distance Units:** Switch between kilometers and miles for all distance displays.
- **Home Base Settings:** Set a fixed home location (by lookup or manual coordinates) used as the reference point for distance calculations.
- **Data Export & Import:** Back up all destinations, history, and settings to a JSON file, or restore from a previous backup.
- **Responsive Layout:** Sidebar navigation on desktop, bottom tab bar on mobile.
- **Client-Side Persistence:** All data is automatically saved to `localStorage`, so your rankings and history persist across sessions.

## 🚀 Quick Start (Local Development)

Travel Ranker is a single self-contained HTML file with no build step required.

### Prerequisites

- A modern web browser (Chrome, Firefox, Safari, or Edge)
- **Git** (optional, for cloning the repository)

### Setup Instructions

1. Clone the repository:

    ```sh
    git clone https://github.com/<your-username>/TravelRanker.git
    ```

2. Navigate to the project directory:

    ```sh
    cd TravelRanker
    ```

3. Open `travel-ranker.html` directly in your browser:

    ```sh
    open travel-ranker.html
    ```
    (On Windows, double-click the file or run `start travel-ranker.html`.)

No installation, dependencies, or dev server is required — the app runs entirely from the static HTML file.

## ⚙️ Usage

1. **Add a Destination:** Click **Add Destination** in the sidebar or the floating **+** button. Fill in the name, season, cost, photo, location (via lookup or manual coordinates), and category ratings.
2. **Rank with the Tier List:** Drag destination cards between tier rows (S through F) or the Unranked section to build your ranking.
3. **Find Trip Pairings:** Switch to the **Trip Matcher** tab, choose a home base destination from the dropdown, and review other destinations scored by distance and season match.
4. **Log a Trip:** Go to the **History** tab and click **Log a Trip** to record a visited destination, date, star rating, and summary.
5. **Switch History Views:** Use the **List / Timeline** toggle at the top of the History tab to switch between the standard list and a horizontally scrollable, dated timeline of trip thumbnails.
6. **Mark as Visited:** Open a destination's detail view and toggle **Mark as visited** to flag it with a badge.
7. **Set Your Home Base:** In **Settings**, look up or manually enter coordinates for your home location — this is the reference point for all Trip Matcher distances.
8. **Switch Units:** In **Settings**, toggle between Kilometers and Miles to change how distances are displayed app-wide.
9. **Back Up Your Data:** In **Settings**, use **Export Data** to download a JSON backup, or **Import Data** to restore from a previous export.

## 🛠️ Technologies Used

- **Vanilla JavaScript:** No framework — the entire app logic, rendering, and state management is hand-rolled.
- **HTML5 & CSS3:** Single-file structure with CSS custom properties for theming.
- **localStorage:** Client-side persistence for destinations, history, and settings.
- **Canvas API:** Used to resize and compress uploaded destination images before storage.
- **OpenStreetMap Nominatim API:** Free geocoding service used to convert place names into coordinates.
- **Haversine Formula:** Used to calculate great-circle distances between destinations for the Trip Matcher.

## 🔒 Security Notes

Travel Ranker is a purely client-side application with no backend server, user accounts, or data transmission beyond geocoding lookups.

- **Local Data Storage:** All destinations, ratings, images, and history are stored exclusively in your browser's `localStorage`. Data never leaves your device except for geocoding requests.
- **No Authentication:** There is no login system — access is controlled entirely by access to your local browser profile.
- **Limited External Calls:** The only network requests made are to the OpenStreetMap Nominatim API for place-name lookups; no destination or history data is sent externally.
- **Storage Limits:** Because images are stored as base64 data URLs in `localStorage`, large photo libraries may approach browser storage limits — export backups regularly.

## ❓ Troubleshooting

**Issue**: My destinations, history, or settings have disappeared.
- **Solution**: All data is stored in `localStorage`. Clearing your browser's site data or cache will permanently delete it. Regularly use **Export Data** in Settings to keep a JSON backup.

**Issue**: Geocoding lookup fails or returns "Location not found."
- **Solution**: Check your internet connection, try a more specific place name (e.g., add a country), or enter latitude/longitude manually.

**Issue**: "Could not save your data" alert appears.
- **Solution**: Your browser's storage may be full, often due to many large images. Remove or replace some destination photos, or export and clear old data.

**Issue**: Importing a backup file fails.
- **Solution**: Ensure the file is a valid Travel Ranker JSON export (must contain a `destinations` array). Files from other apps or manually edited JSON may not match the expected structure.

## 🤝 Contributing

Contributions are welcome. If you have suggestions for new features or bug fixes, feel free to open an issue or submit a pull request. Since Travel Ranker is a single-file, dependency-free app, please keep changes self-contained within `travel-ranker.html` unless a larger refactor is explicitly agreed upon.

## ⚠️ Disclaimer

Travel Ranker is a client-side application designed for personal use. All data is stored locally in your browser's `localStorage` and is not transmitted to external servers except for geocoding lookups. Users are solely responsible for managing their local data, including implementing their own backup strategies via the built-in export feature. This tool is provided "as is," without warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose, and non-infringement.