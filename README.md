# 🦘 Find My Kangaroo

**[findmykangaroo.com](https://findmykangaroo.com)** — How far are you from a kangaroo right now?

A fun, free web app that calculates the distance from your location to the nearest known kangaroo — whether that's a wild mob in the Australian outback or a friendly roo at a zoo near you.

## How It Works

1. Hit **"Find My Kangaroo"** to use your device's GPS, or type any city/address/place name
2. The app looks up your coordinates and calculates the straight-line distance to every kangaroo location in our database
3. You get the nearest match, the distance in km and miles, a compass direction, how many kangaroo hops away you are, and a random fun fact

All processing happens in your browser. We don't store any location data.

## Project Structure

```
├── index.html          # Main app
├── data/
│   ├── locations.json  # 🌏 All known kangaroo locations
│   └── facts.json      # 🧠 Fun kangaroo facts
├── privacy.html        # Privacy policy
├── terms.html          # Terms of service
├── disclaimer.html     # Disclaimer
└── README.md           # You are here
```

## Contributing

The whole point of open-sourcing this is so anyone can help build the world's most comprehensive kangaroo location database. Contributions are welcome via pull request!

### Adding a Kangaroo Location

Edit **`data/locations.json`** and add an entry. Each location needs these fields:

| Field     | Type   | Description                                      | Example                        |
|-----------|--------|--------------------------------------------------|--------------------------------|
| `name`    | string | Name of the place                                | `"Melbourne Zoo"`              |
| `lat`     | number | Latitude coordinate                              | `-37.784`                      |
| `lng`     | number | Longitude coordinate                             | `144.952`                      |
| `type`    | string | Either `"wild"` or `"zoo"`                        | `"zoo"`                        |
| `country` | string | Country name                                     | `"Australia"`                  |
| `desc`    | string | Short description (1 sentence)                   | `"Kangaroos in the Australian bush habitat."` |
| `url`     | string | Link to the location's website or a page confirming they have kangaroos | `"https://www.zoo.org.au/melbourne"` |

**Example entry:**

```json
{
  "name": "Melbourne Zoo",
  "lat": -37.784,
  "lng": 144.952,
  "type": "zoo",
  "country": "Australia",
  "desc": "Kangaroos in the Australian bush habitat trail.",
  "url": "https://www.zoo.org.au/melbourne"
}
```

**Guidelines:**
- The `url` field is required — we need a source proving kangaroos are actually there. This can be the zoo/park's official website, a page listing their animals, or a reputable travel/wildlife site.
- Use `"wild"` for natural habitats and national parks where kangaroos roam freely.
- Use `"zoo"` for zoos, sanctuaries, wildlife parks, and any captive/managed setting.
- Coordinates should be reasonably accurate. You can get them from Google Maps (right-click → "What's here?").
- Keep `desc` to one sentence. Be specific — mention the species if known, or what makes the location notable.
- Please check the existing file to avoid duplicates before adding.

### Adding a Fun Fact

Edit **`data/facts.json`** and add a string to the array.

**Guidelines:**
- Keep it to one sentence, around 15–25 words
- Make it genuinely surprising or delightful
- Include a specific number or comparison where possible (these tend to be most memorable)
- No need for a source link, but the fact should be accurate and verifiable

**Example:**

```json
"A kangaroo's stomach has a chambered structure similar to a cow's, allowing it to ferment and digest tough grasses."
```

### Submitting Your Contribution

1. **Fork** this repository
2. **Edit** `data/locations.json` or `data/facts.json`
3. **Submit a pull request** with a brief description of what you added
4. We'll review and merge it — your contribution goes live on findmykangaroo.com!

You can also [open an issue](https://github.com/ThreeForTen/findmykangaroo/issues) if you know of a location but don't want to create a PR yourself. Just include the name, country, and a link — we'll add it.

## Tech Stack

- **Frontend:** Vanilla HTML/CSS/JS (no build step, no framework)
- **Geocoding:** [OpenStreetMap Nominatim](https://nominatim.openstreetmap.org/) (free, no API key)
- **Hosting:** [GitHub Pages](https://pages.github.com/)
- **Domain:** Registered via [NoFrillsCloud](https://nofrillscloud.com/)
- **Distance:** Haversine formula (straight-line / "as the kangaroo hops")
- **AI:** Built with [Claude](https://www.anthropic.com/) by Anthropic

## Origin Story

This project was inspired by [Garrett's Adventure](https://www.youtube.com/@garrettsadventure) — a YouTuber who was in the middle of Sydney Harbour and just wanted to see a kangaroo. It was further inspired by the [Australian Embassy in Bangkok](https://www.facebook.com/australiainthailand) and their excellent soft power game.

We figured: if one person in Sydney Harbour needed this information, surely everyone does.

## Legal

- [Privacy Policy](https://findmykangaroo.com/privacy.html)
- [Terms of Service](https://findmykangaroo.com/terms.html)
- [Disclaimer](https://findmykangaroo.com/disclaimer.html)

Jurisdiction: Singapore. No kangaroos were disturbed in the making of this app.

## License

MIT — do whatever you want with it. If you build something cool with the data, let us know.
