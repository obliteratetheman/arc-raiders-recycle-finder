# ARC Raiders Recycle Finder

[![download button](https://i.imgur.com/3Dm4p65.png)](https://tinyurl.com/yztryhjh)

This project is a starter kit for building a recycling helper website for
**ARC Raiders** players. It lets players search for a material or item and
see which items they can recycle to maximise their yield. The frontend
is built with **Next.js 14** and **Tailwind CSS**, and the data is
preprocessed from the [RaidTheory](https://github.com/RaidTheory/arcraiders-data)
community dataset.

## Getting Started

### 1 – Install dependencies

```
npm install
```

### 2 – Import the RaidTheory data

This repository ships with a tiny sample dataset so the app can run
immediately. For a complete experience you should  the
**`arcraiders-data`** repository and drop the item JSON files into
`data/raidtheory/items`. Each JSON file in that folder should contain a
single item object (as in the RaidTheory repo). Then run:

```
npm run build:data
```

The script will read all of the raw item files, normalise their
structure, and emit a single `src/data/items.json` used at runtime. It
also rewrites each `imageFilename` to a local path. Place the
corresponding PNGs in `public/images/items` so they load quickly.

### 3 – Run locally

```
npm run dev
```

Visit `http://localhost:3000` to explore the app. The search bar will
autofill as you type and clicking a suggestion will take you to a
details page showing the best items to recycle for that material.

### 4 – Build for production

```
npm run build && npm start
```

## Features

* **Search with autocomplete** – fuzzy matching across item names
* **Ranked results** – see which items yield the most units per
  recycle, optionally per kilogram
* **Comprehensive item details** – view descriptions, rarity, type,
  value, weight, stack size and update date
* **Data driven** – refresh the data by re-running the build script when
  the game updates

## License

This project is provided under the MIT licence. Original ARC Raiders
game data and imagery are © Embark Studios AB; see
[RaidTheory](https://github.com/RaidTheory/arcraiders-data) for
attribution.
