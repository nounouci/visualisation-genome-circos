

# **TP Circos – Visualisation de données génomiques**

## 1. Objectif

L’objectif de ce TP est de représenter graphiquement des données génomiques à l’aide du logiciel **Circos**, en manipulant différents types de données (séquences, annotations, synténie).

---

## 2. Environnement de travail

Le travail a été réalisé sur le cluster **GenOuest**, via une connexion SSH.

Les traitements ont été effectués à l’aide de **scripts Bash** exécutés sur un nœud de calcul (compute node).
Les visualisations ont été produites avec le logiciel **Circos**.

---

## 3. Données utilisées

Les données utilisées pour le génome de *Sorghum bicolor* sont les suivantes :

| Type de données      | Fichier                           |
| -------------------- | --------------------------------- |
| Séquences génomiques | Sbicolor_313_v3.0.fa              |
| Séquences hardmasked | Sbicolor_313_v3.0.hardmasked.fa   |
| Annotations de gènes | Sbicolor_313_v3.1.gene_exons.gff3 |
| Données de synténie  | Sb_Sb.aligncoords.gcoords.txt     |

---

## 4. Méthodes

### 4.1 Préparation des données

Les fichiers ont été organisés dans une structure de projet :

| Dossier  | Contenu           |
| -------- | ----------------- |
| data/    | Données d’entrée  |
| scripts/ | Scripts Bash      |
| results/ | Résultats générés |

---

### 4.2 Génération du karyotype

Un script Bash a permis d’extraire les chromosomes et de calculer leur taille à partir du fichier FASTA.

Seuls les chromosomes principaux (Chr01 à Chr10) ont été conservés, les contigs (super_*) ayant été exclus.

#### Exemple de karyotype :

| Chromosome | Début | Fin      | Couleur |
| ---------- | ----- | -------- | ------- |
| Chr01      | 1     | 80884392 | blue    |
| Chr02      | 1     | 77742459 | blue    |
| Chr03      | 1     | 74386277 | blue    |
| Chr04      | 1     | 68658214 | blue    |
| Chr05      | 1     | 71854669 | blue    |
| Chr06      | 1     | 61277060 | blue    |
| Chr07      | 1     | 65505356 | blue    |
| Chr08      | 1     | 62686529 | blue    |
| Chr09      | 1     | 59416394 | blue    |
| Chr10      | 1     | 61233695 | blue    |

---

### 4.3 Densité des éléments transposables

La densité des éléments transposables a été calculée à partir du fichier **hardmasked**.

Les caractères « N » correspondent aux régions répétées.
Le nombre de « N » a été compté par fenêtres de 100 kb.

#### Exemple de résultat :

| Chromosome | Début  | Fin    | Nombre de N |
| ---------- | ------ | ------ | ----------- |
| Chr01      | 1      | 100000 | 58652       |
| Chr01      | 100001 | 200000 | 34534       |
| Chr01      | 200001 | 300000 | 37062       |

---

### 4.4 Densité des gènes

Les gènes ont été extraits à partir du fichier GFF3.

Le nombre de gènes a été calculé par fenêtres de 100 kb sur chaque chromosome afin d’étudier leur distribution.

---

### 4.5 Synténie intragénomique

Les relations de synténie ont été obtenues à partir du fichier `.gcoords`.

Ces relations ont été converties au format attendu par Circos afin de représenter les correspondances entre régions homologues du génome.

---

## 5. Visualisation avec Circos

Les fichiers générés (karyotype, densité des gènes, densité des transposons, synténie) ont été utilisés dans un fichier de configuration (`circos.conf`).

Circos a permis de produire une représentation circulaire du génome.

---

## 6. Résultats

La visualisation obtenue permet de mettre en évidence :

* l’organisation des chromosomes
* la distribution des gènes le long du génome
* les régions riches en éléments répétés
* les relations de synténie entre différentes régions

---

## 7. Organisation du projet

```
projet_circos/
├── data/
├── scripts/
├── results/
```


* ➜ version **2 pages max (optimisée pour note)**
* ➜ ajouter **interprétation du graphique Circos (très important pour gratter des points)**
