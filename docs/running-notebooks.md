# Running the original notebooks

## Preservation policy

The repository contains the original notebook bytes under descriptive filenames. It does not clear outputs, rewrite cells, relocate data-loading code, or convert notebooks to Python scripts. Changes suggested below are optional runtime cells or edits to a separate working copy.

## Local Jupyter

Create and activate a Python 3 virtual environment, install `requirements.txt`, and launch JupyterLab. The requirements are inferred from notebook imports, not a version-locked reconstruction of the 2023 runtime. They do not guarantee compatibility with every newer Python/package release. No runtime has been advertised as tested.

- **Lab 1:** the core maze/search sections use NumPy, Matplotlib, Pillow, and IPython. The drawing section specifically requires Colab.
- **Lab 2:** use its own requirements file and install SWI-Prolog separately. Start the kernel in the lab folder, where the notebook expects all three CSVs and `db.pl`.
- **Lab 3:** the original notebook imports Colab and reads absolute Drive paths. For an unchanged run, use Colab; for local use, see the lab guide's two path edits and skip the Drive mount in a copy.

## Google Colab

Use Colab's **File → Upload notebook** to open the desired `.ipynb`. After publishing the repository, Colab's GitHub tab can also locate the notebook by repository URL. Uploading a notebook alone does not upload its neighboring CSV or Prolog files.

| Lab | Additional setup |
| --- | --- |
| 1 | No CSVs; respond to interactive maze-drawing cells when reached |
| 2 | Install SWI-Prolog/PySwip and upload the three CSVs plus `db.pl` to the current directory |
| 3 | Put the two CSVs in My Drive's `Lab_DL_ex3_2023` folder and run the existing mount cell |

A GPU is not required by the code inspected. Runtime duration depends on maze sizes, experiment repetitions, and tree settings. Saved outputs can be read without executing anything; reruns may differ because some experiments use randomness without a single fixed seed for the entire notebook.

## Execution order

Start with a fresh kernel/session and follow cells in order. Definitions and in-memory state are shared across cells, especially the Prolog facts and rules in Lab 2. Restart and run the setup sequence again if that state becomes inconsistent. Stop before Lab 1's drawing cells if you want only the non-interactive experiments.

The original notebooks contain assignment text, supplied scaffolding, solutions, and discussion together. Documentation describes their scope, without claiming that every bonus prompt has been completed or validating the original algorithms.
