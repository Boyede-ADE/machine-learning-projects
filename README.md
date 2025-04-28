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

  ## 📁 Documents et fichiers du projet

Ce projet contient les fichiers suivants :

- **Fichier de soumission avec les prévisions définitives** : [soumission.csv](soumission.csv)
  Ce fichier contient les données de base et les prévisions finales du modèle pour les clients à risque de défaut de paiement.

- **Script Python pour la Prédiction** : [Script prédiction.ipynb](scripts/Script%20prédiction.ipynb)  
  Ce fichier contient le code pour prédire les défauts de paiement à partir des caractéristiques des clients.

- **Script Python pour le Clustering** : [Script_clustering.ipynb](scripts/Script_clustering.ipynb)  
  Ce fichier contient le code pour l'application du clustering et la segmentation des clients.
  
- **Clustering et les préconisations** : [Article_segmentation.pdf](documentation/Article_segmentation.pdf)   
  Un document détaillant la segmentation des clients en trois groupes (personas) et les stratégies commerciales proposées pour chaque segment.

- **Base de données d'entraînement** : [training.csv](Base%20de%20données/base1/training.csv)  
  La première base de données utilisée est le fichier d’entraînement comportant **24 000 lignes**, qui correspondent à l’historique de 24 000 personnes débouchant ou non sur un défaut de paiement.

- **Base de données d'évaluation** : [evaluation.csv](Base%20de%20données/base2/evaluation.csv)
  La deuxième base de données, complémentaire à la première, est le fichier d’évaluation **vierge** comportant **6 000 lignes**, correspondant à l’historique de 6 000 autres personnes dont il faut "deviner" s'ils ont subi un défaut de paiement ou non.
  L’objectif est de remplir la colonne **DEF** (défaut de paiement : 1 ou non : 0) pour les 6 000 identifiants.

## 📝 Description des variables

La description des variables dans les bases de données est la suivante :

- **ID** : Identification de la ligne (ce n’est donc pas une variable, elle se trouve en première colonne du fichier).
- **La variable à prédire (Y = "DEF")** : C’est une variable binaire qui indique un défaut de paiement (1 pour Oui, 0 pour Non). Elle se trouve en dernière colonne du fichier.
  
Les variables explicatives (X = …) sont les suivantes :
- **X1 = "LIMIT_BAL"** : Montant du crédit donné (en euros). Il comprend à la fois le crédit à la consommation individuel et le crédit supplémentaire à la famille.
- **X2 = "SEX"** : Sexe (1 = homme, 2 = femme).
- **X3 = "EDUCATION"** : Niveau d’éducation (1 = école supérieure, 2 = université, 3 = lycée, 4,5 … = autres).
- **X4 = "MARRIAGE"** : État civil (1 = marié, 2 = célibataire, 3 = autres).
- **X5 = "AGE"** : Âge (en années).
- **X6 – X11 = "PAY_1 … PAY_6"** : Historique des paiements passés. Nous avons suivi les enregistrements de paiement mensuels passés (d’avril à septembre 2005) comme suit :
  - **X6** = L’état du remboursement en septembre 2005 ;
  - **X7** = État de remboursement en août 2005 ;
  - … ;
  - **X11** = État de remboursement en avril 2005. L’échelle de mesure de l’état de remboursement est :
    - -2 : Non utilisation du crédit ;
    - -1 = Payé dûment ;
    - 0 = Paiement fin de mois en cours ;
    - 1 = Délai de paiement d’un mois ;
    - 2 = Délai de paiement de deux mois ;
    - … ;
    - 8 = Délai de paiement de huit mois ;
    - 9 = Retard de paiement de neuf mois et plus.

- **X12 - X17 = "BILL_AMT1 … BILL_AMT_6"** : Montant du relevé de facture (en euros).
  - **X12** = Montant du relevé de facture en septembre 2005 ;
  - **X13** = Montant du relevé de facture en août 2005 ;
  - … ;
  - **X17** = Montant du relevé de facture en avril 2005.

- **X18 - X23 = "PAY_AMT1 … PAY_AMT_6"** : Montant du paiement précédent (en euros).
  - **X18** = Montant payé en septembre 2005 ;
  - **X19** = Montant payé en août 2005 ;
  - … ;
  - **X23** = Montant versé en avril 2005.

  
  
