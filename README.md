# 30 Days of Scikit-learn 🚀

> From the Scikit-learn estimator API to a complete, production-oriented ML workflow in 30 days.

---

## Introduction

[Scikit-learn](https://scikit-learn.org/stable/) is an open-source Python library for classical machine learning. It provides consistent tools for data preprocessing, supervised and unsupervised learning, model selection, and evaluation. Its approachable estimator API and composable workflow tools make it useful both for learning ML fundamentals and for building maintainable applications.

Over these 30 days, I will move from the estimator API and core algorithms to preprocessing, validation, model selection, and an end-to-end inference workflow. The goal is to understand both the algorithms and how to use Scikit-learn's API correctly, then apply that knowledge to complete ML pipelines.

**Learning rules**

- Study the linked documentation for the day's topic, then write and run the examples.
- Complete the mini task without copying a finished solution.
- Keep preprocessing and model selection inside leakage-safe training workflows.
- Record useful observations, limitations, and questions in that day's folder.
- Mark a day complete only after finishing its practice and mini task.

## Learning Goals

- [ ] Understand the Scikit-learn estimator API
- [ ] Understand `fit()`, `predict()`, `transform()`, and `fit_transform()`
- [ ] Perform train/test splitting
- [ ] Build regression, classification, and clustering models
- [ ] Perform preprocessing and handle missing values
- [ ] Encode categorical features and scale numerical features
- [ ] Build `Pipeline` and use `ColumnTransformer`
- [ ] Evaluate ML models and perform cross-validation
- [ ] Perform hyperparameter tuning
- [ ] Understand overfitting and underfitting
- [ ] Perform feature engineering and feature selection
- [ ] Use PCA
- [ ] Perform anomaly detection
- [ ] Save and load trained models
- [ ] Build an end-to-end ML project
- [ ] Deploy the final model using FastAPI

## Official Resources

All Scikit-learn references in this README point to the official documentation.

1. [Official Documentation](https://scikit-learn.org/stable/)
2. [Getting Started](https://scikit-learn.org/stable/getting_started.html)
3. [User Guide](https://scikit-learn.org/stable/user_guide.html)
4. [API Reference](https://scikit-learn.org/stable/modules/classes.html)
5. [Examples](https://scikit-learn.org/stable/auto_examples/index.html)
6. [Installation Guide](https://scikit-learn.org/stable/install.html)

## Roadmap at a Glance

| Phase | Days | Focus |
|:---:|:---:|---|
| 1 | 1–4 | Estimator API, data, regression, and regression metrics |
| 2 | 5–11 | Core supervised classification algorithms |
| 3 | 12–16 | Scaling, encoding, imputation, and composable preprocessing |
| 4 | 17–21 | Classification evaluation, cross-validation, and tuning |
| 5 | 22–26 | Regularization, clustering, dimensionality reduction, and anomalies |
| 6 | 27–28 | Feature engineering, feature selection, and model persistence |
| 7 | 29–30 | End-to-end project, revision, and portfolio |

**Skill progression**

```text
Day 1  Estimator API
  ↓
Day 11 Core supervised models
  ↓
Day 16 Leakage-safe preprocessing pipelines
  ↓
Day 21 Evaluation and model selection
  ↓
Day 28 Persisted inference workflow
  ↓
Day 30 Portfolio-ready ML API
```

## 30-Day Roadmap

Each day is a focused learning unit. Keep the exercises small, save runnable code, and record decisions and results in that day's folder. Statuses start as **Not Started** and should be updated only after doing the work.

### Day 1 — Scikit-learn Introduction and Estimator API

**Topics**
- Estimators, transformers, predictors, and the fit/predict workflow
- Input convention: feature matrix `X` and target `y`

**Scikit-learn APIs**
- `sklearn`, `sklearn.base.BaseEstimator`, `sklearn.datasets`
- `fit()`, `predict()`, `transform()`

**What I should understand**
- Estimators expose a consistent interface, while their learned state is created by `fit()`. Different estimators can therefore be swapped and composed through common APIs.

**Practice**
- Inspect `X.shape` and `y.shape` for a built-in dataset.
- Fit a simple estimator and inspect its learned attributes.
- Compare the methods available on an estimator and a transformer.

**Mini Task**
- Create a notebook that loads a dataset, fits one model, predicts, and explains each step.

**Official Documentation:** [Getting Started](https://scikit-learn.org/stable/getting_started.html) · [API Reference](https://scikit-learn.org/stable/modules/classes.html)

**Status:** ⬜ Not Started

### Day 2 — Datasets and Train/Test Splitting

**Topics**
- Built-in toy datasets and dataset loaders
- Features, targets, stratification, reproducibility, and held-out testing

**Scikit-learn APIs**
- `load_iris`, `load_diabetes`, `fetch_openml`
- `train_test_split`

**What I should understand**
- A test set estimates performance on unseen data. Split before fitting any learned preprocessing; use stratification for classification when appropriate.

**Practice**
- Load a classification and a regression dataset; identify `X` and `y`.
- Create train/test splits with a fixed `random_state`.
- Compare class proportions before and after a stratified split.

**Mini Task**
- Save a short dataset card with the source, target, row/feature counts, and split strategy.

**Official Documentation:** [Loading datasets](https://scikit-learn.org/stable/datasets.html) · [`train_test_split`](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.train_test_split.html)

**Status:** ⬜ Not Started

### Day 3 — Linear Regression

**Topics**
- Regression as prediction of a continuous target
- Linear relationship, coefficients, intercept, and residuals

**Scikit-learn APIs**
- `LinearRegression`
- `fit()`, `predict()`

**What I should understand**
- Linear regression learns coefficients that minimize residual sum of squares. Coefficients describe the fitted model and should be interpreted with feature units and relationships in mind.

**Practice**
- Fit `LinearRegression` on a regression dataset.
- Compare predictions with actual target values in a small table.
- Inspect coefficients and residuals; try a one-feature model versus a multi-feature model.

**Mini Task**
- Build a reusable script that trains a linear regression model and reports predictions for held-out rows.

**Official Documentation:** [`LinearRegression`](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html) · [Linear models](https://scikit-learn.org/stable/modules/linear_model.html)

**Status:** ⬜ Not Started

### Day 4 — Regression Metrics: MAE, MSE, RMSE, R²

**Topics**
- Absolute and squared errors
- Error units, outlier sensitivity, and baseline comparisons

**Scikit-learn APIs**
- `mean_absolute_error`, `mean_squared_error`, `root_mean_squared_error`, `r2_score`

**What I should understand**
- MAE is an average absolute error; MSE squares errors and penalizes large errors more; RMSE returns an error in the target's units; R² compares residual error with a mean-prediction baseline and can be negative.

**Practice**
- Calculate all four metrics from the same held-out predictions.
- Compare a model with a simple mean-prediction baseline.
- Add an outlier to a small example and observe how MAE and MSE change.

**Mini Task**
- Write a function that reports regression metrics with clear units and a one-sentence interpretation.

**Official Documentation:** [Regression metrics](https://scikit-learn.org/stable/modules/model_evaluation.html#regression-metrics) · [`mean_squared_error`](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.mean_squared_error.html)

**Status:** ⬜ Not Started

### Day 5 — Logistic Regression

**Topics**
- Classification probabilities and decision thresholds
- Binary and multiclass classification
- Regularization as a way to constrain model complexity

**Scikit-learn APIs**
- `LogisticRegression`
- `predict()`, `predict_proba()`, `decision_function()`

**What I should understand**
- Despite its name, logistic regression is a classifier. Class predictions depend on a decision rule; probability estimates and thresholds can be useful when the costs of errors differ.

**Practice**
- Fit a binary classifier and inspect predicted classes and probabilities.
- Compare predictions at the default threshold with a chosen alternative threshold.
- Fit a multiclass example and inspect class ordering.

**Mini Task**
- Train a logistic regression baseline and document the threshold and metric used.

**Official Documentation:** [`LogisticRegression`](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html)

**Status:** ⬜ Not Started

### Day 6 — K-Nearest Neighbors

**Topics**
- Distance-based prediction and neighborhood size
- Classification versus regression
- The influence of feature scales and distance choices

**Scikit-learn APIs**
- `KNeighborsClassifier`, `KNeighborsRegressor`

**What I should understand**
- KNN predicts from nearby training examples. Distance calculations are sensitive to feature scales, and the choice of neighbors affects the bias/variance trade-off.

**Practice**
- Train KNN with several neighbor counts.
- Compare predictions before and after scaling numeric features.
- Inspect the effect of `weights="uniform"` and `weights="distance"`.

**Mini Task**
- Plot validation score against neighbor count and explain the trend.

**Official Documentation:** [Nearest Neighbors](https://scikit-learn.org/stable/modules/neighbors.html) · [`KNeighborsClassifier`](https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsClassifier.html)

**Status:** ⬜ Not Started

### Day 7 — Decision Trees

**Topics**
- Recursive feature splits and tree depth
- Classification and regression trees
- Interpretability and overfitting controls

**Scikit-learn APIs**
- `DecisionTreeClassifier`, `DecisionTreeRegressor`, `plot_tree`

**What I should understand**
- A tree partitions feature space into regions. Deep trees can fit training data closely, so depth and leaf-size constraints are useful controls.

**Practice**
- Fit shallow and deeper trees; compare train and validation scores.
- Visualize a small tree.
- Inspect `feature_importances_` and discuss its limitations.

**Mini Task**
- Create a compact tree model card describing its depth, key split features, and limitations.

**Official Documentation:** [Decision Trees](https://scikit-learn.org/stable/modules/tree.html) · [`DecisionTreeClassifier`](https://scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeClassifier.html)

**Status:** ⬜ Not Started

### Day 8 — Random Forest

**Topics**
- Bagging, bootstrap samples, and ensembles of trees
- Random feature subsets and model variance

**Scikit-learn APIs**
- `RandomForestClassifier`, `RandomForestRegressor`

**What I should understand**
- A random forest averages or votes across many randomized trees. This often improves stability compared with a single tree, but performance and interpretability still depend on data and settings.

**Practice**
- Compare a single tree with a random forest on the same split.
- Vary `n_estimators` and `max_features`.
- Compare impurity-based feature importance with permutation importance.

**Mini Task**
- Record model performance, training time, and the trade-offs versus the single-tree baseline.

**Official Documentation:** [Forests of randomized trees](https://scikit-learn.org/stable/modules/ensemble.html#forests-of-randomized-trees) · [`RandomForestClassifier`](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html)

**Status:** ⬜ Not Started

### Day 9 — Gradient Boosting

**Topics**
- Sequential additive ensembles
- Learning rate, number of boosting stages, and tree complexity

**Scikit-learn APIs**
- `GradientBoostingClassifier`, `GradientBoostingRegressor`, `HistGradientBoostingClassifier`, `HistGradientBoostingRegressor`

**What I should understand**
- Boosting builds learners sequentially to improve the current ensemble. Learning rate and number/complexity of stages interact, so evaluate settings using validation data rather than assuming one configuration is best.

**Practice**
- Compare a gradient boosting model with a random forest.
- Change `learning_rate` and `n_estimators` together.
- Inspect validation performance as model complexity changes.

**Mini Task**
- Choose a boosting baseline using a documented validation strategy.

**Official Documentation:** [Ensemble methods](https://scikit-learn.org/stable/modules/ensemble.html#gradient-boosting) · [`GradientBoostingClassifier`](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.GradientBoostingClassifier.html)

**Status:** ⬜ Not Started

### Day 10 — Naive Bayes

**Topics**
- Bayes' rule and conditional independence assumption
- Gaussian, multinomial, and Bernoulli variants

**Scikit-learn APIs**
- `GaussianNB`, `MultinomialNB`, `BernoulliNB`

**What I should understand**
- Naive Bayes applies Bayes' rule with a simplifying feature-independence assumption. Select a variant that fits the feature representation; it is a useful baseline, not a guarantee of calibrated probabilities or best performance.

**Practice**
- Fit `GaussianNB` on continuous features.
- Use `MultinomialNB` on non-negative count-like features.
- Compare a Naive Bayes baseline with logistic regression using the same split.

**Mini Task**
- Write a short note explaining why the chosen Naive Bayes variant fits the data.

**Official Documentation:** [Naive Bayes](https://scikit-learn.org/stable/modules/naive_bayes.html)

**Status:** ⬜ Not Started

### Day 11 — Support Vector Machines

**Topics**
- Maximum-margin classification
- Kernels, regularization parameter `C`, and `gamma`
- Margin scores versus probability estimates

**Scikit-learn APIs**
- `SVC`, `LinearSVC`, `SVR`

**What I should understand**
- SVMs learn separating boundaries, with kernels enabling nonlinear boundaries. Scale-sensitive SVM workflows generally need scaling fitted on training data; probability estimation may require additional computation.

**Practice**
- Compare a linear SVM and an RBF-kernel SVM.
- Scale features inside a `Pipeline` and compare against an unscaled experiment.
- Explore the effect of `C` and `gamma` using validation data.

**Mini Task**
- Train an SVM baseline and document its kernel, scaling workflow, and selected metrics.

**Official Documentation:** [Support Vector Machines](https://scikit-learn.org/stable/modules/svm.html) · [`SVC`](https://scikit-learn.org/stable/modules/generated/sklearn.svm.SVC.html)

**Status:** ⬜ Not Started

### Day 12 — Feature Scaling: StandardScaler and MinMaxScaler

**Topics**
- Standardization and min-max scaling
- Scale-sensitive versus tree-based workflows
- Fitting transformations without leaking test data

**Scikit-learn APIs**
- `StandardScaler`, `MinMaxScaler`

**What I should understand**
- Scaling changes feature ranges or distributions, not the underlying information. Whether it is useful depends on the estimator and data; fit the scaler on training data only, preferably within a pipeline.

**Practice**
- Compare feature distributions before and after both scalers.
- Compare KNN or SVM scores with and without scaling.
- Verify that a scaler's learned statistics come from the training split only.

**Mini Task**
- Build a scaler-plus-classifier `Pipeline` and test it on a held-out set.

**Official Documentation:** [Preprocessing data](https://scikit-learn.org/stable/modules/preprocessing.html) · [`StandardScaler`](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.StandardScaler.html) · [`MinMaxScaler`](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.MinMaxScaler.html)

**Status:** ⬜ Not Started

### Day 13 — Categorical Encoding: OneHotEncoder and OrdinalEncoder

**Topics**
- Nominal versus ordinal categories
- Unknown categories at inference time
- Sparse one-hot output

**Scikit-learn APIs**
- `OneHotEncoder`, `OrdinalEncoder`

**What I should understand**
- One-hot encoding represents categories without implying an order. Ordinal encoding maps categories to integers and is appropriate when that ordering is meaningful and supplied intentionally.

**Practice**
- Encode a nominal feature using `OneHotEncoder`.
- Encode an ordered feature using an explicit category order.
- Configure and test behavior for categories not seen during fitting.

**Mini Task**
- Create a small preprocessing example that handles both nominal and ordered columns.

**Official Documentation:** [Encoding categorical features](https://scikit-learn.org/stable/modules/preprocessing.html#encoding-categorical-features) · [`OneHotEncoder`](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.OneHotEncoder.html) · [`OrdinalEncoder`](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.OrdinalEncoder.html)

**Status:** ⬜ Not Started

### Day 14 — Missing Value Handling: SimpleImputer

**Topics**
- Missingness and its potential meaning
- Mean, median, most-frequent, and constant strategies
- Missing indicators

**Scikit-learn APIs**
- `SimpleImputer`, `MissingIndicator`

**What I should understand**
- Imputation replaces missing values using a rule learned from training data. The choice should reflect feature type and context; imputation does not automatically remove bias caused by the missingness process.

**Practice**
- Compare mean and median imputation on a numeric column.
- Impute a categorical column with its most frequent value or a constant.
- Check that a missingness indicator can preserve information about absent values.

**Mini Task**
- Add imputation to a pipeline and verify it works with missing values in the validation data.

**Official Documentation:** [Imputation of missing values](https://scikit-learn.org/stable/modules/impute.html) · [`SimpleImputer`](https://scikit-learn.org/stable/modules/generated/sklearn.impute.SimpleImputer.html)

**Status:** ⬜ Not Started

### Day 15 — Pipeline

**Topics**
- Chaining transformations and an estimator
- Reproducible fit/predict workflow
- Pipeline parameters and leakage prevention

**Scikit-learn APIs**
- `Pipeline`, `make_pipeline`

**What I should understand**
- A pipeline fits preprocessing steps on the training data and applies the same learned transformations before prediction. It also lets validation and model selection evaluate the entire workflow.

**Practice**
- Chain a scaler and classifier in a pipeline.
- Fit and predict using the pipeline rather than separate objects.
- Access and update a step parameter using the `step__parameter` convention.

**Mini Task**
- Refactor one previous day's workflow into a single pipeline and compare its predictions.

**Official Documentation:** [Pipelines and composite estimators](https://scikit-learn.org/stable/modules/compose.html) · [`Pipeline`](https://scikit-learn.org/stable/modules/generated/sklearn.pipeline.Pipeline.html)

**Status:** ⬜ Not Started

### Day 16 — ColumnTransformer

**Topics**
- Applying different transformations to different columns
- Numeric and categorical preprocessing branches
- Composing column processing with a model pipeline

**Scikit-learn APIs**
- `ColumnTransformer`, `make_column_selector`

**What I should understand**
- Real datasets often mix numeric and categorical columns. `ColumnTransformer` applies appropriate transformations by column, and can be combined with a final estimator in a pipeline.

**Practice**
- Build separate numeric-imputation/scaling and categorical-imputation/encoding branches.
- Fit a combined preprocessing-and-classifier pipeline.
- Inspect transformed feature names where supported by the configured transformers.

**Mini Task**
- Create a reusable mixed-type preprocessing pipeline for a tabular dataset.

**Official Documentation:** [Column Transformer](https://scikit-learn.org/stable/modules/compose.html#columntransformer-for-heterogeneous-data) · [`ColumnTransformer`](https://scikit-learn.org/stable/modules/generated/sklearn.compose.ColumnTransformer.html)

**Status:** ⬜ Not Started

### Day 17 — Classification Metrics: Accuracy, Precision, Recall, and F1

**Topics**
- Confusion-matrix-derived metrics
- Positive class, averaging choices, and class imbalance

**Scikit-learn APIs**
- `accuracy_score`, `precision_score`, `recall_score`, `f1_score`, `classification_report`

**What I should understand**
- Accuracy is the fraction correct. Precision measures correctness among predicted positives; recall measures coverage of actual positives; F1 is their harmonic mean. Choose metrics based on error costs and class distribution.

**Practice**
- Calculate metrics from held-out predictions.
- Compare metrics for a deliberately imbalanced example.
- Try binary and multiclass `average` choices and interpret what is aggregated.

**Mini Task**
- Produce a classification report and explain which metric best fits a stated use case.

**Official Documentation:** [Classification metrics](https://scikit-learn.org/stable/modules/model_evaluation.html#classification-metrics) · [`classification_report`](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.classification_report.html)

**Status:** ⬜ Not Started

### Day 18 — Confusion Matrix and ROC-AUC

**Topics**
- True/false positives and negatives
- Threshold-dependent decisions versus threshold-independent ranking
- ROC curve and area under the curve

**Scikit-learn APIs**
- `confusion_matrix`, `ConfusionMatrixDisplay`, `roc_curve`, `roc_auc_score`

**What I should understand**
- A confusion matrix counts prediction outcomes at a chosen threshold. ROC-AUC evaluates ranking across thresholds, but can be misleading on highly imbalanced data and does not select an operational threshold by itself.

**Practice**
- Plot a confusion matrix and explain each cell.
- Plot an ROC curve from scores or probabilities.
- Compare ROC-AUC with precision/recall behavior for an imbalanced dataset.

**Mini Task**
- Recommend a threshold for a fictional decision scenario and state the trade-off.

**Official Documentation:** [Model evaluation](https://scikit-learn.org/stable/modules/model_evaluation.html) · [`roc_auc_score`](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.roc_auc_score.html)

**Status:** ⬜ Not Started

### Day 19 — Cross-Validation

**Topics**
- Why a single split can be unstable
- K-fold and stratified folds
- Choosing a splitter that respects the data structure

**Scikit-learn APIs**
- `cross_val_score`, `cross_validate`, `KFold`, `StratifiedKFold`

**What I should understand**
- Cross-validation estimates how a workflow performs across multiple train/validation partitions. The split design must reflect the data; grouped or time-ordered observations may require specialized splitting.

**Practice**
- Calculate cross-validation scores for a baseline classifier.
- Compare `KFold` and `StratifiedKFold` for classification.
- Report the mean and spread of scores rather than only one fold.

**Mini Task**
- Evaluate a complete pipeline with cross-validation and document the splitter and scoring metric.

**Official Documentation:** [Cross-validation](https://scikit-learn.org/stable/modules/cross_validation.html) · [`cross_validate`](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.cross_validate.html)

**Status:** ⬜ Not Started

### Day 20 — GridSearchCV

**Topics**
- Exhaustive search over a defined parameter grid
- Cross-validation within model selection
- Best estimator and search results

**Scikit-learn APIs**
- `GridSearchCV`

**What I should understand**
- Grid search evaluates specified parameter combinations using cross-validation. Search only a considered range, keep the final test set untouched, and account for computation cost.

**Practice**
- Tune a small set of parameters for a pipeline using `step__parameter` names.
- Inspect `best_params_`, `best_score_`, and `cv_results_`.
- Compare tuned and baseline models on the same held-out test set once.

**Mini Task**
- Add a compact, reproducible grid search to a previous project.

**Official Documentation:** [Tuning the hyper-parameters of an estimator](https://scikit-learn.org/stable/modules/grid_search.html) · [`GridSearchCV`](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.GridSearchCV.html)

**Status:** ⬜ Not Started

### Day 21 — RandomizedSearchCV

**Topics**
- Sampling parameter settings from distributions or lists
- Search budgets, reproducibility, and comparison with grid search

**Scikit-learn APIs**
- `RandomizedSearchCV`, `scipy.stats` distributions (optional)

**What I should understand**
- Randomized search samples a fixed number of candidates, which can explore broad spaces with a controlled budget. Its results depend on the search space and random seed; it is not inherently better than a well-designed grid.

**Practice**
- Define a mixed list/distribution search space.
- Run searches with different `n_iter` values and compare time and results.
- Track the search seed and cross-validation strategy.

**Mini Task**
- Replace a large grid with a smaller randomized search and explain the budget choice.

**Official Documentation:** [Randomized parameter optimization](https://scikit-learn.org/stable/modules/grid_search.html#randomized-parameter-optimization) · [`RandomizedSearchCV`](https://scikit-learn.org/stable/modules/generated/sklearn.model_selection.RandomizedSearchCV.html)

**Status:** ⬜ Not Started

### Day 22 — Overfitting, Underfitting, and Regularization

**Topics**
- Training versus validation performance
- Model complexity and generalization
- L1/L2 penalties and Elastic Net

**Scikit-learn APIs**
- `Ridge`, `Lasso`, `ElasticNet`

**What I should understand**
- Underfitting means the model misses useful patterns; overfitting means it captures training-specific patterns that do not generalize. Regularization penalizes coefficient size, and the appropriate strength is selected using validation—not the test set.

**Practice**
- Plot train and validation scores across model complexity or regularization strength.
- Compare `Ridge`, `Lasso`, and `ElasticNet` on a regression task.
- Scale features within the validation pipeline before comparing penalties.

**Mini Task**
- Write a short bias/variance diagnosis using observed train and validation scores.

**Official Documentation:** [Linear models](https://scikit-learn.org/stable/modules/linear_model.html) · [`Ridge`](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.Ridge.html) · [`Lasso`](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.Lasso.html) · [`ElasticNet`](https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.ElasticNet.html)

**Status:** ⬜ Not Started

### Day 23 — K-Means Clustering

**Topics**
- Unsupervised learning and centroid-based clustering
- Number of clusters, initialization, and convergence
- Scaling and cluster interpretation

**Scikit-learn APIs**
- `KMeans`

**What I should understand**
- K-Means assigns observations to a chosen number of centroids by minimizing within-cluster squared distances. It is sensitive to feature scales and initialization, and clusters are not automatically meaningful business segments.

**Practice**
- Fit K-Means at several values of `n_clusters`.
- Compare cluster assignments with and without scaling.
- Inspect cluster centers and cluster sizes.

**Mini Task**
- Create a concise cluster profile table and describe what additional domain validation is needed.

**Official Documentation:** [Clustering](https://scikit-learn.org/stable/modules/clustering.html) · [`KMeans`](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html)

**Status:** ⬜ Not Started

### Day 24 — Clustering Evaluation: Silhouette Score and Related Concepts

**Topics**
- Inertia and within-cluster compactness
- Silhouette coefficient
- Internal metrics versus external/domain validation

**Scikit-learn APIs**
- `silhouette_score`, `silhouette_samples`, `calinski_harabasz_score`, `davies_bouldin_score`

**What I should understand**
- Internal clustering metrics summarize geometric properties, not real-world usefulness. Silhouette values compare within-cluster cohesion and nearest-cluster separation; compare results carefully across appropriate data and distance assumptions.

**Practice**
- Calculate inertia across several K-Means cluster counts.
- Calculate silhouette scores for valid candidate clusterings.
- Compare a metric-based choice with an interpretable cluster profile.

**Mini Task**
- Recommend a cluster count with evidence and explicitly state the limits of the chosen metric.

**Official Documentation:** [Clustering performance evaluation](https://scikit-learn.org/stable/modules/clustering.html#clustering-performance-evaluation) · [`silhouette_score`](https://scikit-learn.org/stable/modules/generated/sklearn.metrics.silhouette_score.html)

**Status:** ⬜ Not Started

### Day 25 — PCA: Principal Component Analysis

**Topics**
- Dimensionality reduction and orthogonal directions
- Explained variance and component selection
- Scaling before PCA when feature units differ

**Scikit-learn APIs**
- `PCA`

**What I should understand**
- PCA creates linear combinations of input features that capture variance in descending order. It is useful for compression and visualization, but components may be less interpretable and high variance is not necessarily predictive signal.

**Practice**
- Fit PCA and inspect `explained_variance_ratio_`.
- Plot two components for a labeled dataset as an exploratory visualization.
- Compare PCA with and without scaling when features have different units.

**Mini Task**
- Document a component-count choice and the cumulative explained variance.

**Official Documentation:** [Decomposing signals in components (PCA)](https://scikit-learn.org/stable/modules/decomposition.html#pca) · [`PCA`](https://scikit-learn.org/stable/modules/generated/sklearn.decomposition.PCA.html)

**Status:** ⬜ Not Started

### Day 26 — Anomaly Detection: IsolationForest

**Topics**
- Outlier/anomaly detection and its assumptions
- Inlier/outlier predictions and anomaly scores
- Contamination as a modeling assumption

**Scikit-learn APIs**
- `IsolationForest`

**What I should understand**
- Isolation Forest isolates observations using randomized trees; observations that are isolated more easily receive different anomaly scores. Anomaly labels depend on a thresholding assumption, and unsupervised detections need investigation rather than automatic acceptance.

**Practice**
- Fit `IsolationForest` on a dataset and inspect `predict()` and `decision_function()`.
- Vary `contamination` and compare the number of flagged observations.
- If labels exist, evaluate detections without treating them as proof of deployment performance.

**Mini Task**
- Produce an anomaly review table with scores and a plan for human/domain verification.

**Official Documentation:** [Novelty and outlier detection](https://scikit-learn.org/stable/modules/outlier_detection.html) · [`IsolationForest`](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.IsolationForest.html)

**Status:** ⬜ Not Started

### Day 27 — Feature Engineering and Feature Selection

**Topics**
- Domain-driven transformations and derived features
- Univariate selection, model-based selection, and permutation importance
- Validation-safe feature creation and selection

**Scikit-learn APIs**
- `PolynomialFeatures`, `SelectKBest`, `f_classif`, `SelectFromModel`, `permutation_importance`

**What I should understand**
- Feature engineering changes the representation provided to a model; feature selection reduces it. Any operation that learns from data belongs inside the training workflow to avoid leakage.

**Practice**
- Create a derived feature with a documented rationale.
- Compare a baseline with `SelectKBest` inside cross-validation.
- Use permutation importance on held-out data and discuss correlated-feature caveats.

**Mini Task**
- Add one well-motivated feature transformation or selector to a pipeline and evaluate its impact.

**Official Documentation:** [Feature selection](https://scikit-learn.org/stable/modules/feature_selection.html) · [Permutation feature importance](https://scikit-learn.org/stable/modules/permutation_importance.html) · [`PolynomialFeatures`](https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.PolynomialFeatures.html)

**Status:** ⬜ Not Started

### Day 28 — Model Persistence with joblib and Production Considerations

**Topics**
- Saving/loading fitted Python objects
- Version compatibility, trusted artifacts, and reproducibility
- Persisting preprocessing together with the estimator

**Scikit-learn APIs**
- `joblib.dump`, `joblib.load`; persist the fitted `Pipeline`

**What I should understand**
- Persist the full fitted preprocessing-and-model pipeline so inference applies the same transformations. Pickle-based formats can execute code when loaded; load only trusted artifacts, and keep compatible dependency versions and metadata.

**Practice**
- Save a fitted pipeline and load it in a fresh process.
- Compare predictions before and after loading.
- Record the training data reference, feature schema, package versions, and model evaluation details.

**Mini Task**
- Create a reproducible inference script that loads a trusted artifact and validates expected input columns.

**Official Documentation:** [Model persistence](https://scikit-learn.org/stable/model_persistence.html)

**Status:** ⬜ Not Started

### Day 29 — Complete End-to-End ML Project

**Topics**
- Problem definition, data checks, baselines, and experiment tracking
- Leakage-safe preprocessing, validation, and evaluation
- Reproducibility and readable project organization

**Scikit-learn APIs**
- `train_test_split`, `Pipeline`, `ColumnTransformer`, `cross_validate`, `GridSearchCV` or `RandomizedSearchCV`

**What I should understand**
- An end-to-end project is a repeatable sequence from raw data to evaluated artifact. Separate model selection from final test evaluation and make assumptions, limitations, and data provenance explicit.

**Practice**
- Define a target, prediction unit, metric, and baseline.
- Build preprocessing and estimator steps in a pipeline.
- Compare at least two model families with a fixed validation approach.
- Evaluate the selected workflow once on held-out test data.

**Mini Task**
- Complete a project README with setup, data source, methodology, evaluation, limitations, and reproduction instructions.

**Official Documentation:** [Getting Started](https://scikit-learn.org/stable/getting_started.html) · [Pipelines and composite estimators](https://scikit-learn.org/stable/modules/compose.html) · [Model evaluation](https://scikit-learn.org/stable/modules/model_evaluation.html)

**Status:** ⬜ Not Started

### Day 30 — Final Project, Revision, and Portfolio Preparation

**Topics**
- Review the workflow and explain design choices
- Inference interface, input validation, and API operations
- Portfolio-quality documentation and limitations

**Scikit-learn APIs**
- The final fitted pipeline's `predict()` or `predict_proba()`
- `joblib.dump`, `joblib.load`

**What I should understand**
- A model API is only one part of a production system. Validate incoming data, version the artifact and dependencies, handle errors clearly, monitor changing data and outcomes, and avoid presenting a demo as a production guarantee.

**Practice**
- Re-run the project from a clean environment using documented steps.
- Add tests for preprocessing and representative inference inputs.
- Explain the metric, validation design, threshold, and key limitations.
- Review every repository day and update only the statuses actually completed.

**Mini Task**
- Publish a concise portfolio summary linking the project, code, evaluation method, and next improvement—without claiming unsupported results.

**Official Documentation:** [Model persistence](https://scikit-learn.org/stable/model_persistence.html) · [Scikit-learn API reference](https://scikit-learn.org/stable/modules/classes.html)

**Status:** ⬜ Not Started

## Daily Learning Format

Copy this template into each day's notes or notebook:

```markdown
# Day XX — Topic

- [ ] 📚 Theory
- [ ] 🔧 Scikit-learn API
- [ ] 💻 Coding Practice
- [ ] 🧠 Mathematical Understanding
- [ ] 🧪 Mini Project/Task
- [ ] 📝 Notes
- [ ] 🔗 Official Documentation
- [ ] ✅ Completion Checklist

## Key takeaways

## Experiments and observations

## Questions / next steps
```

### Suggested Daily Study Pattern

| Time | Activity |
|---:|---|
| 30 min | Read the linked concepts and API documentation |
| 60 min | Code the examples and inspect the results |
| 45 min | Complete the practice exercises or mini task |
| 15 min | Record takeaways, issues, and follow-up questions |

Adjust the time to fit the topic. The objective is a reproducible exercise and a clear explanation of what was learned—not a fixed number of study hours.

## Projects

### Project 1 — Breast Cancer Classification

**Concepts**
- Train/test split
- Logistic Regression
- KNN
- Decision Tree
- Random Forest
- Classification metrics

**Deliverable:** Compare a small set of baselines using a fixed split and appropriate classification metrics. Report the evaluation approach and limitations; do not infer clinical suitability from a learning exercise.

### Project 2 — House Price Prediction

**Concepts**
- Regression
- Feature preprocessing
- Linear Regression
- Ridge
- Lasso
- Random Forest
- Regression metrics

**Deliverable:** Build a reproducible regression workflow, compare a baseline and candidate models, and explain error in the target's units.

### Project 3 — Customer Churn Prediction

**Concepts**
- Missing values
- Numerical preprocessing
- Categorical encoding
- `ColumnTransformer`
- `Pipeline`
- Cross-validation
- Hyperparameter tuning
- Classification metrics

**Deliverable:** Keep preprocessing inside the cross-validated pipeline, select metrics based on the business cost of errors, and document class balance.

### Project 4 — Customer Segmentation

**Concepts**
- K-Means
- Scaling
- Elbow method
- Silhouette score
- PCA visualization

**Deliverable:** Compare candidate clusterings and profile resulting groups. Treat clustering metrics and PCA plots as exploratory evidence, not proof that segments are useful.

### Final Project — Production ML API

Build an end-to-end ML application:

```text
Dataset
  → Data preprocessing
  → Feature engineering
  → Train/test split
  → Pipeline
  → Model training
  → Cross-validation
  → Hyperparameter tuning
  → Evaluation
  → Save model
  → FastAPI
  → Prediction endpoint
```

**Architecture**

```text
Client
  → FastAPI request validation
  → Load the versioned, fitted preprocessing + model pipeline
  → Predict
  → Return a validated response
```

Keep the training code reproducible and the inference code explicit about the expected input schema. FastAPI is outside Scikit-learn's scope; this learning roadmap uses it as an application layer around the persisted Scikit-learn pipeline. Document how to run the API, the expected request fields, model/dependency versions, evaluation method, and known limitations.

## Important Scikit-learn Concepts

Examples below use a small, shared synthetic dataset unless stated otherwise:

```python
from sklearn.datasets import load_iris

X, y = load_iris(return_X_y=True)
```

| Concept | Simple definition and why it matters | Small Python example |
|---|---|---|
| Estimator | An object that learns from data. A common interface makes components easier to swap and evaluate. | `from sklearn.linear_model import LogisticRegression`<br>`model = LogisticRegression(max_iter=1000)` |
| Transformer | An estimator that learns a transformation and applies it to features. | `from sklearn.preprocessing import StandardScaler`<br>`scaler = StandardScaler().fit(X)`<br>`X_scaled = scaler.transform(X)` |
| Predictor | An estimator that produces target predictions, often through `predict()`. | `from sklearn.tree import DecisionTreeClassifier`<br>`clf = DecisionTreeClassifier().fit(X, y)`<br>`labels = clf.predict(X[:3])` |
| `fit()` | Learns model or transformer state from the supplied training data. | `model = LogisticRegression(max_iter=1000).fit(X, y)` |
| `predict()` | Uses a fitted estimator to produce predictions for new rows. | `predictions = model.predict(X[:3])` |
| `transform()` | Applies a transformer's learned mapping to data. | `scaler = StandardScaler().fit(X)`<br>`X_new = scaler.transform(X[:3])` |
| `fit_transform()` | Fits a transformer and transforms the supplied data. On training data this can be convenient; validation/test data should use `transform()` with the already-fitted transformer. | `scaler = StandardScaler()`<br>`X_train_scaled = scaler.fit_transform(X)` |
| Pipeline | Chains transformations and an estimator so fitting and prediction follow one consistent workflow. | `from sklearn.pipeline import make_pipeline`<br>`pipe = make_pipeline(StandardScaler(), LogisticRegression(max_iter=1000))`<br>`pipe.fit(X, y)` |
| ColumnTransformer | Applies different transformations to selected columns in a heterogeneous dataset. | `from sklearn.compose import ColumnTransformer`<br>`prep = ColumnTransformer([("scale", StandardScaler(), [0, 1])], remainder="passthrough")` |
| Cross-validation | Repeats training/validation across folds to estimate performance more robustly than relying on one split. | `from sklearn.model_selection import cross_val_score`<br>`scores = cross_val_score(model, X, y, cv=5)` |
| Hyperparameter | A configuration chosen before/during model fitting, rather than a learned coefficient. Tune it with a validation strategy. | `model = LogisticRegression(C=0.5, max_iter=1000)` |
| Data leakage | Information unavailable at prediction time influences training or model selection, giving overly optimistic evaluation. Keep learned preprocessing in the pipeline and protect the final test set. | `from sklearn.pipeline import make_pipeline`<br>`safe_model = make_pipeline(StandardScaler(), LogisticRegression(max_iter=1000))` |
| Model persistence | Saving a fitted workflow so it can be reloaded for inference. Persist preprocessing with the estimator and only load trusted artifacts. | `import joblib`<br>`joblib.dump(pipe, "model.joblib")`<br>`loaded = joblib.load("model.joblib")` |

## Algorithm Cheat Sheet

Scaling guidance is workflow-dependent. In particular, distance-, margin-, and variance-based methods can be sensitive to feature scales; tree-based methods generally split on feature values and typically do not require standardization. Preprocessing must still be validated as part of the complete workflow.

| Algorithm | Type | Use case | Scaling required? | Important parameters |
|---|---|---|---|---|
| Linear Regression | Supervised regression | Continuous target baseline and linear relationships | Not inherently required for ordinary least squares; scaling can help with regularized variants or numerical conditioning | `fit_intercept`, `positive` |
| Logistic Regression | Supervised classification | Linear decision boundary and probability estimates | Often useful when feature scales vary, especially with regularization | `C`, `penalty`, `solver`, `max_iter` |
| KNN | Supervised classification/regression | Local, distance-based patterns | Usually important when feature units/ranges differ | `n_neighbors`, `weights`, `metric` |
| Decision Tree | Supervised classification/regression | Nonlinear splits and rule-like models | Usually not required for the tree's split criterion | `max_depth`, `min_samples_leaf`, `criterion` |
| Random Forest | Supervised classification/regression | Tree ensemble baseline for nonlinear tabular data | Usually not required for tree splits | `n_estimators`, `max_features`, `min_samples_leaf` |
| Gradient Boosting | Supervised classification/regression | Sequential tree ensembles | Usually not required for tree splits | `learning_rate`, `n_estimators`, `max_depth` |
| Naive Bayes | Supervised classification | Fast probabilistic baseline; variant depends on feature representation | Depends on variant and data representation; not a universal requirement | `var_smoothing` (Gaussian), `alpha` (Multinomial/Bernoulli) |
| SVM | Supervised classification/regression | Margin-based linear or kernel decision boundaries | Generally important when features have different scales | `C`, `kernel`, `gamma` |
| K-Means | Unsupervised clustering | Centroid-based grouping of numeric observations | Usually important when numeric feature scales differ | `n_clusters`, `init`, `n_init` |
| PCA | Unsupervised dimensionality reduction | Compress or visualize correlated numeric features | Often important when feature units/scales differ | `n_components`, `svd_solver`, `whiten` |
| IsolationForest | Unsupervised anomaly detection | Flag observations that are easier to isolate | No universal requirement; assess feature representation and workflow | `n_estimators`, `contamination`, `max_samples` |

## Model Evaluation Cheat Sheet

### Classification

| Metric | What it measures | When to use it | Higher/lower meaning | Important limitations |
|---|---|---|---|---|
| Accuracy | Fraction of predictions that are correct | Balanced classes and similar error costs | Higher means more correct predictions overall | Can hide poor minority-class performance when classes are imbalanced |
| Precision | Fraction of predicted positives that are truly positive | False positives are costly | Higher means fewer false positives among predicted positives | Does not measure how many actual positives were missed |
| Recall | Fraction of actual positives found | False negatives are costly | Higher means fewer actual positives are missed | Can increase at the cost of more false positives |
| F1 | Harmonic mean of precision and recall | Need a single summary of precision/recall balance | Higher means a better balance of the two | Ignores true negatives and depends on positive-class/averaging choices |
| ROC-AUC | Ranking ability across classification thresholds | Comparing binary ranking performance across thresholds | Higher generally means better positive-vs-negative ranking | Does not select a threshold; can be less informative under strong imbalance |
| Confusion Matrix | Counts of actual versus predicted classes | Understanding error types and class-wise outcomes | No single “higher is better”; inspect diagonal and error cells | Raw counts depend on sample size and chosen threshold |

### Regression

| Metric | What it measures | When to use it | Higher/lower meaning | Important limitations |
|---|---|---|---|---|
| MAE | Mean absolute prediction error | Want an average error in target units, less outlier-sensitive than squared error | Lower is better; zero is perfect | Treats each absolute deviation linearly; gives limited information about error distribution |
| MSE | Mean squared prediction error | Large errors should receive stronger penalty | Lower is better; zero is perfect | Squared target units make interpretation less direct; sensitive to outliers |
| RMSE | Square root of MSE, in target units | Want squared-error penalty but interpretable units | Lower is better; zero is perfect | Still sensitive to large errors and can obscure the distribution of residuals |
| R² | Improvement relative to predicting the mean target, on evaluated data | Comparing fit with a mean-prediction baseline | Higher is generally better; 1 is perfect; 0 matches the mean baseline; negative is worse than that baseline | Can be negative; does not show error scale or whether the model is useful for a particular decision |

## Common Mistakes

1. **Data leakage:** Letting future, target, or held-out information influence training or model selection makes evaluation unreliable.
2. **Scaling before train/test split:** The scaler learns statistics from all rows. Split first; fit transformations on training data.
3. **Fitting preprocessing on test data:** Do not call `fit` or `fit_transform` on the test set. Fit on training data, then call `transform`.
4. **Using accuracy blindly on imbalanced data:** Check class distribution and error costs; consider precision, recall, F1, ROC-AUC, or other task-appropriate measures.
5. **Overfitting:** A strong training score alone does not demonstrate generalization. Compare training and validation behavior.
6. **Underfitting:** A model that is too constrained or too simple may miss useful patterns; inspect errors and validation evidence before increasing complexity.
7. **Tuning on the test set:** Repeated test-driven choices turn it into a validation set. Use cross-validation or a validation split for selection and reserve the test set for final evaluation.
8. **Forgetting cross-validation:** One split can be noisy. Use an appropriate CV strategy, especially for smaller datasets, while respecting groups or time order.
9. **Saving only the model:** Inference also needs the same learned preprocessing. Save the complete fitted pipeline and its compatibility metadata.
10. **Not using `Pipeline`:** Separate preprocessing code is easier to apply inconsistently and can leak information during validation. Compose the workflow where practical.

## Recommended Project Structure

```text
scikit-learn-30-days/
├── README.md
├── requirements.txt
├── day-01/
├── day-02/
├── day-03/
│   ...
├── day-30/
├── projects/
│   ├── breast-cancer-classification/
│   ├── house-price-prediction/
│   ├── customer-churn/
│   ├── customer-segmentation/
│   └── production-ml-api/
└── assets/
```

- `README.md`: roadmap, progress, project summaries, and links to detailed work.
- `requirements.txt`: direct Python dependencies with versions or compatible constraints appropriate to the project.
- `day-01/` through `day-30/`: that day's focused notebook or script, notes, and small outputs needed to reproduce the exercise.
- `projects/`: self-contained project code, documentation, and tests. Keep each project's data instructions and execution steps clear.
- `assets/`: small diagrams or images referenced by the README. Avoid committing large datasets, credentials, or generated artifacts that do not belong in version control.

## Progress Tracker

Update **Status** and **Notes** as work is completed. Allowed statuses: `⬜ Not Started`, `🟨 In Progress`, `✅ Completed`.

| Day | Topic | Status | Notes |
|---:|---|---|---|
| 1 | Scikit-learn introduction and estimator API | ⬜ Not Started | |
| 2 | Datasets and train/test splitting | ⬜ Not Started | |
| 3 | Linear Regression | ⬜ Not Started | |
| 4 | Regression metrics — MAE, MSE, RMSE, R² | ⬜ Not Started | |
| 5 | Logistic Regression | ⬜ Not Started | |
| 6 | K-Nearest Neighbors | ⬜ Not Started | |
| 7 | Decision Trees | ⬜ Not Started | |
| 8 | Random Forest | ⬜ Not Started | |
| 9 | Gradient Boosting | ⬜ Not Started | |
| 10 | Naive Bayes | ⬜ Not Started | |
| 11 | Support Vector Machines | ⬜ Not Started | |
| 12 | Feature Scaling — StandardScaler and MinMaxScaler | ⬜ Not Started | |
| 13 | Categorical Encoding — OneHotEncoder and OrdinalEncoder | ⬜ Not Started | |
| 14 | Missing Value Handling — SimpleImputer | ⬜ Not Started | |
| 15 | Pipeline | ⬜ Not Started | |
| 16 | ColumnTransformer | ⬜ Not Started | |
| 17 | Classification Metrics — Accuracy, Precision, Recall and F1 | ⬜ Not Started | |
| 18 | Confusion Matrix and ROC-AUC | ⬜ Not Started | |
| 19 | Cross Validation | ⬜ Not Started | |
| 20 | GridSearchCV | ⬜ Not Started | |
| 21 | RandomizedSearchCV | ⬜ Not Started | |
| 22 | Overfitting, Underfitting and Regularization — Ridge, Lasso, ElasticNet | ⬜ Not Started | |
| 23 | K-Means Clustering | ⬜ Not Started | |
| 24 | Clustering Evaluation — Silhouette Score and related concepts | ⬜ Not Started | |
| 25 | PCA — Principal Component Analysis | ⬜ Not Started | |
| 26 | Anomaly Detection — IsolationForest | ⬜ Not Started | |
| 27 | Feature Engineering and Feature Selection | ⬜ Not Started | |
| 28 | Model Persistence using joblib and production considerations | ⬜ Not Started | |
| 29 | Complete End-to-End ML Project | ⬜ Not Started | |
| 30 | Final Project, Revision and Portfolio Preparation | ⬜ Not Started | |

## After 30 Days I Should Be Able To

- Build ML models using Scikit-learn
- Select appropriate algorithms for a problem
- Preprocess real-world datasets
- Build reproducible pipelines
- Prevent data leakage
- Evaluate models correctly
- Perform cross-validation
- Tune hyperparameters
- Compare multiple models
- Perform unsupervised learning
- Save trained models
- Build an inference pipeline
- Expose a model through FastAPI
- Explain the complete ML workflow in an interview

## Next Roadmap

```text
Scikit-learn
    ↓
XGBoost / LightGBM
    ↓
PyTorch
    ↓
Deep Learning
    ↓
Transformers
    ↓
LLMs
    ↓
RAG
    ↓
Agentic AI
```

Scikit-learn provides a strong foundation in data preparation, evaluation, validation, and reproducible model workflows. These fundamentals remain valuable when moving to boosted-tree libraries and deep-learning frameworks: they help distinguish a sound experiment from a misleading score and make later AI systems easier to build, evaluate, and maintain.
