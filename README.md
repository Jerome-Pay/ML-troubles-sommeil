# ML-troubles-sommeil
Projet de Master 2 - Classification des troubles du sommeil par apprentissage supervisée

## Introduction

D’après un rapport de l’INSERM, 1 personne sur 5 souffre de troubles du sommeil
chronique en France. Un sommeil de mauvaise qualit´e augmente les risques d’obésité,
de cancers et de maladies cardio-vasculaires. Il est important de bien détecter ces troubles avant de proposer des solutions aux personnes affectées par ceux-ci.  
Pour une personne soupçonné d’avoir un trouble du sommeil, les professionnels de santé
peuvent être amené à préparer un bilan du sommeil dans un centre spécialisé et cela
demande du temps et de l’espace. De plus, une personne qui soupçonne être atteinte
de l’apnée du sommeil peut potentiellement dépenser une grosse somme d’argent pour
acheter une machine.  

Il devient indispensable d’émettre des soupçons basé sur des indicateurs pertinents comme
l’IMC, la durée du sommeil ou encore l’âge. Ainsi, un modèle d’apprentissage supervisée
aide les professionnels de santé émettre un diagnostic et à prendre les mesures nécessaires
pour le patient.  

Le jeu de données utilisé dans cette étude, accessible sur [Kaggle](https://www.kaggle.com/datasets/uom190346a/sleep-health-and-lifestyle-dataset), se compose de deux parties distinctes. Ces deux parties ont été fusionnées pour constituer notre jeu de données
final qui contient 569 lignes et 13 colonnes, lequel inclut des indices sur la santé et le mode
de vie des participants ainsi que sur la qualité du sommeil. Le jeu de donn´ees a été crée
à des fins ´éducatives et ne provient pas de sources réelles.

### Metadata

• Identifiant (PersonID) quantitative discrète:  
Un identifiant pour chaque individu.  

• Genre (Gender) qualitative catégorielle :  
Le genre de la personne  

• Age (Age) quantitative discrète:  
L’âge de la personne.  

• Profession (Occupation) qualitative catégorielle:  
La profession de la personne.  

• Durée du sommeil (SleepDuration) quantitative continue:  
La durée de sommeil de la personne en heure.  

• Qualité du sommeil (QualityofSleep) qualitative ordinale:  
Note subjective de la qualité du sommeil de 1 à 10.  

• Niveau d’activité physique (PhysicalActivityLevel) quantitative discrète:  
La durée quotidienne d’activité physique en minutes.  

• Niveau de stress (StressLevel) qualitative ordinale:  
Note subjective du niveau de stress de la personne de 1 à 10.  

• Catégorie IMC (BMICategory) qualitative catégorielle:  
Catégorie d’IMC (Indice de masse corporelle).  

• Pression sanguine (BloodPressure) qualitative ordinale:  
La pression sanguine de la personne. Elle est définit par la pression sanguine systolique sur la pression sanguine diastolique.  

• Battements du coeur (HeartRate) quantitative discrète:  
Le nombre de battements du coeur en minutes de la personne au repos.  

• Pas quotidien (DailySteps) quantitative discrète:  
Le nombre de pas quotidien effectu´e par la personne.  

• Trouble du sommeil (SleepDisorder) qualitative catégorielle:  
La présence ou absence de troubles du sommeil(apnée du sommeil ou insomnie).  

Détails sur la colonne Sleep Disorder :  
• None : L’individu ne pr´esente aucun trouble spécifique du sommeil.  
• Insomnia : L’individu ´eprouve des difficultés à s’endormir ou à rester endormi,
entrainant un sommeil inadéquat ou de mauvaise qualité.  
• Sleep Apnea : L’individu souffre de pauses respiratoires pendant le sommeil, ce
qui perturbe le sommeil et peut entrainer des risques pour la santé.  

## Méthodes mises en oeuvre

Pour la classification nous utilisons 6 modèles d'apprentissage supervisée qui sont les suivants :  
- La régression logistique  
- L’arbre de décision  
- La forêt aléatoire  
- La machine à vecteurs de support  
- le Gradient Boosting  
- Le Perceptron Multi-Couches  

Les mesures de performance pour un modèle indiquent si le modèle est bien entrainé
et plus généralement s’il classifie bien les données du set de test.  
Voici les mesures de performances que nous avons utilisé :  
- l'accuracy  
- la matrice de confusion  
- la courbe ROC  

## Résultats

Nos modèles ont un taux
de bonnes prédictions aux alentours de 80%, Le meilleur modèle est le Gradient Boosting sur des arbres de d´ecision avec une accuracy de 87.87%. Nous avons pu exploité les
hyper-paramètres pertinents à l’amélioration du modèle. L’étude des features importance
montre que les variables BloodPressureSystolic et ”BloodPressureDiastolic” jouent un
rêle important dans la détection du trouble du sommeil.

Voici la matrice de confusion et la courbe ROC pour notre meilleur modèle :  
![ML_confusion_ROC](https://github.com/user-attachments/assets/3711602c-1d78-45f6-a166-876db524c8a4)  

Et ci-dessous l'importance de nos variables :  
![ML_variable_importance](https://github.com/user-attachments/assets/e5936f2f-fab7-44b1-aa09-0e2be9eaf952)  



