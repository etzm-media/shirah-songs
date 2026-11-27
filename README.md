# Shirah songs

Song list and slides for the **Shirah** song presenter. Every Shirah install
pulls this repository when it starts, so a push here updates every church PC.

## Layout

- `songs.json`: the song list, one song per line.
- `PPTs/<number>.pptx`: the slides for each song. The file name must equal the song's `number`.

## Song fields

| field | example | notes |
|---|---|---|
| `number` | `"45"`, `"MAL5"`, `"NEW1"` | Unique. Searchable. Names the PPT file. |
| `name` | `"Aanantha Thuthi Oli Kaekum"` | Tanglish title (phonetic search). |
| `alias` | `"Anantha Thuthi"` | Optional alternate title (also searched). |
| `tamilName` | `"ஆனந்த துதி ஒலி கேட்கும்"` | Optional, shown under the name. |
| `chord` | `"C# Major"` | Optional, `""` when unknown. |
| `category` | `"New"` | Any name: `Tamil`, `Malayalam`, `New`, `Tamil Chorus`, … Each category becomes a filter chip in the app (capitalisation doesn't matter). If missing, the song's `language` is used. |
| `language` | `"tamil"` | What the song is sung in: `tamil`, `malayalam`, `telugu`, `hindi`, `english`, … Keep it on every song, whatever its category. |

## Adding / changing / removing a song

1. Add, replace or delete `PPTs/<number>.pptx`.
2. Add, edit or delete the matching line in `songs.json` (keep it valid JSON).
3. Commit and push to `main`. Every Shirah install picks it up at its next start.

A song listed without a PPT shows as **No slides** in the app.
Do **not** use Git LFS: the app downloads files directly and checks them against their git hashes.
