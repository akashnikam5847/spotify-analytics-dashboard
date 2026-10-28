# Spotify Top 50 Analytics Dashboard (Power BI)

A 4-page Power BI report analysing the **Spotify Daily Top 50 (World)** chart from **18 May 2023 to 27 Nov 2024**: 27,800 chart entries, 794 distinct songs and 343 artists.

<!-- Add after exporting screenshots -->
![Overview](screenshots/page1.png)

## Business questions answered
- Which artists and songs dominate the global Top 50?
- How popular are explicit vs clean tracks?
- Do singles or albums chart better?
- How does average popularity change month by month?
- How long are chart songs, and how old are they when they chart?

## Dataset
`data/spotify-top-50-world.csv`: 27,800 rows, 11 columns (date, position, song, artist, popularity, duration_ms, album_type, total_tracks, release_date, is_explicit, album_cover_url). One row is one song's position on one day, so "chart appearances" is a row count and "songs" is a distinct count. No missing values.

**Data notes**
- `release_date` is mixed: 101 rows have year only and 4 have year-month, so it is rebuilt into a proper date in Power Query (`docs/power_query.m`).
- 182 rows have popularity = 0 (kept in the data).

## Tools
Power BI Desktop, Power Query (M), DAX, report navigation buttons, slicers.

## Key facts (checked against the CSV)
| Metric | Value |
|---|---|
| Chart entries | 27,800 |
| Distinct songs / artists | 794 / 343 |
| Average popularity | 89.6 |
| Average song length | 3.28 min |
| Explicit share of chart entries | 40.2% |
| Album vs single entries | 62.1% vs 37.8% |
| Most chart days (entries) | Taylor Swift (1,871), Billie Eilish (860), Sabrina Carpenter (736) |
| Most distinct songs charted | Taylor Swift (85), Travis Scott (30), Drake (27) |
| Longest-running songs | I Wanna Be Yours (548 days), Cruel Summer (517) |

Explicit tracks are 40% of the chart but are not more popular on average (89.5 vs 89.7 for clean tracks), and singles average higher popularity (91.9) than album tracks (88.3).

## Files
```
spotify-powerbi/
├── Spotify_Top50_Analytics.pbix
├── data/spotify-top-50-world.csv
├── screenshots/            (page screenshots)
├── docs/
│   ├── power_query.m
│   ├── dax_measures.md
│   └── dashboard_guide.md
└── README.md
```

## How to open
Install Power BI Desktop (Windows), open `Spotify_Top50_Analytics.pbix`. If it asks for the data source, Transform data > Data source settings and point it to `data/spotify-top-50-world.csv`.

## Author
Akash Nikam | Data Analytics | Pune, India
