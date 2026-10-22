# Data inventory

| Lab | File | Rows excluding header | Columns |
| --- | --- | --- | --- |
| 2 | `movies_metadata.csv` | 4,803 | 27 |
| 2 | `train_ratings.csv` | 100 | 6 |
| 2 | `test_ratings.csv` | 141 | 6 |
| 3 | `movies_metadata.csv` | 4,803 | 27 |
| 3 | `ratings.csv` | 2,374 | 3 |

Counts include the original unnamed index column. No CSV values, columns, or filenames were changed. The movie metadata files in Labs 2 and 3 have identical SHA-256 hashes; both are retained so each lab has its own complete input set.

Movie metadata contains titles, genre/plot attributes, cast/director information, production information, and numerical attributes. Lab 2's ratings include user/movie identifiers, title, rating, and timestamp. Lab 3's ratings contain an index column, movie ID, and rating.

The notebook assignment text describes the supplied movie datasets, but no separate definitive dataset license or source manifest was provided. This package preserves the provided inputs without assigning them a new license or inferring an upstream dataset version.

For paths, Lab 2 reads from its current directory. Lab 3's original code reads its data from a fixed Google Drive folder. Refer to each lab's README before running.
