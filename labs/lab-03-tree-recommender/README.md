# Lab 3: Movie recommendations with decision trees

Open [tree_recommender.ipynb](tree_recommender.ipynb).

## Coverage

1. Explore movie metadata and ratings, missing values, and class-conditional feature distributions.
2. Merge movie data with ratings and encode categorical/multivalued features.
3. Implement a CART classifier using Gini impurity and recursive binary splits.
4. Compare it with scikit-learn's decision tree using accuracy and training time; visualize learned trees.
5. Vary maximum depth and study generalization, then experiment with random forests and ensemble size.
6. Discuss precision/F1 and the earlier rule-based recommender.

## Inputs

| File | Role | Data rows |
| --- | --- | --- |
| [movies_metadata.csv](movies_metadata.csv) | Movie attributes | 4,803 |
| [ratings.csv](ratings.csv) | Movie ratings | 2,374 |

This lab's `ratings.csv` is a separate input from Lab 2's train/test files. The notebook creates its own train/test splits. Keep its data separate from Lab 2.

## Run the notebook unchanged in Google Colab

The original code mounts Google Drive and reads exactly:

```text
/content/drive/My Drive/Lab_DL_ex3_2023/movies_metadata.csv
/content/drive/My Drive/Lab_DL_ex3_2023/ratings.csv
```

1. Create a folder named `Lab_DL_ex3_2023` in the root of your Google Drive (My Drive).
2. Upload this lab's two CSVs into that folder.
3. Open/upload the notebook in Colab.
4. Run the Drive mount cell and authorize access to your Drive.
5. Run the remaining cells in order. Install any missing imports using the packages listed in the repository's requirements.

These steps preserve the notebook itself. Its existing outputs and embedded explanations remain included.

## Optional local workflow

Install the root requirements and open the notebook from this folder in Jupyter. In a separate working copy, skip the Colab Drive-mount cell and change the two loading lines to:

```python
movies_metadata = pd.read_csv("movies_metadata.csv")
ratings = pd.read_csv("ratings.csv")
```

The delivered notebook has not been edited to make these changes. Some cells save decision-tree plots as `out_<max_depth>.pdf` in the current working directory; those generated files are excluded by `.gitignore`.
