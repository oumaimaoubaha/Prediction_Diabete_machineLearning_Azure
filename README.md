# 🩺 DiagDiabète – Prédiction du diabète sous Azure Cloud

## 📌 Description du projet

**DiagDiabète** est une application de data mining permettant de prédire le risque de diabète à partir de données médicales simples. Le projet couvre l’ensemble du cycle de vie d’un modèle de Machine Learning : préparation des données, modélisation, évaluation et déploiement sous forme d’application web.

L’ensemble du pipeline de traitement et d’entraînement a été réalisé dans un **environnement Cloud Azure**, à l’aide de **Azure Machine Learning Studio**, puis le modèle final a été intégré dans une application **Streamlit**.

---

## 🎯 Objectifs

* Prédire si un patient est **diabétique (1)** ou **non diabétique (0)**
* Comparer plusieurs modèles de Machine Learning
* Optimiser le modèle retenu
* Déployer une application web simple et utilisable par des non‑experts

---

## 🗂 Dataset

* Source : HuggingFace – *diabetes_prediction_dataset*
* Taille : ~100 000 enregistrements
* Variables principales :

  * Âge
  * IMC (BMI)
  * HbA1c
  * Glycémie
  * Sexe
  * Tabagisme
  * Hypertension
  * Maladie cardiaque
* Variable cible : `diabetes` (0 = non diabétique, 1 = diabétique)

---

## ⚙️ Méthodologie

### 1️⃣ Prétraitement des données

* Nettoyage des valeurs non informatives
* Encodage des variables catégorielles (One‑Hot Encoding)
* Détection des valeurs aberrantes avec **Isolation Forest** et méthode IQR
* Normalisation des variables numériques avec **RobustScaler**
* Rééquilibrage des classes (oversampling inspiré de SMOTE)

### 2️⃣ Modélisation

Quatre modèles supervisés ont été comparés :

* XGBoost
* Random Forest
* LightGBM
* Régression Logistique

Optimisation des hyperparamètres avec **RandomizedSearchCV** et ajustement du seuil de classification.

### 3️⃣ Évaluation

* Accuracy
* Precision
* Recall
* F1‑score
* AUC
* Matrices de confusion

➡️ **XGBoost** a été retenu comme modèle final pour son meilleur équilibre entre précision et rappel.

---

## 🚀 Déploiement

### Application Streamlit – *DiagDiabète*

Deux modes d’utilisation sont proposés :

#### 🔹 Mode formulaire individuel

* Saisie manuelle des données patient
* Affichage :

  * Probabilité de diabète
  * Verdict clair (Faible risque / Diabète probable)

#### 🔹 Mode fichier CSV

* Upload d’un fichier contenant plusieurs patients
* Sans labels : génération d’un fichier enrichi avec prédictions
* Avec labels : calcul automatique des métriques et affichage de la matrice de confusion

---

## 🧱 Architecture technique

* **Azure Machine Learning Studio** (pipeline cloud)
* **XGBoost** (modèle final)
* **Python**
* **Pandas / NumPy**
* **Scikit‑learn**
* **Joblib** (sauvegarde du modèle)
* **Streamlit** (interface web)

---

## 📈 Résultats clés

* F1‑score : **0.92**
* AUC : **0.997**
* Très faible taux de faux négatifs
* Modèle fiable et robuste pour un contexte médical

---

## 🧠 Limites et perspectives

* Dataset générique (non spécifique à une population locale)
* Pas de données cliniques avancées

### Améliorations possibles :

* Intégration de données médicales réelles
* Ajout d’explicabilité (SHAP, LIME)
* Déploiement via API ou conteneurisation

---

## 👩‍💻 Auteurs

* **Kawtar Benali**
* **Oubaha Oumaima**

Encadré par : *Pr. Hayat Routaib*

---

## 🏁 Conclusion

Ce projet démontre comment une solution de **data mining appliquée à la santé** peut être conçue, entraînée et déployée entièrement dans un **environnement Cloud Azure**, puis rendue accessible via une application web simple et interactive.
