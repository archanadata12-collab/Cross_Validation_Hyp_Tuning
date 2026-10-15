# Hands on Machine Learning

A hands-on introduction to core machine learning techniques every data scientist should know. In the guided notebook you will validate models with cross-validation and tune both hyperparameters of ElasticNet with grid search and randomized search, on the California housing data. In the exercise you then apply the full workflow yourself to predict how far a patient's diabetes will progress over a year. Both are regressions, which is what the Friday project asks for.

## Learning Objectives

By the end of this repository, you should be able to:

- Follow the machine learning workflow from defining a goal to evaluating a model.
- Build a `Pipeline` with a `ColumnTransformer` that prepares numeric and categorical columns separately.
- Validate models reliably using K-fold cross-validation, and compare the spread of their fold scores.
- Tune the `alpha` and `l1_ratio` of ElasticNet with grid search and randomized search.
- Apply the full workflow end to end to build a regression model on a new problem.
- Compare a tuned model against a baseline, and read its residuals rather than only its score.

## Learning Path

> [!TIP]
> Start with the [**Machine Learning Workflow**](machine_learning_workflow.md) guide. It walks through every step of an ML project (define the goal, get the data, split, explore, model, evaluate) and gives you the map for what the notebooks practice.

The notebooks build on each other in order:

| File / Folder | Description |
|---|---|
| [**The Machine Learning Workflow**](machine_learning_workflow.md) | Step-by-step overview of an end-to-end ML project. Read this first. |
| [**1 - Cross-Validation & Hyperparameter Tuning**](1_cross_validation_hyperparameter_tuning.ipynb) | Evaluate linear regression and ElasticNet on polynomial features with cross-validation, then tune ElasticNet with grid and randomized search, on the California housing data. |
| [**2 - Exercise: Machine Learning**](2_exercise_machine_learning.ipynb) | Practice the whole workflow yourself, predicting diabetes progression. |

### Additional Folders and Files

| File / Folder | Description |
|---|---|
| [**Data**](data/) | `california_housing.csv` for the guided notebook: the California housing data from Tuesday, with the coordinates replaced by a categorical `location` column taken from the `ocean_proximity` column of [Aurélien Géron's edition](https://github.com/ageron/handson-ml2/tree/master/datasets/housing). `diabetes_progression.csv` for the exercise, which ships with scikit-learn. |
| [**Assets**](assets/) | Images used in the notebooks and the workflow guide. |
| [**Solutions**](solutions/) | Reference solutions. |
| [**pyproject.toml**](pyproject.toml) | Project configuration and dependencies. |
| [**uv.lock**](uv.lock) | Dependency lock file. |

## Setup

> [!NOTE]
> Throughout these steps, text in angle brackets like `<repo-name>` is a **placeholder**. Replace it including the `< >` brackets with your own value. For example, `cd <repo-name>` becomes `cd ds-hands-on-ml`.

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

This installs all dependencies and creates a virtual environment in (`.venv/`).

```bash
cd <repo-name>
uv sync
```

---


### 5. Open the Notebooks

> [!NOTE]
> Make sure you open VS Code from the project root so it automatically detects the environment created by `uv sync`.

Launch VS Code in the project root folder:

```bash
code .
```

Then open a notebook and select the Python environment created by `uv sync` as the kernel.

## References & Further Reading

- [**The Machine Learning Workflow**](machine_learning_workflow.md): The step-by-step guide in this repo, your starting point.
- [**Feature Engineering**](https://github.com/neuefische/ds-feature-engineering): Companion bootcamp repo to go deeper on feature engineering (imputation, encoding, binning, feature creation).
- [**Scikit-learn: ElasticNet**](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.ElasticNet.html): The model tuned in the guided notebook.
- [**Scikit-learn: Preprocessing data**](https://scikit-learn.org/stable/modules/preprocessing.html): The scaling and polynomial features from the feature engineering day, for reference.
- [**Scikit-learn: Cross-validation**](https://scikit-learn.org/stable/modules/cross_validation.html): Evaluating estimator performance and avoiding overfitting.
- [**Scikit-learn: Tuning hyperparameters**](https://scikit-learn.org/stable/modules/grid_search.html): Grid search, randomized search, and successive halving.