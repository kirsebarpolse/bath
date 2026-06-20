
## Data Sources

The basic bath data comes from the [termalonline.hu](https://termalonline.hu/) collection, archived from a Google My Maps map:

- **Archived termalonline article**: [Magyarország gyógyfürdő térkép (as of 2025-08-06)](https://web.archive.org/web/20250806111746/https://termalonline.hu/termal-hirek/magyarorszag-gyogyfurdo-terkep)
- **Original Google My Maps map**: [Magyarország gyógyfürdői](https://www.google.com/maps/d/viewer?mid=1hDSW7i4zLmSfXZEGWfTAxNX9j2P_veis&femb=1&ll=47.05333882719781%2C19.39560550000002&z=8)

The regions (tájegységek) boundaries are based on the classification from [turaoldal.hu](https://web.archive.org/web/20230605011353/https://turaoldal.hu/?t=magyarorszag-tajegysegei) (archived), and their center points are stored in the `regional-centers.json` file.

## Usage

1. Clone the repo or download the files.
2. Open the `index.html` file in a browser (no web server required).
3. Use the search bar, the price sliders, and click on baths for details.

## Contributing

If you find a bug or want to suggest a new feature, open an Issue or send a Pull Request.  
You can update the data by modifying the `baths.geojson` file.
