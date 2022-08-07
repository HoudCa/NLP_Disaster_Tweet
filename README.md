# Kaggle competition: Natural Language Processing with Disaster Tweets
Dans ce projet, nous ferons une analyse des sentiments couplée à l'apprentissage automatique afin de détecter les tweets de catastrophe de Twitter. Le
but est de déterminer s'il y a une véritable catastrophe ou non d'après le tweet.
Pour cela, nous avons d'utilisé deux modèles pré-entrainés BERT, RoBERTa et évaluer leurs performances respectives en examinant la précision et l'aire sous
la courbe ROC.

# Les données
Le jeu de données utilisé est issu de la compétition Kaggle [Natural Language Processing with Disaster Tweets](https://www.kaggle.com/competitions/nlp-getting-started).
Il est réparti en 7613 tweets pour la formation et 3263 tweets pour la validation.
Il contient les 6 champs suivants :

1. id : Un identifiant unique pour chaque tweet,
2. text : Le texte du tweet,
3. keyword : Un mot-clé du tweet (bien qu'il puisse être vide !),
4. location : L'emplacement d'où le tweet a été envoyé (peut également être
vide),
5. target : Indique si un tweet concerne une véritable catastrophe (1) ou
non (0), seulement dans les fichiers train.csv et sample_submission.csv

Dans le jeu de données pour la formation, il y 57% de tweets annonçant une catastrophe.

Nous avons divisé notre jeu de données en un ensemble de données d'entrainement et de validation en utilisant train_test_split. Nous utiliserons 80% de l'ensemble de 
données comme données d'apprentissage et évaluerons les performances sur les 20% restantes.

# Évaluation des performances
La partie évaluation de notre travail utilise l'évaluateur Kaggle. L'évaluation se compose de 3263 tweet non labellisés que nous classons avec chacun de
nos modèles. Nos simulations ont montré que RoBERTa atteint des meilleurs performances que BERT. En effet, la précision (accuracy) de 83% et dont l'aire
sous la courbe ROC (AUC) est de 89% contre une précision de 57% et une AUC de 68% pour le modèle BERT.

![AUC BERT](https://github.com/HoudCa/NLP_Disaster_Tweet/blob/main/Images/AUC_Bert.png)
![AUC RoBERTa](https://github.com/HoudCa/NLP_Disaster_Tweet/blob/main/Images/AUC_Roberta.png)
