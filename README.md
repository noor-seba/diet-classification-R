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

| Modèle | Accuracy | Points forts |
|---|---|---|
| LDA | ~41.5% | Keto bien classé (68%), vegan correct (56%) |
| kNN (k=15) | ~modérée | Stable, bon compromis biais-variance |
| CART (élagué) | ~modérée | Interprétable, règles de décision lisibles |

**Conclusion :** Les trois modèles présentent des performances modérées. Les variables
nutritionnelles seules ne suffisent pas à différencier les 5 régimes — l'ajout de
variables supplémentaires améliorerait les résultats.

---

## 👥 Contribution

Projet réalisé en groupe (Iman Oudkhiss, Noor Seba, Rania Lahyani).
Ma contribution porte sur les parties **kNN et CART**.

---

## 👩‍💻 Auteure

**Noor Seba** – Étudiante en Master Épidémiologie, Données de Santé & Biostatistique
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Noor%20Seba-blue?logo=linkedin)](https://www.linkedin.com/in/noor-seba-260685369)
