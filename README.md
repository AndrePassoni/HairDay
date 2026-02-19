# HairDay

HairDay is a simple web application for managing hair salon/barbershop appointments.  
It allows viewing daily appointments and canceling existing ones.

The project uses plain JavaScript, HTML and CSS on the frontend, bundled with Webpack, and a local JSON Server to simulate the backend/data storage.

![HairDay Hero](./preview.svg)  

## Current Features

- Display all appointments scheduled for the current day
- Cancel an existing appointment
- Local data persistence using JSON Server (file-based)

## Technologies Used

- **Frontend**: Vanilla JavaScript, HTML5, CSS3
- **Bundler**: Webpack + Babel
- **Date handling**: Day.js
- **Development server / fake API**: JSON Server
- No frameworks (React, Vue, etc.) or backend framework

## Project Structure

HairDay/
├── src/                # Source code (JS logic for appointments)
├── dist/               # Built files (after webpack build)
├── index.html          # Main entry point
├── server.json         # Data file used by JSON Server (appointments)
├── package.json
├── package-lock.json
├── webpack.config.js
└── .gitignore

## Quick Start

### Prerequisites

- Node.js (v14+ recommended)
- npm

### Installation

1. Clone the repository

```bash
git clone https://github.com/AndrePassoni/HairDay.git
cd HairDay
```

2. Install dependencies

```bash
npm install
```

### Running the project

1. **Start the JSON Server** (fake backend)  
   In one terminal:

```bash
npx json-server --watch server.json --port 3000
```

2. **Build the frontend** (once, or whenever you change src files)

```bash
npm run build
```

3. **Serve the built files** (or use any static server)  
   Simple option with http-server:

```bash
npx http-server dist -p 8080 --open
```

Or open `dist/index.html` directly in the browser (but fetch to `http://localhost:3000` must work).

Recommended development flow: keep JSON Server running, rebuild when needed, refresh browser.

### Available npm scripts (current)

```json
"scripts": {
  "build": "webpack --mode production"
  // You can add more, e.g.:
  // "server": "json-server --watch server.json --port 3000",
  // "dev": "webpack --mode development --watch"
}
```

## How to Use

1. Start JSON Server on port 3000
2. Build the project (`npm run build`)
3. Open the application (http://localhost:8080 or file://.../dist/index.html)
4. The page will show today's appointments (if any exist in `server.json`)
5. Click to cancel an appointment (updates `server.json` via fetch)

## License

MIT License

<p align="center">
  Made with 💜 by <a href="https://github.com/AndrePassoni">André Passoni</a>
</p>