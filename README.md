# Hungarian Thermal Baths Map

An interactive, brutalist-style web application that displays Hungary's thermal baths on a clean, easy-to-use map.
It helps users find the right bath with search, price filtering, region-based filtering, and a bilingual (Hungarian/English) interface.

## Features

- **Bath search** – instant suggestions for bath names and regions while typing, even with typos
- **Price filter** – dual range slider with preset quick buttons (0-2,000 HUF, 2,000-4,000 HUF, etc.)
- **Visual categories** – price ranges get unique geometric icons, so the category is visible at a glance on the map
- **Bath list** – all baths matching the active filters, displayed with names and adult ticket prices
- **Detailed sheet** – description, exact price, links to price list and official website, plus direct buttons for directions (Google Maps) and accommodation search (Booking, Airbnb)
- **Region-based filtering** – shows baths within a 60 km radius of a selected region (e.g., "Nyirseg", "Balaton-felvidek")
- **Bilingual interface** – the entire app is available in Hungarian and English, switchable with a single button
- **Responsive and accessible** – mobile-friendly menu, keyboard-navigable modals, screen reader support

## Technology

- **Map**: Leaflet + CartoDB Light base tiles
- **Frontend**: HTML5, CSS3 (brutalist style), vanilla JavaScript (no framework)
- **Data**: GeoJSON format with custom icons and properties
- **Languages**: full i18n support for Hungarian and English

## Technical Overview

The application is a single-page static web app with no build step or server-side dependencies. All logic runs in the browser.

- **Data loading**: GeoJSON bath data, region centers, icon definitions, and multilingual UI text are fetched as static JSON files.
- **Map rendering**: Leaflet draws the base map and custom divIcon markers using pre-generated SVG icons. Each marker is stored in a global array for fast filtering.
- **Search and filtering**: search.js handles real-time text search with Levenshtein tolerance for typos. The dual price slider updates a global filter state, and markers are toggled on/off via filterMap().
- **Region filter**: When a region is selected, distances from its center point are calculated, and markers within 60 km are shown (combined with other active filters).
- **UI components**: All overlays (search suggestions, price filter, legend, bath details, list view, "How it works") are custom-built modals managed with vanilla JS focus trapping and ARIA attributes.
- **Responsive design**: CSS media queries adapt the layout for desktop, tablet, and mobile; the header becomes a sliding side panel on small screens.

Current code status: 2026-06-20 – all core features implemented and tested in modern browsers.

## Project Structure

├── index.html # Main HTML structure
├── style.css # Brutalist styles, responsive breakpoints
├── app.js # Map initialization, interactions, data loading
├── search.js # Search, region filter, price filter logic
├── baths.geojson # Bath data (name, price, description, coordinates, icon)
├── regional-centers.json # Region center points for 60 km radius filtering
├── icon-types.json # Icon categories and price ranges
├── how-it-works.json # "How it works" description in two languages
└── README.md



## Data Sources

The basic bath data comes from the termalonline.hu collection, archived from a Google My Maps map:

- Archived termalonline article: Magyarorszag gyogyfurdo terkep (as of 2025-08-06)  
  https://web.archive.org/web/20250806111746/https://termalonline.hu/termal-hirek/magyarorszag-gyogyfurdo-terkep
- Original Google My Maps map: Magyarorszag gyogyfurdoi  
  https://www.google.com/maps/d/viewer?mid=1hDSW7i4zLmSfXZEGWfTAxNX9j2P_veis&femb=1&ll=47.05333882719781%2C19.39560550000002&z=8

The regions (tajegysegek) boundaries are based on the classification from turaoldal.hu (archived):  
https://web.archive.org/web/20230605011353/https://turaoldal.hu/?t=magyarorszag-tajegysegei

Their center points are stored in the regional-centers.json file.

## Usage

1. Clone the repo or download the files.
2. Open the index.html file in a browser (no web server required).
3. Use the search bar, the price sliders, and click on baths for details.

## Contributing

If you find a bug or want to suggest a new feature, open an Issue or send a Pull Request.
You can update the data by modifying the baths.geojson file.
