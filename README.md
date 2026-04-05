# TP Circos - Visualisation de données génomiques

## Objectif

L’objectif de ce TP est de représenter des données génomiques à l’aide du logiciel Circos.

## Environnement de travail

Le travail a été réalisé sur le cluster GenOuest en utilisant une connexion SSH.
Les calculs et traitements ont été effectués via des scripts Python, puis les résultats ont été visualisés avec Circos.

## Données

Les données utilisées comprennent :

* des séquences génomiques (.fa)
* des annotations de gènes (.gff)
* des données de synténie (.gcoords)

## Méthodes

### 1. Préparation des données

Les fichiers nécessaires ont été récupérés depuis le serveur et organisés dans un dossier de travail.

### 2. Génération des fichiers

Des scripts Python ont été utilisés pour :

* extraire les chromosomes et leurs tailles (karyotype)
* calculer la densité de gènes par fenêtres de 100 kb
* calculer la densité des éléments répétés
* identifier les relations de synténie

### 3. Visualisation avec Circos

Les fichiers générés ont été utilisés comme entrées pour Circos afin de produire une représentation circulaire du génome.

## Résultats

Le graphique obtenu permet de visualiser :

* l’organisation des chromosomes
* la distribution des gènes
* les éléments répétés
* les relations de synténie entre régions du génome

## Organisation du projet

* `data/` : fichiers d’entrée
* `scripts/` : scripts utilisés
* `results/` : résultats générés

## Auteurs

Ton Nom & Nom du binôme
