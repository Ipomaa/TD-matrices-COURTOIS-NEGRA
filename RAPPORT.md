# TD — Stockage de matrices en C

**Programmation modulaire et séparée, fichiers texte et allocation dynamique**

| Membre | Identifiant GitHub |
|---|---|
| NEGRA Ahmed | [@NegraAhmed](https://github.com/NegraAhmed) |
| COURTOIS Léandre | [@Ipomaa](https://github.com/Ipomaa) |

- **Formation :** 3e année STI — INSA Centre Val de Loire
- **Groupe de TD :** NEGRA Ahmed, COURTOIS Léandre
- **Date de remise :** 
- **Dépôt :** [Ipomaa/Projet_Programmation_C](https://github.com/Ipomaa/Projet_Programmation_C)

## Table des matières

1. [Introduction](#1-introduction)
2. [Exercice 1 : allocation et destruction](#2-exercice-1--allocation-et-destruction)
3. [Exercice 2 : entrées-sorties](#3-exercice-2--entrées-sorties)
4. [Exercice 3 : calcul matriciel](#4-exercice-3--calcul-matriciel)
5. [Exercice 4 : démonstration complète](#5-exercice-4--démonstration-complète)

---

## 1. Introduction

### Le problème

L'objectif du TD est d'écrire une petite bibliothèque C permettant de créer, sauvegarder, relire, afficher, additionner et multiplier des matrices d'entiers de taille quelconque. Une matrice est représentée par une structure `Matrice` qui contient ses dimensions et un tableau de pointeurs de lignes (`int **coef`), chaque ligne étant allouée séparément dans le tas.

La bibliothèque est découpée en quatre modules, chacun formé d'un fichier d'en-tête (`.h`, l'interface) et d'un fichier d'implémentation (`.c`) :

| Module | Rôle |
|---|---|
| `matrice` | type `Matrice`, codes d'erreur `MatErreur`, outils communs |
| `matrice_alloc` | création et destruction d'une matrice |
| `matrice_io` | lecture, écriture et affichage d'une matrice (fichier texte) |
| `matrice_calcul` | addition et multiplication de deux matrices |

Un programme de démonstration (`main.c`) utilise ces modules : il lit deux matrices dans des fichiers, calcule leur somme ou leur produit, affiche le résultat et l'enregistre. Toutes les fonctions qui peuvent échouer renvoient un code `MatErreur` et respectent des règles de propriété de la mémoire (R1 à R7), afin d'éviter toute fuite, y compris en cas d'erreur.

### Objectifs du TD

- séparer l'interface d'un module (`.h`) de son implémentation (`.c`) ;
- compiler séparément plusieurs modules, puis les assembler par édition de liens ;
- allouer dynamiquement une matrice à deux niveaux, en gérant l'échec partiel d'allocation ;
- respecter des règles de propriété de la mémoire (qui alloue, qui libère) ;
- lire et écrire un fichier texte en vérifiant chaque opération ;
- programmer l'addition et la multiplication en contrôlant les dimensions et le dépassement de capacité ;
- mettre en place une gestion d'erreurs uniforme et la vérifier par des tests.

### État du projet à la remise

**Les exercices 1 à 4 sont complets.**

| Exercice | Fichier(s) complété(s) | Résultat |
|---|---|---|
| 1 — Allocation et destruction | `matrice.c`, `matrice_alloc.c` | `test_ex1` : **16 / 16** |
| 2 — Entrées-sorties | `matrice_io.c` | `test_ex2` : **14 / 14** |
| 3 — Calcul matriciel | `matrice_calcul.c` | `test_ex3` : **14 / 14** |
| 4 — Démonstration complète | `main.c` | **10 / 10** scénarios de la section 6.5 conformes |

- Tous les fichiers compilent **sans aucun avertissement** avec `-std=c11 -Wall -Wextra -Wpedantic`.
- Il ne reste aucune ligne provisoire dans les fichiers complétés.
- Le fichier produit par le scénario 1 est relu correctement par le programme lui-même (`add R.txt R.txt R2.txt`).
- `valgrind --leak-check=full` affiche *All heap blocks were freed* et 0 erreur pour `test_ex1`, `test_ex2`, `test_ex3` et `demo_matrices`.

**Limites et remarques :**

- Nous avons compilé et exécuté les tests sous Windows (gcc MinGW 16.2). **valgrind n'existant pas sous Windows**, nous avons vérifié les fuites mémoire sous **Linux**. L'outil équivalent sous Windows, Dr. Memory, s'arrête avec une erreur interne avec notre version de gcc : nous n'avons donc pas pu l'utiliser.
- Sous Windows, le *Contrôle intelligent des applications* bloquait l'exécution des programmes compilés (exécutables non signés). Nous avons dû le désactiver pour lancer les tests.
- Les réponses aux questions de réflexion se trouvent dans la section de chaque exercice.

---

## 2. Exercice 1 : allocation et destruction

_À rédiger._

## 3. Exercice 2 : entrées-sorties

_À rédiger._

## 4. Exercice 3 : calcul matriciel

_À rédiger._

## 5. Exercice 4 : démonstration complète

_À rédiger._
