# Artificial Intelligence Labs

Three notebook-based projects for the **Artificial Intelligence** course at the **National Technical University of Athens (NTUA)**, completed in 2023 by **Ioannis Litsos** and **Achilleas Tsimichodimos**.

The labs move from search and adversarial planning to symbolic reasoning and supervised learning. Each folder contains an original notebook and the input files it needs. Notebook contents, outputs, embedded figures, and Greek explanations are preserved unchanged; only notebook filenames have been simplified.

## Projects

| Lab | Focus | Main topics | Notebook |
| --- | --- | --- | --- |
| 1 | Maze generation, pathfinding, and ghost avoidance | A*, Dijkstra, greedy best-first search, distance heuristics, alpha-beta search | [Maze search](labs/lab-01-search/maze_search.ipynb) |
| 2 | Logic-based movie recommendations | Prolog knowledge representation, similarity rules, user ratings, precision/recall/F1 | [Movie recommender](labs/lab-02-logic-recommender/movie_recommender.ipynb) |
| 3 | Learning movie preferences with trees | Data exploration, feature encoding, custom CART, decision trees, random forests | [Tree recommender](labs/lab-03-tree-recommender/tree_recommender.ipynb) |

### Lab 1: Search and adversarial agents

Generate random mazes with adjustable obstacle density and compare pathfinding strategies using path length and expanded-node counts. Explore Manhattan, Euclidean, and Chebyshev distance functions, then implement an alpha-beta agent that attempts to reach a goal while avoiding a ghost that follows its own A* path. The notebook also includes an interactive maze-drawing bonus section and embedded visualizations.

See the [Lab 1 guide](labs/lab-01-search/README.md).

### Lab 2: Symbolic movie recommender

Convert movie metadata into Prolog facts, define rules for shared genres, directors, actors, plot keywords, language, and production attributes, and combine these into five similarity levels. Build recommendations from movie characteristics and user ratings, then evaluate precision, recall, and F1 over different training-subset sizes.

Python handles data preparation and evaluation; **PySwip** connects Python to **SWI-Prolog**. The supplied `db.pl` contains composite similarity rules and is used together with facts and base predicates created inside the notebook.

See the [Lab 2 guide](labs/lab-02-logic-recommender/README.md).

### Lab 3: Decision-tree movie recommender

Explore movie metadata and ratings, merge and encode features, and implement a CART classifier with Gini-based splits. Compare its accuracy and training time with scikit-learn's `DecisionTreeClassifier`, visualize trees, and investigate tree depth. Extend the experiments to `RandomForestClassifier`, varying tree depth and ensemble size.

See the [Lab 3 guide](labs/lab-03-tree-recommender/README.md).

## Repository organization

- `labs/lab-01-search/`: notebook and guide; no input CSVs.
- `labs/lab-02-logic-recommender/`: notebook, `db.pl`, three CSVs, and guide.
- `labs/lab-03-tree-recommender/`: notebook, two CSVs, and guide.
- `requirements.txt`: shared Python dependencies.
- `docs/running-notebooks.md`: local Jupyter and Google Colab instructions.
- `docs/data.md`: dataset inventory and path conventions.
- `docs/provenance.json`: original filenames and SHA-256 checksums.
- `GITHUB_SETUP.md`: suggested repository description, topics, and upload steps.

Data stays within each lab to make the projects self-contained. The two copies of `movies_metadata.csv` are identical and are deliberately retained with their respective labs.

## Running the notebooks

**Google Colab** is the most direct option for Lab 1's interactive drawing section and Lab 3's existing Drive-based loading cells. Open or upload each notebook in Colab and follow its lab guide for the inputs. For local execution:

```bash
python -m venv .venv
# Linux / macOS
source .venv/bin/activate
# Windows PowerShell: .venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
python -m jupyter lab
```

Lab 2 additionally requires SWI-Prolog and its own requirements file. Lab 3's existing loading cells point to a specific Google Drive folder; simply putting CSVs next to the notebook does not satisfy those absolute paths. The guides explain both the unchanged Colab workflow and optional adjustments in a working copy.

See [running notebooks](docs/running-notebooks.md) before executing cells.

## Preservation and validation

All three notebooks, all five CSVs, and the Prolog file are byte-for-byte copies of the supplied working files. The nested Lab 2 submission archive was unpacked into usable notebook and Prolog files. No Python-script conversion or algorithm changes were made. Prior repository metadata and redundant nested ZIP containers are excluded from the new package.

Packaging checks cover notebook structure, CSV inventory, relative documentation links, source-file checksums, and ZIP integrity. Full notebook execution and dependency compatibility were not validated. Saved notebook outputs reflect the original runs; randomized experiments may produce different results when rerun.

## Credits

The notebooks identify **Ioannis Litsos** and **Achilleas Tsimichodimos** as collaborators. Assignment text and supplied scaffolding remain within the original notebooks. No repository-wide license was supplied, and no new license is assigned to the notebooks, course materials, or datasets.
