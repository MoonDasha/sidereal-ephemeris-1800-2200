# Vedic Astrology Ephemeris Dataset (1800–2200)

Free daily sidereal ephemeris data for **Vedic Astrology (Jyotish)**, planetary
transit research, horoscope applications, astrology software, and birth chart
tools. The dataset covers the Sun, Moon, planets, Rahu, and Ketu for every date
from 1800 through 2200.

Download the planetary positions as yearly [JSON](./json),
[Markdown](./markdown), or [CSV](./csv) files. The data is released under CC0
for unrestricted personal, academic, and commercial use.

## Vedic astrology data at a glance

| Property | Value |
| --- | --- |
| Date range | 1 January 1800–31 December 2200 |
| Frequency | One planetary position per day |
| Zodiac | Sidereal (Nirayana) |
| Ayanamsa | Lahiri |
| Daily time | 12:00 at UTC+05:30 (06:30 UTC) |
| Coordinate format | Zodiac sign and decimal degrees |
| File formats | JSON, Markdown, CSV |
| License | CC0 1.0 Universal |

## Planetary positions included

Each daily Vedic astrology ephemeris record contains the sidereal longitude of:

- Sun (Surya)
- Moon (Chandra)
- Mercury (Budha)
- Venus (Shukra)
- Mars (Mangala)
- Jupiter (Guru or Brihaspati)
- Saturn (Shani)
- Uranus
- Neptune
- Pluto
- Rahu (mean north lunar node)
- Ketu (calculated exactly 180° opposite Rahu)

The classical Navagraha are represented by the Sun, Moon, Mercury, Venus, Mars,
Jupiter, Saturn, Rahu, and Ketu. Uranus, Neptune, and Pluto are included for
astrologers and software projects that also use the modern outer planets.

## Uses for Jyotish and astrology software

This open Vedic astrology dataset can be used to:

- look up daily sidereal planetary positions;
- study gochara and long-term planetary transits;
- build Vedic astrology, Jyotish, and horoscope applications;
- create planetary calendars, transit tables, and research visualizations;
- import historical ephemeris data into spreadsheets or databases;
- test astrology APIs and planetary position software; and
- analyze Rahu–Ketu, Saturn, Jupiter, and other graha movements over time.

The files contain daily planetary snapshots rather than complete natal charts.
They do not include houses, Ascendant (Lagna), nakshatras, dashas, aspects,
tithis, yogas, retrograde flags, or divisional charts. These can be calculated
separately from the supplied sidereal longitudes where appropriate.

## Explore planetary positions with Moon Dasha

Moon Dasha is a Vedic astrology platform with
interactive tools for exploring planetary transits, Jyotish concepts, and
astrological timing. While this repository is designed for downloading and
processing yearly ephemeris data, Moon Dasha provides a visual interface for
people who want to inspect planetary positions without working directly with
JSON or CSV files.

Use the free
[Moon Dasha Planetary Positions GUI](https://moondasha.com/planetary-positions)
to calculate the sidereal planetary positions for a selected date, time, and
location. The interface displays each planet's:

- zodiac sign and degrees within the sign;
- nakshatra and pada;
- speed in degrees per day;
- direct or retrograde motion; and
- absolute longitude in the 360° zodiac.

The page also presents the planetary data in a D1 (Lagna) chart. You can change
the ascendant to your own Ascendant or Moon sign to see which houses the
current transiting planets occupy in your chart. This is useful for checking
today's graha positions, studying past or future gochara, comparing transits
with a Janam Kundli, and learning how planets move through signs and
nakshatras.

## Data format

Planet positions are expressed as a zodiac sign plus decimal degrees within
that sign. Values are rounded to five decimal places.

Example JSON record:

```json
{
  "date": "2026-01-01",
  "Sun": {
    "sign": "Sagittarius",
    "degrees": 16.6229
  },
  "Moon": {
    "sign": "Taurus",
    "degrees": 16.56051
  },
  "Rahu": {
    "sign": "Aquarius",
    "degrees": 17.93459
  },
  "Ketu": {
    "sign": "Leo",
    "degrees": 17.93459
  }
}
```

The `degrees` value is between 0 and 30 and is measured within the named rashi
(zodiac sign). To convert it to an absolute sidereal longitude from 0° to 360°:

```text
absolute longitude = (zodiac sign index × 30) + degrees
```

Aries has index 0, Taurus 1, Gemini 2, and so on through Pisces at index 11.

## Calculation settings

- Zodiac system: sidereal (Nirayana)
- Ayanamsa: Lahiri
- Position type: geocentric apparent longitude
- Snapshot time: 12:00 at UTC+05:30, equivalent to 06:30 UTC
- Reference coordinates: 28.5622321° N, 77.197764° E
- Precision in published files: five decimal places within each sign

UTC+05:30 is treated as a fixed offset throughout the 1800–2200 date range,
not as a reconstruction of historical local civil time. The planetary
longitudes are geocentric, and the dataset does not contain houses or local
angles, so the reference coordinates do not change the published longitude
values.

## Download yearly ephemeris files

The repository provides one file per calendar year in each format:

```text
.
├── json/
│   ├── ephemeris_1800.json
│   ├── ...
│   └── ephemeris_2200.json
├── markdown/
│   ├── ephemeris_1800.md
│   ├── ...
│   └── ephemeris_2200.md
└── csv/
    ├── ephemeris_1800.csv
    ├── ...
    └── ephemeris_2200.csv
```

Leap years contain 366 daily records; other years contain 365.

### JSON ephemeris

Each yearly JSON file is an array of daily objects. Every planet has a full
zodiac sign name and its decimal degrees within that sign. JSON is suitable for
web applications, APIs, JavaScript, Python, and database imports.

### Markdown ephemeris

Each date is a level-two heading followed by all planetary positions using
three-letter zodiac abbreviations and decimal degrees. Markdown is convenient
for reading, documentation, static websites, and text search.

### CSV ephemeris

Each CSV row represents one date. Every planet has paired `BodySign` and
`BodyDegrees` columns. CSV is suitable for Excel, Google Sheets, data analysis,
and relational database imports.

## Open-data license

To the extent the dataset publisher holds copyright, database, or related
rights in this compilation, those rights are waived under the
[CC0 1.0 Universal Public Domain Dedication](https://creativecommons.org/publicdomain/zero/1.0/).

You may copy, modify, redistribute, combine, publish, and use the ephemeris
data for any purpose, including commercial astrology products, without asking
permission. Attribution is appreciated but not required.

CC0 applies only to rights held by the dataset publisher. It does not alter or
grant rights in third-party software, source data, names, or trademarks.

## Accuracy and disclaimer

Positions are rounded to five decimal places and represent one daily snapshot,
not a continuous planetary trajectory. Historical and far-future astronomical
calculations also depend on time-scale models and their uncertainties. Users
should independently verify values when greater precision is required.

The dataset is provided without warranties of accuracy, completeness, or
fitness for a particular purpose. It should not be used for navigation,
safety-critical decisions, or professional astronomical operations.

## Citation

Citation is optional under CC0. If you would like to credit the dataset, use:

```text
Vedic Astrology Ephemeris Dataset (1800–2200), CC0 1.0 Universal.
```
