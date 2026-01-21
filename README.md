# TP Spark Streaming (DStream) — WordCount (Colab)

Ce dépôt contient une solution simple du TP **Spark Streaming (DStream)** exécutée sur **Google Colab**.

## Objectif
Simuler un flux de données texte via un **serveur socket**, puis traiter ce flux avec Spark Streaming pour calculer le **WordCount en temps réel** (micro-batch de **5 secondes**).

## Contenu
- `solution_tp_spark_streaming_sans_fautes.ipynb` : notebook Colab complet
- `messages.txt` : fichier de messages (1 ligne = 1 message) utilisé par le serveur socket

## Fonctionnement
1. Installation de PySpark
2. Création d’un serveur socket sur `localhost:9999` qui envoie une ligne aléatoire de `messages.txt` toutes les 2 secondes
3. Lecture du flux avec `socketTextStream`
4. Traitement streaming : `flatMap` → `map` → `reduceByKey`
5. Affichage des résultats avec `pprint()`

## Exécution (Colab)
1. Ouvrir le notebook dans Google Colab
2. Exécuter les cellules dans l’ordre
3. Le streaming tourne **30 secondes** puis s’arrête automatiquement

## Remarque
Spark peut afficher un warning indiquant que **DStream est déprécié** (Spark ≥ 3.4). Ce n’est pas une erreur et le TP fonctionne normalement.

---
Auteur : Youssef Bouzit
