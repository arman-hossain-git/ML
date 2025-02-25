<h1><a href="https://github.com/arman-hossain-git/ML/blob/main/credit_card_fraud_detection.ipynb">Credit Card Fraud Detection</a></h1>
<p>This repository contains a machine learning project focused on detecting fraudulent credit card transactions. The notebook analyzes a dataset of credit card transactions and applies various classification models to identify fraudulent activity.</p>
<div class="section">
<h2>Data</h2>
 <h3>Context</h3>
  <p>It is important that credit card companies are able to recognize fraudulent credit card transactions so that customers are not charged for items that they did not purchase.</p>
  <h3>Content</h3>
  <p>The dataset contains transactions made by credit cards in September 2013 by European cardholders.
This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.<br>
It contains only numerical input variables which are the result of a PCA transformation. Unfortunately, due to confidentiality issues, we cannot provide the original features and more background information about the data. Features V1, V2, … V28 are the principal components obtained with PCA, the only features which have not been transformed with PCA are 'Time' and 'Amount'. Feature 'Time' contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature 'Amount' is the transaction Amount, this feature can be used for example-dependant cost-sensitive learning. Feature 'Class' is the response variable and it takes value 1 in case of fraud and 0 otherwise.
<br>
Given the class imbalance ratio, we recommend measuring the accuracy using the Area Under the Precision-Recall Curve (AUPRC). Confusion matrix accuracy is not meaningful for unbalanced classification.</p>
<p>In summary the dataset (<code><a href="https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud">creditcard.csv</a></code>) contains:</p>
<ul>
<li>Various anonymized transaction features (V1-V28)</li>
<li>Transaction amount</li>
<li>Time (seconds elapsed)</li>
<li>Class label (0 for normal transactions, 1 for fraudulent transactions)</li>
</ul>
</div>
<div class="section">
<h2>Project Structure</h2>
<h3>1. Exploratory Data Analysis</h3>
<ul>
<li>Basic data examination (shape, info, columns)</li>
<li>Class distribution analysis (highly imbalanced dataset with ~99.8% normal transactions)</li>
<li>Visual representation of class distribution through pie charts and count plots</li>
<li>Correlation analysis with heatmaps</li>
</ul>
<h3>2. Feature Engineering</h3>
<ul>
<li>Time feature conversion to more usable time components</li>
<li>Removal of redundant time features</li>
</ul>
<h3>3. Model Building</h3>
<ul>
<li><code>Logistic Regression (with L1 and L2 regularization)</code></li>
<li><code>K-Nearest Neighbors (KNN)</code></li>
<li><code>Decision Trees</code></li>
<li><code>Random Forest</code></li>
<li><code>XGBoost</code></li>
<li><code>Support Vector Machine (SVM)</code></li>
</ul>
<h3>4. Cross-Validation</h3>
<ul>
<li><code>RepeatedKFold</code></li>
<li><code>StratifiedKFold</code></li>
</ul>
<h3>5. Handling Class Imbalance</h3>
<ul>
<li><code>Random Oversampling (ROS)</code></li>
<li><code>Synthetic Minority Oversampling Technique (SMOTE)</code></li>
<li><code>Adaptive Synthetic Sampling (ADASYN)</code></li>
</ul>
<h3>6. Model Optimization</h3>
<ul>
<li>Hyperparameter tuning for XGBoost using RandomizedSearchCV</li>
<li>Final model building with optimal parameters</li>
</ul>
</div>
<div class="section">
<h2>Key Outputs</h2>
<h3>Class Distribution:</h3>
<ul>
<li>Normal transactions: ~99.8%</li>
<li>Fraudulent transactions: ~0.2%</li>
</ul>
<h3>Model Performance:</h3>
<ul>
<li>The XGBoost model with Random Oversampling and StratifiedKFold CV outperforms all other models</li>
<li>Evaluation metrics include Accuracy, ROC-AUC, and optimal threshold values</li>
</ul>
<h3>Feature Importance:</h3>
<ul>
<li>The notebook identifies the top 5 most important features for fraud detection</li>
<li>Visual representations of feature importance</li>
</ul>
</div>
<div class="section">
<h2>Conclusion</h2>
<p>XGBoost with Random Oversampling performs best across various sampling techniques.</p>
<p>Final model achieves high <code>ROC-AUC</code> score (exact value in output).</p>
</div>
<div class="section">
<h2>Usage</h2>
<p>The notebook is designed to be run in a Jupyter/Colab environment with access to the <code>creditcard.csv</code> dataset. It requires standard data science libraries including:</p>
<ul>
<li><code>pandas</code></li>
<li><code>numpy</code></li>
<li><code>scikit-learn</code></li>
<li><code>matplotlib</code></li>
<li><code>seaborn</code></li>
<li><code>imbalanced-learn</code></li>
<li><code>XGBoost</code></li>
</ul>
</div>
<div class="section">
<h2>Notes</h2>
<ul>
<li>The dataset exhibits extreme class imbalance, which is addressed through various sampling techniques.</li>
<li>All models are evaluated using <code>ROC-AUC</code> as the primary metric to account for the imbalanced nature of the problem.</li>
<li>The final <code>XGBoost model</code> parameters are optimized for this specific fraud detection task.</li>
</ul>
</div>
