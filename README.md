# Machine Learning Projects

Ce dépôt contient des projets réalisés en Machine Learning avec Python, principalement sur **Google Colab**.  
Voici le projet principal que vous pouvez trouver ici :

## Projet
- **Identification des défauts de paiement de cartes de crédit**  
   À partir des données d'une banque internationale implantée à Paris, mon objectif dans ce projet était de :
   - **Expliquer les causes des défauts de paiement** de cartes de crédit.
   - **Prédire** les clients qui auront des défauts de paiement de cartes de crédit.
   - **Regrouper les clients** de la banque en **3 segments pertinents** (clustering), en créant des personas pour chaque segment.
   - **Proposer une offre commerciale** pour chaque segment afin de **réduire le risque de défaut bancaire**.

### Méthodologie :
Mon approche méthodologique débute par le nettoyage rigoureux et la normalisation des données financières pour neutraliser les écarts d'échelle entre les variables. J'ai effectué un prétraitement sur les données pour les rendre appropriées pour le clustering. J'ai procédé à la suppression de colonnes non pertinentes, le traitement des valeurs manquantes ou aberrantes, et la normalisation des caractéristiques.

J'ai employé le **K-means** pour classifier les clients en trois clusters, en me basant sur des caractéristiques telles que l'historique de paiement et les montants de transactions. Parallèlement, un modèle prédictif de **Random Forest** a été calibré pour identifier les indicateurs précoces de défauts de paiement, offrant ainsi une possibilité de réaction avant que le risque ne devienne réalité.

### Phases du projet :
1. **Phase 1: Exploration et Compréhension des Données**  
   Outil utilisé : **Google Colab**  
   J'ai utilisé Google Colab pour charger, explorer et visualiser les données grâce aux bibliothèques intégrées comme **Pandas** pour la manipulation des données et **Matplotlib/Seaborn** pour la génération de graphiques exploratoires.

2. **Phase 2: Prétraitement des Données**  
   Outil utilisé : **Google Colab**  
   Nettoyage des données, gestion des valeurs manquantes et standardisation des caractéristiques en utilisant **StandardScaler** de **Scikit-learn**.

3. **Phase 3: Modélisation Prédictive**  
   Outil utilisé : **Google Colab**  
   J'ai construit et entraîné un modèle de classification, spécifiquement le **RandomForestClassifier** de **Scikit-learn**.  
   Optimisation des hyperparamètres avec **RandomizedSearchCV** pour trouver les meilleurs paramètres pour le modèle.

4. **Phase 4: Clustering et Segmentation des Clients**  
   Outil utilisé : **Google Colab**  
   Prétraitement des données pour les rendre appropriées pour le clustering. Application de la méthode **K-Means** pour segmenter les clients en groupes basés sur leurs profils de consommation et autres caractéristiques.

5. **Phase 5: Développement d'Offres Commerciales Ciblées**  
   Outil utilisé : **Google Colab**  
   Utilisation des insights tirés de l'analyse de clustering pour concevoir des stratégies de communication et des offres commerciales ciblées.

### Techniques utilisées :
- **Modélisation prédictive** : Random Forest pour la classification des clients à risque de défaut de paiement.
- **Clustering** : K-Means pour la segmentation des clients en groupes distincts, permettant une analyse approfondie des profils de consommation.
- **Analyse exploratoire des données (EDA)** : Visualisation et préparation des données avant l'entraînement des modèles.

### Résultats :
- **Prédiction des défauts de paiement** :  
   Le modèle **Random Forest** a permis de prédire les clients à risque de défaut de paiement avec une **précision de 82%**. Cela montre que le modèle est efficace pour identifier les clients potentiels à risque.

- **Segmentation des clients (Clustering)** :  
   Le **clustering K-Means** a permis de segmenter les clients en **3 groupes distincts** avec les personas suivants :  
     - **0: "Hauts Revenus"** : Clients ayant un revenu élevé et des comportements de dépenses importants.  
     - **1: "Utilisateurs Prudents"** : Clients ayant un comportement plus prudent avec leurs finances et un faible risque de défaut.  
     - **2: "Jeunes Professionnels"** : Clients jeunes, avec un revenu moyen et un potentiel de défaut modéré.

   Cette segmentation a permis de proposer des offres commerciales ciblées pour chaque groupe, adaptées à leurs profils financiers spécifiques.
