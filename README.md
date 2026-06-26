# WorldWise

WorldWise is a single-page React application for tracking the cities you've visited around the world. Click anywhere on an interactive map to log a city, attach a date and personal notes, and build up a visual travel journal — complete with a country-level breakdown of everywhere you've been.

## Features

- **Interactive world map** powered by Leaflet, with markers for every city you've logged
- **Click-to-add workflow** — click any point on the map to drop a pin and open a pre-filled entry form
- **Automatic reverse geocoding** of the clicked coordinates into a city name, country, and flag emoji
- **City & country views** — browse visited cities individually or grouped by country
- **Geolocation support** to center the map on your current position
- **Authenticated app shell** with protected routes, gating the main app behind a login screen
- **Persisted trip data** (city name, date, notes, position) backed by a local REST API

## Tech Stack

| Layer | Technology |
|---|---|
| UI | React 19, React Router 7 |
| Mapping | Leaflet, React Leaflet |
| Forms | React Datepicker |
| State management | React Context + `useReducer` |
| Build tooling | Vite |
| Linting | ESLint |
| Mock API | json-server |

## Getting Started

### Prerequisites

- Node.js (LTS recommended)
- npm

### Installation

```bash
npm install
```

### Running locally

The app reads and writes city data from a local REST API, so two processes need to run side by side.

1. Start the mock API server (serves `data/cities.json` on port `8000`):

   ```bash
   npm run server
   ```

2. In a separate terminal, start the Vite dev server:

   ```bash
   npm run dev
   ```

3. Open the URL Vite prints (typically `http://localhost:5173`).

### Demo login

Authentication is simulated for demo purposes. Use the credentials pre-filled on the login screen:

- **Email:** `jack@example.com`
- **Password:** `qwerty`

### Other scripts

```bash
npm run build    # Production build
npm run preview  # Preview the production build locally
npm run lint     # Run ESLint
```

## Project Structure

```
src/
├── components/   # Reusable UI building blocks (Map, Form, City/Country lists, etc.)
├── contexts/      # Global state: cities data and authentication
├── hooks/         # Custom hooks (geolocation, URL position parsing)
├── pages/         # Top-level routed pages (Homepage, Login, AppLayout, etc.)
└── App.jsx        # Route definitions
data/
└── cities.json    # Mock dataset served by json-server
```

## License

Licensed under the Apache License 2.0. See [LICENSE](LICENSE) for details.
