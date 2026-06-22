# 🩺 Prédiction du Diabète — Machine Learning

Un projet de classification binaire qui prédit si un patient est diabétique ou non, à partir du dataset [Pima Indians Diabetes](https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database).

---

## 📋 Description

Ce notebook couvre l'ensemble du pipeline ML :
- Analyse exploratoire des données (EDA)
- Nettoyage et feature engineering
- Comparaison de 5 algorithmes de classification
- Optimisation des hyperparamètres (GridSearchCV)
- Évaluation finale + prédiction interactive

Le meilleur modèle retenu est le **Gradient Boosting**, sélectionné sur la base du F1-score et de l'AUC (métriques adaptées au déséquilibre de classes).

---

## 🗂️ Structure du projet

```
.
├── first_try.ipynb     # Notebook principal
├── diabetes.csv        # Dataset (Pima Indians Diabetes)
└── README.md           # Ce fichier
```

---

## ⚙️ Installation

1. **Cloner le dépôt**
   ```bash
   git clone https://github.com/<votre-username>/<nom-du-repo>.git
   cd <nom-du-repo>
   ```

2. **Installer les dépendances**
   ```bash
   pip install numpy pandas matplotlib seaborn scikit-learn
   ```
   Ou avec la cellule d'installation en haut du notebook :
   ```bash
   !pip install numpy pandas matplotlib seaborn scikit-learn -q
   ```

3. **Lancer Jupyter**
   ```bash
   jupyter notebook first_try.ipynb
   ```

---

## 🔬 Pipeline ML

| Étape | Description |
|-------|-------------|
| **EDA** | Distribution des classes, matrice de corrélation, détection des zéros impossibles |
| **Prétraitement** | Remplacement des zéros par NaN, imputation par médiane conditionnée à la classe |
| **Feature Engineering** | Catégories d'IMC (`BMI_cat`), d'âge (`Age_cat`), de glycémie (`Glucose_cat`) |
| **Modélisation** | Régression Logistique, KNN, SVM, Random Forest, Gradient Boosting |
| **Optimisation** | GridSearchCV (5 folds) sur `n_estimators`, `learning_rate`, `max_depth` |
| **Évaluation** | Accuracy, Precision, Recall, F1-score, AUC, matrice de confusion, courbe ROC |
| **Prédiction** | Interface interactive en ligne de commande pour un nouveau patient |

---

## 📊 Résultats

Les modèles sont comparés sur le F1-score et l'AUC. Le **Gradient Boosting** obtient les meilleures performances après optimisation des hyperparamètres via GridSearchCV.

---

## 📦 Dépendances

- Python 3.8+
- numpy
- pandas
- matplotlib
- seaborn
- scikit-learn

---

## 📄 Dataset

- **Source :** [Pima Indians Diabetes Database — UCI / Kaggle](https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database)
- **Taille :** 768 patientes, 8 variables médicales + 1 variable cible (`Outcome`)
- **Cible :** `0` = non diabétique, `1` = diabétique