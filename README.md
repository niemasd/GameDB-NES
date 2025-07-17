# GameDB-NES
Nintendo Entertainment System (NES), part of [GameDB](https://github.com/niemasd/GameDB).

## Structured Downloads
* **[`NES.data.json`](https://github.com/niemasd/GameDB-NES/releases/latest/download/NES.data.json):** All data, structured in the JSON format
* **[`NES.data.tsv`](https://github.com/niemasd/GameDB-NES/releases/latest/download/NES.data.tsv):** All data, structured in the TSV format
* **[`NES.release_dates.pdf`](https://github.com/niemasd/GameDB-NES/releases/latest/download/NES.release_dates.pdf):** Histogram of release dates, stratified by region
* **[`NES.titles.json`](https://github.com/niemasd/GameDB-NES/releases/latest/download/NES.titles.json):** Mapping of serial numbers to game titles, structured in the JSON format

# Notes

## Uniquely Identifying Games

To my knowledge, it doesn't seem like the [NES ROM header](https://bheisler.github.io/post/nes-rom-parser-with-nom/) contains a uniquely-identifying serial number or game code: just information that's necessary for the actual execution of the game code. However, NES games are *very* small (the largest cartridge capacity was [1 MB](https://en.wikipedia.org/wiki/List_of_Nintendo_Entertainment_System_games#:~:text=Cartridges%20had%20storage%20sizes%20ranging%20from%2064%20Kilobits%20to%208%20Megabits)), so the CRC32 hash can be computed quickly. Further, folks commonly compress ROM dumps, and GZIP files contain the uncompressed file's CRC32 hash for validity checks, which can be easily read without recalculating from scratch (e.g. `gzip -lv game.nes.gz`).

# Sources

* [No-Intro](https://no-intro.org/)
