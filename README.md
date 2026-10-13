# Clustering

A hands-on introduction to unsupervised learning with clustering. You will compare the main clustering algorithms (K-Means, hierarchical clustering, DBSCAN) on synthetic data, then apply them to three realistic use cases: segmenting mall customers, compressing the colours of a satellite image, and grouping texts by their word embeddings.

## Learning Objectives

By the end of this repository, you should be able to:

- Compare K-Means, hierarchical clustering, and DBSCAN, and recommend a suitable algorithm for a given dataset.
- Tune the key hyperparameters (`k`, `linkage`, `eps`, `min_samples`) and estimate the number of clusters from an elbow plot, silhouette analysis, or a dendrogram.
- Segment customers with K-Means and profile each cluster to recommend a marketing target.
- Apply clustering to image pixels for colour quantisation and land-cover segmentation.
- Construct text embeddings (word2vec, GloVe) and cluster documents by topic.

## Learning Path

Work through the notebooks in this order:

| File / Folder | Description |
|---|---|
| [**1 - Comparing Clustering Algorithms**](1_comparing_clustering_algorithms.ipynb) | How K-Means, hierarchical clustering, and DBSCAN work, with their strengths and limitations. |
| [**2 - Clustering for Customer Segmentation**](2_clustering_for_customer_segmentation.ipynb) | Segmenting mall customers with K-Means and interpreting the clusters. |
| [**3 - Clustering Images**](3_clustering_images.ipynb) | Colour quantisation of a satellite image with K-Means. |
| [**4 - Bonus: Clustering Texts**](4_bonus_clustering_texts.ipynb) | Clustering texts with word2vec and GloVe embeddings. |

### Additional Folders and Files

| File / Folder | Description |
|---|---|
| [**Data**](data.zip) | The datasets, bundled as a zip (unzip it during setup). |
| [**Assets**](assets/) | Images used by the notebooks; notebook 3 also saves its output images here. |
| [**Solutions**](solutions/) | Reference solutions. |
| [**pyproject.toml**](pyproject.toml) | Project configuration. |
| [**uv.lock**](uv.lock) | Dependency lock file. |

## Setup

> [!NOTE]
> Throughout these steps, text in angle brackets like `<repo-name>` is a **placeholder**. Replace it including the `< >` brackets with your own value. For example, `cd <repo-name>` becomes `cd ds-clustering`.

### 1. Create the Repository from the Template

Click **Use this template** on GitHub.

When creating the repository:

- Set yourself as the **Owner**
- Choose a repository name
- Disable **Include all branches**
- Click **Create repository**

> [!IMPORTANT]
> If you are working in pairs or groups, only **one person** should complete this step.

---

### 2. Add Collaborators (Pairs/Groups Only)

If working with teammates:

1. Open the repository on GitHub
2. Go to **Settings → Collaborators**
3. Add your teammates as collaborators
4. Share the repository link with your team

Teammates should accept the invitation before continuing.

---

### 3. Clone the Repository

Copy the SSH URL from the **Code** button on GitHub, then run:

```bash
git clone <copied-ssh-url>
```

The copied SSH URL will look like `git@github.com:<your-username>/<repo-name>.git`.

---

### 4. Move into the Project Folder and Install Dependencies

This installs all dependencies and creates a virtual environment in `.venv/`.

```bash
cd <repo-name>
uv sync
```

---

### 5. Unzip the Data

The datasets are bundled in `data.zip`. Extract them into a `data/` folder before running the notebooks. This command uses the environment from `uv sync`:

```bash
uv run python -c "import zipfile; zipfile.ZipFile('data.zip').extractall()"
```

---

### 6. Open the Notebooks

> [!NOTE]
> Make sure you open VS Code from the project root so it automatically detects the environment created by `uv sync`.

Launch VS Code in the project root folder:

```bash
code .
```

Then open a notebook and select the Python environment created by `uv sync` as the kernel.

## References & Further Reading

- [**Scikit-learn: Clustering**](https://scikit-learn.org/stable/modules/clustering.html): User guide covering the clustering algorithms in scikit-learn and how to evaluate them.
- [**Scikit-learn: Comparing Clustering Algorithms**](https://scikit-learn.org/stable/auto_examples/cluster/plot_cluster_comparison.html): The classic comparison plot behind notebook 1.
- [**Visualizing K-Means Clustering**](https://www.naftaliharris.com/blog/visualizing-k-means-clustering/): Interactive step-by-step demo of centroid assignment and updates.
- [**Visualizing DBSCAN Clustering**](https://www.naftaliharris.com/blog/visualizing-dbscan-clustering/): Interactive demo of how `eps` and `min_samples` shape density-based clusters.
- [**Gensim: Word2Vec**](https://radimrehurek.com/gensim/models/word2vec.html): Documentation for the word-embedding model used in the bonus text-clustering notebook.
- [**Mall Customer Segmentation Data on Kaggle**](https://www.kaggle.com/datasets/vjchoudhary7/customer-segmentation-tutorial-in-python): The dataset behind notebook 2, with community notebooks applying segmentation in practice.