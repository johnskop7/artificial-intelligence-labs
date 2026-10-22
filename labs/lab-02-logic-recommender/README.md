# Lab 2: Prolog-based movie recommendations

Open [movie_recommender.ipynb](movie_recommender.ipynb).

## Coverage

- Read and clean movie metadata and construct Prolog facts.
- Define similarity predicates for genres, director, actors, plot keywords, language, color, production companies/countries, and decade.
- Combine predicates into the five `find_sim_1` through `find_sim_5` rules stored in [db.pl](db.pl).
- Produce movie recommendations and weight them using user ratings.
- Compare precision, recall, and F1 over repeated random training-subset experiments.

The training helper calls `simple_recommender(movie)` with its original default `k=1`; the notebook's conclusions discuss an alternative using all five similarity levels. This behavior is preserved.

## Required files

Keep these files in the notebook's working directory:

| File | Role | Data rows |
| --- | --- | --- |
| [movies_metadata.csv](movies_metadata.csv) | Movie features | 4,803 |
| [train_ratings.csv](train_ratings.csv) | Training ratings | 100 |
| [test_ratings.csv](test_ratings.csv) | Test ratings | 141 |
| [db.pl](db.pl) | Composite similarity rules | — |

`path = './'` is active in the notebook. For local Jupyter, start from this directory, or make sure the notebook kernel uses it as the current directory.

## Local setup

Install **SWI-Prolog** for your OS. On an Ubuntu/Debian system with the package available:

```bash
sudo apt-get update
sudo apt-get install swi-prolog
```

From the repository root, with your Python environment activated:

```bash
python -m pip install -r labs/lab-02-logic-recommender/requirements.txt
cd labs/lab-02-logic-recommender
python -m jupyter lab
```

PySwip requires an accessible SWI-Prolog shared library. Restart the kernel after installing native/runtime dependencies if necessary. The original installation cell is commented out and references a Git branch/PPA; the repository does not enable or run it.

## Google Colab

Upload/open the notebook. Before its import cells, use a temporary setup cell in your Colab copy:

```python
!apt-get -qq update
!apt-get -qq install -y swi-prolog
%pip install pyswip pandas numpy matplotlib scikit-learn tqdm
from google.colab import files
files.upload()  # select all three CSVs and db.pl from this lab folder
```

The uploaded files are placed in the current Colab directory, matching `path = './'`. Run the original notebook cells in sequence. `db.pl` is not a standalone complete knowledge base: facts and supporting predicates are generated in the notebook before the recommender queries are used.
