![Magyar Gyógyfürdők Térkép](assets/social-preview.png)

# Magyar gyógyfürdő térkép

Fedezd fel Magyarország összes gyógyfürdőjét egyetlen letisztult, interaktív térképen – keresővel, árszűrővel, tájegységenkénti böngészéssel és kétnyelvű felülettel.

## Funkciók
- Fürdő keresése javaslatokkal
- Ár szerinti szűrés dupla csúszkával és gyorsgombokkal
- Egyedi ikonok az ársávokhoz
- Fürdőlista aktív szűrésekkel
- Részletes adatlap árral, leírással, linkekkel
- Tájegység alapú szűrés 60 km-es körzetben
- Kétnyelvű (magyar/angol) felület
- Reszponzív, akadálymentes kialakítás

## Technológia
Leaflet + CartoDB Light, HTML5, CSS3, vanilla JavaScript, GeoJSON adatok.

## Fájlok
`index.html` `style.css` `app.js` `search.js` `baths.geojson` `regional-centers.json` `icon-types.json` `how-it-works.json`

## Adatforrások
Fürdők: [termalonline.hu](https://web.archive.org/web/20250806111746/https://termalonline.hu/termal-hirek/magyarorszag-gyogyfurdo-terkep) és [Google My Maps](https://www.google.com/maps/d/viewer?mid=1hDSW7i4zLmSfXZEGWfTAxNX9j2P_veis) archívum.  
Tájegységek: [turaoldal.hu](https://web.archive.org/web/20230605011353/https://turaoldal.hu/?t=magyarorszag-tajegysegei) felosztása.

## Használat
1. Töltsd le a fájlokat
2. Nyisd meg az `index.html`-t böngészőben
3. Keresd a fürdőket, használd a szűrőket

## Közreműködés
Hibát találsz? Nyiss Issue-t vagy Pull Request-et. Az adatok frissítése a `baths.geojson` módosításával lehetséges.

---

# Hungarian Thermal Baths Map

Explore all of Hungary's thermal baths on a single, clean interactive map – complete with search, price filters, region-based browsing, and a bilingual interface.

## Features
- Bath search with suggestions
- Price filter with dual slider and presets
- Unique icons for price categories
- Filtered bath list
- Detail sheet with price, description, links
- Region-based filtering (60 km radius)
- Bilingual (Hungarian/English) interface
- Responsive, accessible design

## Technology
Leaflet + CartoDB Light, HTML5, CSS3, vanilla JavaScript, GeoJSON data.

## Files
`index.html` `style.css` `app.js` `search.js` `baths.geojson` `regional-centers.json` `icon-types.json` `how-it-works.json`

## Data sources
Baths: [termalonline.hu](https://web.archive.org/web/20250806111746/https://termalonline.hu/termal-hirek/magyarorszag-gyogyfurdo-terkep) and [Google My Maps](https://www.google.com/maps/d/viewer?mid=1hDSW7i4zLmSfXZEGWfTAxNX9j2P_veis) archive.  
Regions: [turaoldal.hu](https://web.archive.org/web/20230605011353/https://turaoldal.hu/?t=magyarorszag-tajegysegei) classification.

## Usage
1. Download the files
2. Open `index.html` in a browser
3. Search for baths, use the filters

## Contributing
Found a bug? Open an Issue or Pull Request. Update data by editing `baths.geojson`.
