
# **TP Circos – Visualisation de données génomiques**

## 🎯 Objectif

L’objectif de ce TP est de représenter graphiquement des données génomiques à l’aide du logiciel **Circos**, en manipulant différents types de données (séquences, annotations, synténie).

---

## 💻 Environnement de travail

Le travail a été réalisé sur le cluster **GenOuest**, en utilisant une connexion SSH.

Les différentes étapes ont été effectuées via des **scripts Bash** exécutés sur un nœud de calcul (compute node).
Les visualisations ont été générées avec le logiciel **Circos**.

---

## 📂 Données utilisées

Les données utilisées pour le génome de **Sorghum bicolor** sont :

* Séquences génomiques : `Sbicolor_313_v3.0.fa`
* Séquences hardmasked : `Sbicolor_313_v3.0.hardmasked.fa`
* Annotations de gènes : `Sbicolor_313_v3.1.gene_exons.gff3`
* Données de synténie : `Sb_Sb.aligncoords.gcoords.txt`

---

## ⚙️ Méthodes

### 🔹 1. Préparation des données

Les fichiers ont été récupérés depuis le serveur et organisés en dossiers :

* `data/` : données d’entrée
* `scripts/` : scripts Bash
* `results/` : résultats

---

### 🔹 2. Génération du karyotype

Un script Bash a été utilisé pour extraire les chromosomes et calculer leur taille à partir du fichier FASTA.

Seuls les chromosomes (`Chr01` à `Chr10`) ont été conservés, les contigs (`super_*`) ont été exclus.

#### 📊 Exemple de karyotype :

```text
chr - Chr01 Chr01 1 80884392 blue
chr - Chr02 Chr02 1 77742459 blue
chr - Chr03 Chr03 1 74386277 blue
chr - Chr04 Chr04 1 68658214 blue
chr - Chr05 Chr05 1 71854669 blue
chr - Chr06 Chr06 1 61277060 blue
chr - Chr07 Chr07 1 65505356 blue
chr - Chr08 Chr08 1 62686529 blue
chr - Chr09 Chr09 1 59416394 blue
chr - Chr10 Chr10 1 61233695 blue
```

---

### 🔹 3. Densité des éléments transposables

La densité des éléments transposables a été calculée à partir du fichier **hardmasked**.

Les caractères `N` correspondent aux régions répétées.
Le nombre de `N` a été compté par fenêtres de **100 kb**.

#### 📊 Format du fichier :

```text
Chr01   1       100000   10832
Chr01   100001  200000   1683
...
```

---

### 🔹 4. Densité des gènes

Les gènes ont été extraits à partir du fichier GFF3.

Le nombre de gènes a été calculé par fenêtres de **100 kb** sur chaque chromosome.

---

### 🔹 5. Synténie intragénomique

Les données de synténie ont été extraites à partir du fichier `.gcoords`.

Les relations entre régions homologues ont été converties au format compatible avec Circos (`links.txt`).

---

## 🎨 Visualisation avec Circos

Les fichiers générés ont été utilisés dans un fichier de configuration (`circos.conf`) pour produire une visualisation circulaire.

La figure obtenue permet de représenter :

* les chromosomes
* la densité des gènes
* la densité des éléments transposables
* les relations de synténie

---

## 📊 Résultats

La visualisation Circos permet d’observer :

* l’organisation globale du génome
* la distribution non homogène des gènes
* la présence de régions riches en éléments répétés
* les duplications et relations entre régions génomiques

---

## 📁 Organisation du projet

```text
projet_circos/
├── data/
├── scripts/
├── results/
```


* 👉 version **2 pages optimisée PDF**
* 👉 ou ajouter une **explication simple du graphique Circos (très important pour la note)**
