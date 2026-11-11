# BookRank open data

Bulk files from [BookRank](https://openbookrank.com/en/open-data), a free site that ranks books by reader ratings from open sources.

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.24129205.svg)](https://doi.org/10.5281/zenodo.24129205)

Snapshot 2026-10-31: 14,213 books (4,866 with a score), 1,689 series, 1,488 authors, 49 ranking categories.

## Files

| File | What it holds |
|---|---|
| `books.csv` | One row per work: score, number of ratings, confidence, popularity percentile, best rank and category, series and position, Wikidata, Open Library and ISBN-13 identifiers, page URL |
| `rankings.csv` | Rank of each scored book in each category |
| `series.csv` | One row per series: author, number of volumes, series score and ratings, reading-order page URL |
| `authors.csv` | One row per author: Wikidata ID, number of ranked books and series, page URL |
| `identifiers.csv` | Crosswalk between BookRank IDs, ISBN-13, Wikidata and Open Library |
| `datapackage.json` | Frictionless Data descriptor |

The NDJSON version of `books.csv` is on [Zenodo](https://doi.org/10.5281/zenodo.24129205) and [openbookrank.com/open-data/books.ndjson](https://openbookrank.com/open-data/books.ndjson).

## Method

Confidence is ratings ÷ (ratings + prior weight). A book with too few ratings is listed but not scored. Full method: [openbookrank.com/en/methodology](https://openbookrank.com/en/methodology).

Averages from individual rating sources are not in these files; they follow those sources' terms and appear only on each book's own page.

## Licence

- Scores, ranks and confidence: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Credit: “BookRank (openbookrank.com)”.
- Identifier crosswalk (`identifiers.csv`): [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/).

## Other copies and the live API

- Zenodo: [10.5281/zenodo.24129205](https://doi.org/10.5281/zenodo.24129205)
- Hugging Face: [grynien/bookrank](https://huggingface.co/datasets/grynien/bookrank)
- Kaggle: [BookRank: Book Scores, Rankings and Series](https://www.kaggle.com/datasets/marcingrynienko/bookrank-book-scores-rankings-and-series)
- Static JSON API with an OpenAPI 3.1 spec: [openbookrank.com/api/v1/openapi.json](https://openbookrank.com/api/v1/openapi.json)

These files are a snapshot; the site updates weekly.
