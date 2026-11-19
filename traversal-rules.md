# Traversal — Règles du jeu (référence tournoi)

> **Version :** 2 — 8 novembre 2026 (intègre les décisions du registre `points-bloquants-traversal.md`).
> **Périmètre :** règles du jeu uniquement (le règlement du tournoi : appariements, cadences, arbitrage, etc. est traité à part).
> **Convention :** les passages marqués **⏳ [PB-xx]** renvoient à un point encore ouvert du registre.

---

## Sommaire

0. [Ordre de priorité des sources](#0-ordre-de-priorité-des-sources)
1. [Présentation et objectif](#1-présentation-et-objectif)
2. [Le plateau](#2-le-plateau)
3. [Les pièces](#3-les-pièces)
4. [Mise en place](#4-mise-en-place)
5. [Déroulement d'un tour](#5-déroulement-dun-tour)
6. [Déplacement](#6-déplacement)
7. [Combat](#7-combat)
8. [Arrivée et score](#8-arrivée-et-score)
9. [Fin de partie et victoire](#9-fin-de-partie-et-victoire)
10. [Aide-mémoire](#10-aide-mémoire)
11. [Glossaire](#11-glossaire)

---

## 0. Ordre de priorité des sources

En cas de divergence, les sources font foi dans l'ordre suivant :

1. **le fonctionnement du jeu en ligne** (implémentation technique) ;
2. **le présent règlement** ;
3. **la page officielle « Comment jouer »** de traversalgame.com.

---

## 1. Présentation et objectif

| Élément | Valeur |
|---|---|
| Joueurs | 2 |
| Pièces par joueur | 6 (2 de chaque type) |
| Plateau | grille de 10 × 10 cases, à hauteurs variables |
| Types de pièces | 3 (Explorateur, Avant-garde, Sentinelle) |

**Objectif :** faire traverser le plateau à ses pièces et les faire **sortir par le bord opposé** à sa rangée de départ. Chaque pièce sortie rapporte un nombre de points égal à sa **Force**.

**Fin de partie standard :** dès que **deux pièces au total** sont sorties (qu'elles appartiennent au même joueur ou à des joueurs différents), le joueur au score le plus élevé gagne.

**Victoire spéciale :** si la **toute première** pièce à sortir (tous joueurs confondus) est une **Sentinelle**, son propriétaire gagne immédiatement.

---

## 2. Le plateau

### 2.1 Grille et coordonnées

- Le plateau est une grille de **10 × 10** cases.
- **Colonnes** : **A à J**, de gauche à droite vues du côté du Joueur 1 (rouge).
- **Rangées** : **1 à 10**, la rangée **1** étant la rangée de départ du Joueur 1 (en bas) et la rangée **10** celle du Joueur 2 (en haut).
- **A1** est la case en bas à gauche, **J10** la case en haut à droite (vue du Joueur 1).

### 2.2 Hauteurs

- Chaque case possède une **hauteur** entière comprise entre **0 et 36** (bornes théoriques). En pratique, l'écart entre la case la plus basse et la plus haute d'un plateau est d'environ 8 à 10 unités.
- **Contrainte de relief :** deux cases orthogonalement adjacentes ont au plus **2 unités** de différence de hauteur. Aucune case n'est donc infranchissable.

### 2.3 Génération et modes de terrain

- Chaque partie se joue sur un plateau généré pour ne donner d'avantage notable à aucun camp.
- Pour une édition physique, le **Générateur de plateaux** du site permet de produire un plateau.
- Un mode de terrain peut être choisi avant la partie, exemples:

| Mode | Style de relief |
|---|---|
| Aléatoire | Variété équilibrée de terrains |
| Montagnes | Pics centraux spectaculaires |
| Vallées | Cuvettes profondes bordées de crêtes |
| Hautes terres | Montagnes et vallées réunies |
| Bois | Plutôt plat, collines douces |
| Désert | Étendues plates, rares pics |

> Le choix du mode et l'équité du plateau relèvent du règlement du tournoi.

---

## 3. Les pièces

### 3.1 Caractéristiques

- **Mouvement (M)** : budget de points de déplacement par tour, égal au **nombre de côtés de la base** de la pièce.
- **Force (F)** : puissance de combat et valeur en points à l'arrivée, égale au **nombre de pointes au sommet** de la pièce.
- Pour toutes les pièces, **M + F = 6**.

| Pièce | Forme | Mouvement | Force | Points à l'arrivée | Capacité spéciale |
|---|---|:-:|:-:|:-:|---|
| **Explorateur** | Cône pentagonal | 5 | 1 | 1 | Déplacements spéciaux (§ 6.4) |
| **Avant-garde** | Coin en losange | 4 | 2 | 2 | Charge : +1 en attaque (§ 7.5) |
| **Sentinelle** | Prisme triangulaire | 3 | 3 | 3 | Victoire immédiate si première pièce sortie (§ 9.1) |

---

## 4. Mise en place

### 4.1 Camps

| Joueur | Couleur | Rangée de départ | Sortie par | Joue |
|---|---|:-:|---|---|
| Joueur 1 | Rouge | 1 | le bord au-delà de la rangée 10 | **en premier** |
| Joueur 2 | Bleu | 10 | le bord au-delà de la rangée 1 | en second |

### 4.2 Placement des pièces

Chaque joueur place ses 6 pièces sur les colonnes **C à H** de sa rangée de départ :

| Colonne | C | D | E | F | G | H |
|---|---|---|---|---|---|---|
| Pièce | Sentinelle | Avant-garde | Explorateur | Explorateur | Avant-garde | Sentinelle |

- Joueur 1 : **C1 à H1**.
- Joueur 2 : **C10 à H10**.
- Les colonnes A, B, I et J de chaque rangée de départ restent vides.

```
            A   B   C   D   E   F   G   H   I   J
          ┌───┬───┬───┬───┬───┬───┬───┬───┬───┬───┐
      10  │   │   │ S │ A │ E │ E │ A │ S │   │   │   Joueur 2 (bleu)
          ├───┼───┼───┼───┼───┼───┼───┼───┼───┼───┤
     9…2  │          rangées intermédiaires          │
          ├───┼───┼───┼───┼───┼───┼───┼───┼───┼───┤
       1  │   │   │ S │ A │ E │ E │ A │ S │   │   │   Joueur 1 (rouge)
          └───┴───┴───┴───┴───┴───┴───┴───┴───┴───┘

  S = Sentinelle   A = Avant-garde   E = Explorateur
  Le Joueur 1 sort par le haut (au-delà de la rangée 10), le Joueur 2 par le bas (au-delà de la rangée 1).
```

---

## 5. Déroulement d'un tour

Les joueurs jouent à tour de rôle, en commençant par le **Joueur 1**. À son tour, le joueur actif :

1. choisit **une seule** de ses pièces ;
2. joue **un coup** avec cette pièce :
   - un **déplacement normal** vers une case libre (§ 6.1 à 6.3) ;
   - un **déplacement spécial** s'il s'agit d'un Explorateur (§ 6.4) ;
   - une **attaque** : un déplacement dont la case de destination est occupée par une pièce ennemie (§ 7) ;
   - une **sortie du plateau** pour marquer (§ 8) ;
3. son tour **se termine** immédiatement après ce coup.

**Obligation de jouer :** un joueur **doit** jouer un coup légal à chaque tour. Il est interdit de passer. Le Mouvement non utilisé est perdu.

**Aucun coup légal :** un joueur qui, à son tour, n'a **aucun coup légal** (toutes ses pièces sont bloquées, seules des attaques perdantes sont possibles, ou il n'a plus de pièce sur le plateau) **perd la partie**.

---

## 6. Déplacement

### 6.1 Principe : un coup est défini par sa case d'arrivée

- Une pièce se déplace **orthogonalement** (avant, arrière, gauche, droite), case par case. Elle ne se déplace jamais en diagonale, sauf par le déplacement spécial de l'Explorateur.
- Un déplacement est défini uniquement par sa **case d'arrivée**. Une case est **accessible** s'il existe un chemin orthogonal :
  - qui ne traverse **aucune pièce** (alliée ou ennemie) ;
  - dont le **coût total** (§ 6.2) est **inférieur ou égal** au Mouvement de la pièce.
- La pièce peut changer de direction en cours de chemin. Le chemin exact emprunté n'a pas d'importance : seul compte le coût du chemin le moins cher jusqu'à la case d'arrivée.
- **La case d'arrivée ne peut pas être la case de départ** : un déplacement nul est interdit. (Au tour suivant, la pièce peut revenir sur une case qu'elle occupait auparavant.)

### 6.2 Coût d'un pas

**Coût d'un pas = |différence de hauteur| + 1.** Monter et descendre coûtent la même chose.

| Différence de hauteur | Coût |
|:-:|:-:|
| 0 (plat) | 1 |
| 1 | 2 |
| 2 | 3 |

**Exemple** (chemin 2 → 2 → 4 → 3 → 1) : 1 + 3 + 2 + 3 = **9 points**.

### 6.3 Résumé des interdictions

1. Traverser une pièce, alliée ou ennemie.
2. Terminer son déplacement sur sa case de départ.
3. Terminer sur une case occupée par une pièce alliée.
4. Dépasser son budget de Mouvement.

### 6.4 Déplacements spéciaux de l'Explorateur

À chaque tour, **au lieu** d'un déplacement normal, un Explorateur peut effectuer **un seul** des deux déplacements spéciaux suivants, à partir de la case qu'il occupe au début du tour. Ils ne consomment pas de Mouvement et **ignorent le relief**.

| Déplacement spécial | Description | Conditions |
|---|---|---|
| **Pas en diagonale** | 1 case en diagonale | Autorisé même si les deux cases orthogonales qui le bordent sont occupées |
| **Bond en ligne droite** | 2 cases dans une direction orthogonale | La **case intermédiaire doit être libre** (pas de saut par-dessus une pièce) |

- La case d'arrivée doit être **libre** ou occupée par une **pièce ennemie**, auquel cas le déplacement spécial est une **attaque** (§ 7).
- Un déplacement spécial ne se combine pas avec un déplacement normal.
- Un déplacement spécial peut faire **sortir** l'Explorateur du plateau (§ 8.2).

**Exemple :** un Explorateur entouré orthogonalement (S = Sentinelle, A = Avant-garde, O = case libre) peut quand même se déplacer en diagonale vers n'importe quelle case O :

```
  O  S  O
  A  E  A
  O  S  O
```

---

## 7. Combat

### 7.1 Principe

Une **attaque** est un coup dont la **case d'arrivée est occupée par une pièce ennemie**. Il n'est pas nécessaire d'être adjacent à la cible au début du tour :

- **déplacement normal :** la case de la cible doit être accessible selon les règles du § 6.1. Le pas qui **entre dans la case de la cible** coûte |Δh| + 1 comme tout autre pas et compte dans le budget de Mouvement ;
- **Explorateur :** un pas en diagonale ou un bond (§ 6.4) peut aussi se terminer sur une pièce ennemie.

*Exemple :* deux Explorateurs ennemis sur terrain plat. Si le premier peut atteindre la case du second en 5 points de Mouvement ou moins, il peut l'attaquer (Force 1 contre 1 : l'attaque réussit).

### 7.2 Résolution

1. Calculer la **Force effective de l'attaquant** (§ 7.3) et celle du **défenseur** (§ 7.4).
2. Comparer :
   - **Attaquant ≥ Défenseur** → le défenseur est **capturé**, définitivement retiré de la partie, et **l'attaquant prend sa case** ;
   - **Attaquant < Défenseur** → l'attaque est **interdite** : ce coup n'est pas légal.
3. L'attaque **met fin au tour**.

> Une attaque ne peut jamais échouer : seules les attaques gagnantes (ou à égalité) sont des coups légaux.

### 7.3 Force effective de l'attaquant

**Attaquant = Force de base + Modificateur de hauteur + Alliés + Charge (Avant-garde)**

Tous les modificateurs se **cumulent**.

| Modificateur | Condition | Effet |
|---|---|:-:|
| **Hauteur** | Case occupée par l'attaquant **au début du tour** plus **haute** que la case de la cible | **+1** |
| | … plus **basse** que la case de la cible | **−1** |
| | … de même hauteur | 0 |
| **Alliés** | Chaque **autre** pièce de l'attaquant **orthogonalement adjacente à la cible** | **+ sa Force de base** |
| **Charge** | Avant-garde uniquement, voir § 7.5 | **+1** |

- Le modificateur de hauteur vaut toujours **±1**, quelle que soit l'ampleur de la différence.
- Il compare la case de départ du tour à la case de la cible, et non la case traversée juste avant la cible.
- Les alliés n'apportent que leur **Force de base**, sans aucun modificateur.

### 7.4 Force effective du défenseur

**Défenseur = Force de base + Renforts**

| Modificateur | Condition | Effet |
|---|---|:-:|
| **Renforts** | Chaque pièce alliée du défenseur **orthogonalement adjacente au défenseur** | **+1** par pièce, quelle que soit sa Force |

Le défenseur n'a pas de modificateur de hauteur propre : le relief n'intervient que par le modificateur de l'attaquant.

### 7.5 Charge de l'Avant-garde

Une Avant-garde gagne **+1 en Force d'attaque** si, et seulement si, le **coût du chemin le moins cher** jusqu'à la case de la cible est **exactement 4**.

- Le coût inclut le pas qui entre dans la case de la cible.
- Il est calculé sur le **plateau réel** : relief **et** pièces présentes (qui bloquent le passage).
- Le bonus est **automatique**. Si le chemin le moins cher coûte 1, 2 ou 3, il n'y a pas de bonus, même si un détour coûtant 4 existe.

### 7.6 Exemples officiels

**Exemple 1 — Avantage de la colline**

| | Attaquant : Avant-garde rouge | Défenseur : Avant-garde bleue |
|---|:-:|:-:|
| Force de base | 2 | 2 |
| Hauteur (départ du tour plus haut que la cible) | +1 | — |
| Renfort (1 Sentinelle bleue orthogonalement adjacente) | — | +1 |
| **Force effective** | **3** | **3** |

Résultat : 3 ≥ 3 → l'Avant-garde bleue est capturée et l'Avant-garde rouge prend sa case. Une Sentinelle en renfort n'apporte que +1.

**Exemple 2 — Assaut allié**

| | Attaquant : Explorateur rouge | Défenseur : Sentinelle bleue |
|---|:-:|:-:|
| Force de base | 1 | 3 |
| Allié (Avant-garde rouge orthogonalement adjacente à la cible) | +2 | — |
| **Force effective** | **3** | **3** |

Résultat : 3 ≥ 3 → la Sentinelle bleue est capturée. L'Explorateur, parti à 3 cases sur terrain plat (coût 3 ≤ 5), prend sa case.

---

## 8. Arrivée et score

### 8.1 Sortie par déplacement normal

- Une pièce qui se trouve sur sa **dernière rangée** (rangée 10 pour le Joueur 1, rangée 1 pour le Joueur 2) peut **sortir du plateau** par le bord opposé à son camp.
- La sortie coûte **toujours exactement 1 point de Mouvement**, quelle que soit la hauteur de la case.
- Une pièce peut atteindre la dernière rangée, s'y déplacer et sortir **dans le même tour**, si son budget le permet.
- La sortie est **facultative** et **met fin au tour**.
- Il est impossible de quitter le plateau par les bords latéraux ou par son propre bord de départ.

### 8.2 Sortie de l'Explorateur par déplacement spécial

L'Explorateur peut aussi sortir :

- par un **bond** vers l'avant depuis l'avant-dernière rangée (la case intermédiaire, sur la dernière rangée, doit être libre) ou depuis la dernière rangée ;
- par un **pas en diagonale** vers l'avant depuis la dernière rangée.

### 8.3 Points

La pièce sortie est retirée du jeu et le joueur marque sa **Force de base** :

| Pièce | Points |
|---|:-:|
| Explorateur | 1 |
| Avant-garde | 2 |
| Sentinelle | 3 |

---

## 9. Fin de partie et victoire

Les conditions sont vérifiées après chaque coup, **dans l'ordre suivant**.

### 9.1 Victoire spéciale de la Sentinelle (immédiate)

Si une **Sentinelle** est la **toute première pièce** de la partie (tous joueurs confondus) à sortir, son joueur **gagne immédiatement**. Si une autre pièce est déjà sortie, la Sentinelle rapporte simplement 3 points.

### 9.2 Victoire standard (2ᵉ pièce sortie)

Dès que la **deuxième pièce** de la partie sort, la partie s'arrête :

- score de chaque joueur = somme des Forces de base de ses pièces sorties ;
- le **score le plus élevé** gagne ;
- en cas d'**égalité**, la partie est **nulle**.

| 1ʳᵉ sortie | 2ᵉ sortie | Score J1 – J2 | Résultat |
|---|---|:-:|---|
| Sentinelle J1 | — | 3 - 0 | J1 gagne immédiatement |
| Explorateur J1 | Sentinelle J2 | 1 – 3 | J2 gagne |
| Avant-garde J1 | Avant-garde J2 | 2 – 2 | Nulle |
| Explorateur J1 | Avant-garde J1 | 3 – 0 | J1 gagne |
| Avant-garde J1 | Sentinelle J1 | 5 - 0 | J1 gagne |

### 9.3 Défaite faute de coup légal

Un joueur qui n'a aucun coup légal au début de son tour **perd** (§ 5). C'est notamment le cas d'un joueur qui n'a plus aucune pièce sur le plateau.

Cette règle ne s'applique que si la partie continue. Si le coup qui retire la dernière pièce d'un joueur met fin à la partie (sa Sentinelle sort en premier, ou sa pièce est la 2ᵉ à sortir), le résultat est celui des § 9.1 ou 9.2.

*Exemple :* il ne reste au Joueur 1 qu'une Sentinelle, et aucune pièce n'est encore sortie. Elle sort : le Joueur 1 gagne immédiatement (§ 9.1), même s'il n'a plus de pièce.

### 9.4 Limite de 200 coups

- Un **coup** est l'action d'un joueur. La limite est de **200 coups au total**, soit 100 par joueur. La partie s'arrête après le 200ᵉ coup, joué par le Joueur 2.
- Si ce 200ᵉ coup déclenche une fin de partie des § 9.1 à 9.3, celle-ci s'applique.
- Sinon, le résultat est déterminé ainsi :
  1. le **score le plus élevé** gagne (à ce stade, au plus une pièce est sortie) ;
  2. si **aucun joueur n'a marqué** : gagne le joueur dont la pièce la plus avancée est **la plus proche de son arrivée**, en nombre de rangées restant à franchir (sans tenir compte du relief) ;
  3. à égalité de distance : gagne celui dont la pièce la plus avancée a la **Force la plus élevée** ⏳ [PB-24] ;
  4. à égalité de Force : partie **nulle**.

**Répétition de position :** aucune règle de répétition ne s'applique. Jouer des allers-retours, par exemple pour atteindre la limite de 200 coups, est une stratégie légitime.

---

## 10. Aide-mémoire

```
ORDRE       Joueur 1 (rouge, rangée 1) commence · 1 pièce → 1 coup → fin du tour · passer interdit
            aucun coup légal = défaite

COORDONNÉES colonnes A–J, rangées 1–10, A1 en bas à gauche (côté rouge)
MISE EN PL. C–H : S A E E A S   (J1 en rangée 1, J2 en rangée 10)

DÉPLACER    orthogonal · coût d'un pas = |Δh| + 1 · coup défini par sa case d'arrivée
            chemin le moins cher ≤ M · pas de traversée de pièce · arrivée ≠ case de départ

EXPLORATEUR (M5 F1)  au choix : 1 diagonale (même entre 2 pièces) OU bond de 2 (case du milieu libre)
            relief ignoré · peut attaquer et sortir par ces déplacements

AVANT-GARDE (M4 F2)  +1 en attaque si le chemin le moins cher (relief + pièces) jusqu'à la cible coûte exactement 4

SENTINELLE  (M3 F3)  1re pièce de la partie à sortir → victoire immédiate

ATTAQUE     = coup qui se termine sur une pièce ennemie (le pas d'entrée est payé) · l'attaquant prend la case
            Att = F + hauteur (case de départ du tour vs case cible : +1 / 0 / −1)
                    + Σ F de base des autres alliés orthogonalement adjacents à la cible + 1 charge AG
            Déf = F + 1 par allié orthogonalement adjacent au défenseur
            Att ≥ Déf → capture · Att < Déf → coup interdit

SORTIE      depuis la dernière rangée, coût fixe 1 · facultative · même tour possible

FIN         Sentinelle 1re sortie → victoire · 2e pièce sortie → meilleur score (égalité = nulle)
            200 coups au total → score > rangées restantes > Force > nulle
```

---

## 11. Glossaire

| Terme | Définition |
|---|---|
| **Adjacent** | Orthogonalement voisin : case directement devant, derrière, à gauche ou à droite. Les diagonales ne comptent pas. |
| **Alliés** | En attaque : les autres pièces de l'attaquant orthogonalement adjacentes à la cible. |
| **Arrivée** | Bord du plateau opposé à la rangée de départ d'un joueur, par lequel ses pièces sortent pour marquer. |
| **Case accessible** | Case libre ou ennemie atteignable par un chemin orthogonal sans traverser de pièce, pour un coût total ≤ Mouvement. |
| **Charge** | Bonus d'attaque +1 de l'Avant-garde (§ 7.5). |
| **Coup** | Action d'un joueur pendant son tour (déplacement, déplacement spécial, attaque ou sortie). |
| **Dernière rangée** | Rangée 10 pour le Joueur 1, rangée 1 pour le Joueur 2. |
| **Force de base** | Force imprimée de la pièce (1, 2 ou 3), avant tout modificateur. |
| **Force effective** | Force après application des modificateurs de combat. |
| **Mouvement** | Budget de points de déplacement d'une pièce pour un tour. |
| **Renforts** | En défense : pièces alliées orthogonalement adjacentes au défenseur (+1 chacune). |
