# 🩺 DiagDiabète – Machine Learning & Cloud (Azure)

## 🚀 Présentation du projet

**DiagDiabète** est un projet de **Machine Learning appliqué à la santé**, réalisé dans un **environnement Azure Cloud**, dont l’objectif est de prédire le risque de diabète à partir de données médicales simples.

Le projet couvre **tout le cycle Data / ML** : préparation des données, modélisation, optimisation, évaluation et déploiement sous forme d’une **application web interactive**.

👉 Projet orienté **Data Engineer / ML Engineer**, avec mise en place d’un pipeline reproductible et déployable.

---

## 🎯 Objectifs techniques

* Construire un pipeline de data mining sous **Azure Machine Learning**
* Comparer plusieurs algorithmes de classification
* Optimiser un modèle ML (hyperparamètres + seuil de décision)
* Déployer le modèle sous forme d’une application web
* Rendre le modèle exploitable par des utilisateurs non techniques

---

## 🗂 Dataset

* Source : HuggingFace – *diabetes_prediction_dataset*
* Taille : ~100 000 lignes
* Variable cible : `diabetes`

  * **0 = non diabétique**
  * **1 = diabétique**

Variables utilisées :

* Âge
* IMC (BMI)
* HbA1c
* Glycémie
* Sexe
* Historique de tabagisme
* Hypertension
* Maladie cardiaque

---

## ⚙️ Pipeline Data & ML (Azure Cloud)

### 🔹 Prétraitement des données

* Nettoyage et préparation des données
* Encodage One-Hot des variables catégorielles
* Détection des valeurs aberrantes avec **Isolation Forest** et méthode IQR
* Normalisation robuste des variables numériques avec **RobustScaler**
* Rééquilibrage des classes (oversampling inspiré de SMOTE)

### 🔹 Modélisation et optimisation

Modèles comparés :

* XGBoost
* Random Forest
* LightGBM
* Régression Logistique

Optimisation via **RandomizedSearchCV** et ajustement du seuil de classification pour maximiser le **F1-score**.

➡️ **XGBoost** retenu comme modèle final pour son meilleur compromis précision / rappel.

---

## 📊 Évaluation des performances

* Accuracy
* Precision
* Recall
* F1-score
* AUC
* Matrices de confusion

**Résultats clés :**

* F1-score : **0.92**
* AUC : **0.997**
* Très faible taux de faux négatifs (critique en contexte médical)

---

## 🌐 Déploiement – Application Streamlit

Le modèle final est intégré dans une application web développée avec **Streamlit**.

### Fonctionnalités :

* **Prédiction individuelle** via formulaire
* **Prédiction en masse** via fichiers CSV
* Calcul automatique des métriques si les labels sont présents
* Génération de matrices de confusion et visualisations

---

## 🧱 Architecture technique

* **Azure Machine Learning Studio** (pipeline cloud)
* **Python**
* **Pandas / NumPy**
* **Scikit-learn**
* **XGBoost**
* **Joblib** (sérialisation du modèle)
* **Streamlit** (interface web)

---

## 💼 Compétences mises en œuvre (profil Data Engineer / ML)

* Data preprocessing et feature engineering
* Détection d’anomalies
* Pipelines ML reproductibles
* Optimisation de modèles
* Déploiement de modèles en production
* Cloud Computing (Azure)

---

## 👩‍💻 Auteurs

* **Kawtar Benali**
* **Oubaha Oumaima**

Encadré par : *Pr. Hayat Routaib*

---

## 🏁 Conclusion

Ce projet démontre la capacité à concevoir et déployer une **solution ML complète sous Azure Cloud**, depuis les données brutes jusqu’à une application web fonctionnelle, avec une approche orientée **production, performance et reproductibilité**.
