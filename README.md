# Magyar gyógyfürdő térkép

Interaktív térkép, amely Magyarország gyógyfürdőit jeleníti meg egy letisztult térképen.
Keresővel, árszűrővel, tájegység szerinti szűréssel és kétnyelvű (magyar/angol) felülettel segíti a felhasználót a megfelelő fürdő megtalálásában.

## Funkciók

- **Fürdő keresése** – gépelés közben azonnali javaslatok fürdőnevekre és tájegységekre, akár elgépelés esetén is
- **Ár szerinti szűrés** – dupla csúszkás árszűrő, előre definiált gyorsgombokkal (0–2000 Ft, 2000–4000 Ft stb.)
- **Vizuális kategóriák** – az ársávokhoz egyedi geometrikus ikonok tartoznak, így egy pillantással átlátható a fürdők árkategóriája
- **Fürdőlista** – az aktív szűréseknek megfelelő fürdők listája névvel és felnőtt belépőjeggyel
- **Részletes adatlap** – leírás, pontos ár, link az árlistához és a hivatalos honlaphoz, valamint közvetlen gombok útvonaltervhez (Google Térkép) és szálláskereséshez (Booking, Airbnb)
- **Tájegység alapú szűrés** – a kiválasztott tájegység középpontjától 60 km-es körzetben mutatja a fürdőket (pl. Nyírség, Balaton-felvidék)
- **Kétnyelvű felület** – a teljes alkalmazás magyarul és angolul is használható, egy gombnyomással váltható
- **Reszponzív és akadálymentes** – mobilbarát menü, billentyűzetről kezelhető modálok, képernyőolvasó-támogatás

## Technológia

- **Térkép**: Leaflet + CartoDB Light alaptérkép
- **Frontend**: HTML5, CSS3 (brutál stílus), vanilla JavaScript (nincs keretrendszer)
- **Adatok**: GeoJSON formátum, egyedi ikonokkal és tulajdonságokkal
- **Nyelvek**: teljes körű i18n magyar és angol nyelven

## Technikai összefoglaló

Az alkalmazás egyetlen statikus weblap, nincs build folyamat vagy szerveroldali függőség. Minden logika a böngészőben fut.

- **Adatbetöltés**: a fürdők GeoJSON adatai, a tájegységek középpontjai, az ikondefiníciók és a többnyelvű feliratok statikus JSON fájlokból töltődnek be.
- **Térkép megjelenítése**: a Leaflet rajzolja ki az alaptérképet és az egyedi divIcon markereket, előre generált SVG ikonokkal. Minden marker egy globális tömbben tárolódik a gyors szűrés érdekében.
- **Keresés és szűrés**: a search.js végzi a valós idejű szöveges keresést, Levenshtein-távolság alapú tűréssel az elgépelésekre. A dupla árcsúszka egy globális szűrőállapotot frissít, a markereket a filterMap() kapcsolja ki/be.
- **Tájegység-szűrés**: egy tájegység kiválasztásakor a program kiszámítja a távolságot a középpontjától, és a 60 km-en belüli markereket jeleníti meg (a többi aktív szűrővel kombinálva).
- **UI komponensek**: minden overlay (keresési javaslatok, árszűrő, jelmagyarázat, fürdő adatlap, listanézet, "Hogyan működik") egyedi építésű modál, natív JavaScript focus kezeléssel és ARIA attribútumokkal.
- **Reszponzív dizájn**: CSS media query-k igazítják az elrendezést asztali, táblagép és mobil nézethez; a fejléc kis képernyőn oldalról beúszó panellé alakul.

A kód aktuális állapota: 2026-06-20 – minden alapvető funkció megvalósítva és tesztelve modern böngészőkben.



## Adatforrások

A fürdők alapadatai a termalonline.hu gyűjtéséből származnak, egy Google My Maps térképről archiválva:

- Archivált termalonline cikk: Magyarország gyógyfürdő térkép (2025-08-06-i állapot)  
  https://web.archive.org/web/20250806111746/https://termalonline.hu/termal-hirek/magyarorszag-gyogyfurdo-terkep
- Eredeti Google My Maps térkép: Magyarország gyógyfürdői  
  https://www.google.com/maps/d/viewer?mid=1hDSW7i4zLmSfXZEGWfTAxNX9j2P_veis&femb=1&ll=47.05333882719781%2C19.39560550000002&z=8

A tájegységek lehatárolása a turaoldal.hu felosztásán alapul (archivált):  
https://web.archive.org/web/20230605011353/https://turaoldal.hu/?t=magyarorszag-tajegysegei

A tájegységek középpontjai a regional-centers.json fájlban találhatók.

## Használat

1. Klónozd a repót vagy töltsd le a fájlokat.
2. Nyisd meg az index.html fájlt egy böngészőben (nincs szükség webszerverre).
3. Használd a keresőt, az árszűrő csúszkáit, és kattints a fürdőkre a részletekért.

## Közreműködés

Ha hibát találsz, vagy új funkciót javasolnál, nyiss egy Issue-t, vagy küldj Pull Request-et.
Az adatok frissítése a baths.geojson fájl módosításával lehetséges.




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
