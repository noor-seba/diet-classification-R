# 🥗 Classification des régimes alimentaires – LDA, kNN & CART

## 📌 Contexte

Ce projet étudie la capacité des composantes nutritionnelles de recettes alimentaires
à discriminer différents types de régimes. Le jeu de données provient de Kaggle et
regroupe 7804 recettes accompagnées d'informations nutritionnelles.

**Dataset :** All Diets (Kaggle)
- 7804 observations, sans valeurs manquantes
- Variables explicatives : protéines, glucides, lipides (g)
- Variable cible : `Diet_type` — 5 classes (dash, keto, mediterranean, paleo, vegan)

---

## 🎯 Objectifs

- Explorer et prétraiter les données nutritionnelles
- Comparer trois méthodes de classification supervisée : LDA, kNN et CART
- Évaluer les performances via accuracy, précision, recall et F1-score

---

## 🛠️ Technologies utilisées

![R](https://img.shields.io/badge/R-Statistics-blue?logo=r)
![ggplot2](https://img.shields.io/badge/ggplot2-Visualisation-green)
![rpart](https://img.shields.io/badge/rpart-CART-orange)
![MASS](https://img.shields.io/badge/MASS-LDA-purple)

- **Langage :** R
- **Librairies :** MASS, class, rpart, ggplot2, tidyr

---

## 🔬 Méthodologie

### Partie I – Exploration et prétraitement
- Boxplots et matrice de corrélation
- Transformation logarithmique des variables nutritionnelles
- Centrage-réduction
- ACP (65.88% variance expliquée sur CP1, 24.29% sur CP2)

### Partie II – Analyse Discriminante Linéaire (LDA)
- Application de la LDA sur les variables nutritionnelles transformées
- Validation croisée à 2 blocs répétée 100 fois
- Taux de bonne classification global : ~41.5%

### Partie III – kNN
- Sélection du k optimal par validation croisée (k=15)
- Évaluation sur split train/test 75/25

### Partie IV – CART
- Arbre initial → arbre complet → élagage (cp=0.02)
- Visualisation des règles de décision

### Comparaison finale
- Tableau et heatmap ggplot2 des métriques (accuracy, précision, recall, F1)

---

## 📊 Résultats

| Modèle | Évaluation |
|---|---|
| LDA | Validation croisée 2 blocs × 100 répétitions : **41,4 %** de bonne classification |
| kNN (k = 15) | k choisi par validation croisée (4 blocs), puis évaluation sur un échantillon test de 25 % |
| CART (élagué, cp = 0,02) | Arbre élagué, métriques calculées sur les données d'apprentissage |

Les métriques détaillées (accuracy, précision, recall, F1) des trois modèles sont comparées dans le tableau et la heatmap en fin de script.

**Détail LDA :** keto est le régime le mieux reconnu (≈ 68 %), suivi de vegan (≈ 56 %). Mediterranean (≈ 39 %) et dash (≈ 35 %) sont moins bien discriminés, paleo presque pas (≈ 5 %).

**Conclusion :** les trois méthodes ont des performances modérées. Les macronutriments (protéines, glucides, lipides) se chevauchent fortement d'un régime à l'autre et ne suffisent pas à séparer les 5 classes. Des variables supplémentaires (type de cuisine, ingrédients, micronutriments) seraient nécessaires pour améliorer la discrimination.

---

## ▶️ Reproduire l'analyse

1. Télécharger le jeu de données *All Diets* sur Kaggle et placer `All_Diets.csv` à la racine du dépôt
2. Placer dans le même dossier les fonctions de validation croisée utilisées par le script (`constCV.R`, `lda_CV.R`, `knn_CV.r`, avec ce nom exact)
3. Ouvrir `Projet_script.rmd` dans RStudio et le compiler (*Knit*)

Packages : `install.packages(c("MASS", "class", "rpart", "ggplot2", "tidyr"))`

---

## 👩‍💻 Auteure

**Noor Seba** – Étudiante en M2 Épidémiologie, Données de Santé & Biostatistique (parcours Data Analyst), Université de Montpellier
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Noor%20Seba-blue?logo=linkedin)](https://www.linkedin.com/in/noor-seba-260685369)
