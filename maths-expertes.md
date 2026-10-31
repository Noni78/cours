---
title: Mathématiques expertes
permalink: /maths-expertes.html
---

# Mathématiques expertes

*Fiche de révision — Terminale*

[← Retour au sommaire des cours](index.html) · Pour conserver une copie PDF, utiliser la fonction **Imprimer** du navigateur.

## Sommaire
- [1. Nombres complexes](#1-nombres-complexes)
  - [1.1. Définition et forme algébrique](#11-definition-et-forme-algebrique)
  - [1.2. Calculs algébriques](#12-calculs-algebriques)
  - [1.3. Conjugué et inverse](#13-conjugue-et-inverse)
  - [1.4. Équations faisant intervenir z et z̄](#14-equations-faisant-intervenir-z-et-z)
  - [1.5. Module, argument et représentation](#15-module-argument-et-representation)
  - [1.6. Équations polynomiales](#16-equations-polynomiales)
  - [1.7. Pièges et checklist](#17-pieges-et-checklist)
- [2. Matrices](#2-matrices)
  - [2.1. Vocabulaire et dimensions](#21-vocabulaire-et-dimensions)
  - [2.2. Opérations](#22-operations)
  - [2.3. Puissances d’une matrice](#23-puissances-dune-matrice)
  - [2.4. Inverse d’une matrice](#24-inverse-dune-matrice)
  - [2.5. Systèmes linéaires et équations matricielles](#25-systemes-lineaires-et-equations-matricielles)
  - [2.6. Pièges et checklist](#26-pieges-et-checklist)
- [3. Graphes](#3-graphes)
  - [3.1. Vocabulaire](#31-vocabulaire)
  - [3.2. Représenter un graphe](#32-representer-un-graphe)
  - [3.3. Matrice d’adjacence et chemins](#33-matrice-dadjacence-et-chemins)
  - [3.4. Connexité, parcours et recherche de chemin](#34-connexite-parcours-et-recherche-de-chemin)
  - [3.5. Plus court chemin et Dijkstra](#35-plus-court-chemin-et-dijkstra)
  - [3.6. Coloration et nombre chromatique](#36-coloration-et-nombre-chromatique)
  - [3.7. Pièges et checklist](#37-pieges-et-checklist)
- [Annexe — Synthèse des réflexes en contrôle](#annexe--synthese-des-reflexes-en-controle)
  - [Maths expertes](#maths-expertes)
  - [Plan de révision conseillé](#plan-de-revision-conseille)
  - [Sources officielles](#sources-officielles)

Les nombres complexes servent à la fois au calcul algébrique et à la géométrie du plan. Il faut savoir choisir la forme la plus efficace : algébrique pour additionner et résoudre certaines équations, trigonométrique ou exponentielle pour multiplier, diviser et calculer des puissances.

## 1. Nombres complexes

### 1.1. Définition et forme algébrique

Un nombre complexe s’écrit z = a + ib, avec a et b réels et i² = −1. L’ensemble des nombres complexes est noté ℂ. Tout réel est un complexe dont la partie imaginaire est nulle.

| Notation | Définition | Interprétation |
| --- | --- | --- |
| Re(z) = a | Partie réelle de z | Abscisse du point image |
| Im(z) = b | Partie imaginaire de z | Ordonnée du point image |
| i | Unité imaginaire, i² = −1 | Le point image de i est (0 ; 1) |
| z = a + ib | Forme algébrique | Écriture adaptée aux sommes et aux équations cartésiennes |

> Égalité : a + ib = c + id  ⇔  a = c et b = d

Deux complexes sont égaux si et seulement si leurs parties réelles sont égales et leurs parties imaginaires sont égales. On identifie donc les deux coordonnées.

### 1.2. Calculs algébriques

> Addition : (a + ib) + (c + id) = (a + c) + i(b + d)

> Multiplication : (a + ib)(c + id) = (ac − bd) + i(ad + bc)

> Puissances de i : i² = −1 ;  i³ = −i ;  i⁴ = 1 ; les puissances se répètent tous les 4

Pour développer un produit, on distribue comme avec des polynômes, puis on remplace chaque i² par −1. Pour une puissance entière, le binôme de Newton peut être utilisé :

> Binôme de Newton : (a + b)ⁿ = Σ(k=0 à n) C(n,k) aⁿ⁻ᵏ bᵏ

> MÉTHODE  Développer, regrouper les termes réels et les termes en i, puis réduire. À la fin, toujours remettre le résultat sous la forme x + iy.

### 1.3. Conjugué et inverse

Si z = a + ib, son conjugué est z̄ = a − ib. Géométriquement, les points images de z et z̄ sont symétriques par rapport à l’axe réel.

> Identités : z + z̄ = 2Re(z) ;  z − z̄ = 2i Im(z) ;  z z̄ = \|z\|² = a² + b²

> Conjugaison : (z + w)̄ = z̄ + w̄ ;  (zw)̄ = z̄w̄ ;  (zⁿ)̄ = (z̄)ⁿ

> Inverse : 1/z = z̄ / \|z\|² = (a − ib)/(a² + b²), pour z ≠ 0

Le conjugué permet de transformer un dénominateur complexe en dénominateur réel. Pour calculer z/w, avec w non nul, on multiplie le numérateur et le dénominateur par w̄.

### 1.4. Équations faisant intervenir z et z̄

On pose z = x + iy, donc z̄ = x − iy, avec x et y réels. On remplace dans l’équation, puis on identifie les parties réelle et imaginaire.

#### Exemple corrigé - équation avec conjugué

Résoudre z + 2z̄ = 3 + i.

Poser z = x + iy et z̄ = x − iy.

(x + iy) + 2(x − iy) = 3 + i, donc 3x − iy = 3 + i.

Identification : 3x = 3 et −y = 1, donc x = 1 et y = −1.

> RÉSULTAT  La solution est z = 1 − i.

Pour une équation linéaire az = b, si a ≠ 0, l’unique solution est z = b/a. Si a = 0, on distingue b = 0 (tous les complexes sont solutions) et b ≠ 0 (aucune solution).

### 1.5. Module, argument et représentation

Le complexe z = a + ib est représenté par le point M(a ; b) dans le plan complexe. Son module est la distance OM. Pour z non nul, un argument est une mesure de l’angle orienté entre l’axe réel positif et le vecteur OM.

> Module : \|z\| = √(a² + b²) ;  \|z\|² = z z̄

> Argument : arg(z) = θ  ⇔  z/\|z\| = cos θ + i sin θ, modulo 2π

> Produit et quotient : \|zw\| = \|z\|\|w\| ;  \|z/w\| = \|z\|/\|w\| ;  arg(zw) = arg(z) + arg(w) [2π]

| Situation | Argument possible |
| --- | --- |
| z = a + 0i avec a > 0 | 0 [2π] |
| z = a + 0i avec a < 0 | π [2π] |
| z = ib avec b > 0 | π/2 [2π] |
| z = ib avec b < 0 | −π/2 [2π] |
| z = 0 | Pas d’argument |

Pour déterminer l’argument à partir de a et b, on commence par repérer le quadrant. Il ne suffit pas de calculer arctan(b/a), car cette fonction ne distingue pas toujours les quadrants. La calculatrice peut donner un argument principal, à vérifier avec le signe de a et de b.

> À RETENIR  Un argument n’est jamais unique : si θ est un argument, alors θ + 2kπ l’est aussi pour tout entier k. On écrit souvent arg(z) = θ [2π].

### 1.6. Équations polynomiales

Pour une équation du second degré az² + bz + c = 0 à coefficients réels et a ≠ 0, on utilise le discriminant Δ = b² − 4ac. Si Δ < 0, les solutions complexes sont conjuguées.

> Second degré : Δ = b² − 4ac ; si Δ < 0 : z = (−b ± i√(−Δ))/(2a)

Si un polynôme P admet a pour racine, alors P(z) est divisible par z − a : il existe un polynôme Q tel que P(z) = (z − a)Q(z). Un polynôme de degré n admet au plus n racines distinctes. Pour résoudre un degré 3 avec une racine connue, effectuer la division ou la factorisation par z − a, puis résoudre le facteur de degré 2.

### 1.7. Pièges et checklist

- Ne pas confondre Im(z) avec iz : Im(z) est un réel.

- Ne pas oublier que i² = −1 et non +1.

- Ne pas diviser par un complexe sans vérifier qu’il est non nul.

- L’argument est défini seulement pour z ≠ 0 et modulo 2π.

- Vérifier le quadrant avant de valider un argument calculé à la calculatrice.

- Pour additionner, soustraire ou développer, on utilise la forme algébrique ; pour une puissance simple, on développe puis on réduit en remplaçant i² par −1.

- Dans une équation avec z et z̄, poser z = x + iy avant de séparer les parties réelle et imaginaire.

- ☐ Calculer un conjugué, un module, un argument et un inverse.

- ☐ Calculer le module et déterminer un argument en tenant compte du quadrant.

- ☐ Calculer un produit, un quotient et une puissance en choisissant la bonne forme.

- ☐ Résoudre une équation polynomiale simple et une équation avec z̄.

## 2. Matrices

Une matrice est un tableau rectangulaire de nombres. Elle peut représenter un système linéaire, une transformation, une évolution ou les connexions d’un graphe. Les puissances de matrices sont particulièrement importantes en Maths expertes.

### 2.1. Vocabulaire et dimensions

Une matrice A de dimension m × n possède m lignes et n colonnes. Le coefficient situé à la ligne i et à la colonne j se note aᵢⱼ. Une matrice carrée possède autant de lignes que de colonnes.

| Type | Description |
| --- | --- |
| Matrice nulle 0 | Tous les coefficients sont nuls. |
| Matrice identité Iₙ | Matrice carrée avec des 1 sur la diagonale et des 0 ailleurs. |
| Matrice diagonale | Tous les coefficients hors diagonale sont nuls. |
| Matrice ligne | Une seule ligne (dimension 1 × n). |
| Matrice colonne | Une seule colonne (dimension m × 1). |
| Matrice symétrique | Aᵀ = A ; elle est carrée. |

> Condition d’addition : A + B défini si A et B ont la même dimension

> Condition de produit : AB défini si le nombre de colonnes de A = nombre de lignes de B

### 2.2. Opérations

L’addition se fait coefficient par coefficient. La multiplication d’une matrice par un réel multiplie tous ses coefficients. Le produit matriciel s’effectue en multipliant chaque ligne de la première matrice par chaque colonne de la seconde, puis en additionnant les produits.

> Coefficient du produit : (AB)ᵢⱼ = Σₖ aᵢₖ bₖⱼ

> Propriétés : A I = I A = A ;  A(B + C) = AB + AC ;  (AB)C = A(BC)

> ATTENTION  En général, AB ≠ BA. Le produit matriciel n’est pas commutatif. Même lorsque AB et BA existent tous les deux, ils peuvent être différents.

#### Exemple corrigé - produit 2 × 2

A = [[1, 2], [0, 1]] et B = [[2, 1], [3, 0]].

AB = [[1×2 + 2×3, 1×1 + 2×0], [0×2 + 1×3, 0×1 + 1×0]].

AB = [[8, 1], [3, 0]]. En inversant l’ordre, BA = [[2, 5], [3, 6]].

> RÉSULTAT  AB est différent de BA : l’ordre du produit compte.

### 2.3. Puissances d’une matrice

Les puissances A², A³, … ne sont définies que pour une matrice carrée. On pose A⁰ = I. Pour calculer Aⁿ, on peut multiplier successivement, utiliser une relation de récurrence, une diagonalisation si elle a été étudiée, ou la calculatrice selon les consignes.

> Puissance : Aⁿ = A × A × … × A (n facteurs) ;  A⁰ = I

Pour calculer Aⁿ, on multiplie A par elle-même n fois. À chaque étape, il faut vérifier que les dimensions permettent le produit et respecter l’ordre des facteurs.

### 2.4. Inverse d’une matrice

Une matrice carrée A est inversible s’il existe une matrice A⁻¹ telle que AA⁻¹ = A⁻¹A = I. L’inverse n’existe pas toujours. Pour une matrice 2 × 2, on peut utiliser le déterminant.

> Déterminant 2 × 2 : A = [[a,b],[c,d]] ; det(A) = ad − bc

> Inverse 2 × 2 : Si ad − bc ≠ 0 : A⁻¹ = 1/(ad−bc) × [[d,−b],[−c,a]]

> Propriétés : (AB)⁻¹ = B⁻¹A⁻¹ ;  (A⁻¹)⁻¹ = A

### 2.5. Systèmes linéaires et équations matricielles

Un système de plusieurs équations linéaires peut s’écrire AX = B, où A contient les coefficients, X les inconnues et B les constantes. Si A est inversible, la solution unique est X = A⁻¹B.

### 2.6. Pièges et checklist

- Vérifier les dimensions avant d’additionner ou de multiplier.

- Respecter l’ordre des facteurs dans un produit matriciel.

- Ne pas confondre A² avec le carré de chaque coefficient de A.

- Ne calculer A⁻¹ que si A est inversible.

- ☐ Effectuer un produit matriciel et vérifier sa dimension.

- ☐ Calculer une puissance et utiliser une matrice identité.

- ☐ Calculer ou exploiter l’inverse d’une matrice.

- ☐ Écrire un système linéaire sous la forme AX = B.

## 3. Graphes

Un graphe modélise des relations entre des objets : routes entre villes, connexions d’un réseau, relations dans un groupe, transitions entre états. Les graphes interagissent avec les matrices grâce à la matrice d’adjacence.

### 3.1. Vocabulaire

| Terme | Définition |
| --- | --- |
| Sommet | Objet représenté par un point du graphe. |
| Arête | Lien non orienté entre deux sommets. |
| Arc | Lien orienté : il va d’un sommet de départ vers un sommet d’arrivée. |
| Sommets adjacents | Deux sommets reliés par une arête (ou par un arc selon la convention). |
| Ordre | Nombre de sommets du graphe. |
| Degré d’un sommet | Nombre d’arêtes incidentes ; une boucle compte deux fois dans un graphe non orienté. |
| Chaîne | Suite de sommets consécutifs reliés par des arêtes. |
| Longueur | Nombre d’arêtes de la chaîne. |
| Cycle | Chaîne fermée : départ et arrivée identiques. |
| Connexe | Dans un graphe non orienté, tout couple de sommets est relié par une chaîne. |
| Graphe complet Kₙ | Chaque paire de sommets distincts est reliée. |

> Lemme des poignées de main : Somme des degrés = 2 × nombre d’arêtes (graphe non orienté)

> Graphe complet : Nombre d’arêtes de Kₙ = n(n−1)/2

Dans un graphe orienté, on distingue le degré entrant (nombre d’arcs qui arrivent) et le degré sortant (nombre d’arcs qui partent). Dans un graphe pondéré, chaque arête ou arc possède un poids : distance, durée, coût, capacité, etc.

### 3.2. Représenter un graphe

Trois représentations fréquentes : dessin du graphe, liste des voisins/successeurs, matrice d’adjacence. La représentation dépend des opérations que l’on souhaite effectuer.

| Représentation | Principe | Point fort / limite |
| --- | --- | --- |
| Dessin | Sommets et liens dessinés. | Très lisible pour un petit graphe, peu pratique pour un grand. |
| Liste de successeurs | Pour chaque sommet, liste des voisins accessibles. | Économe si peu de liens ; pratique pour parcourir. |
| Matrice d’adjacence | Tableau carré dont les coefficients indiquent les liens. | Accès rapide au test d’un lien ; coûteuse si le graphe est très creux. |

Pour un graphe non orienté simple, la matrice d’adjacence est symétrique : aᵢⱼ = aⱼᵢ. Pour un graphe orienté, aᵢⱼ vaut 1 si un arc va de i vers j, et 0 sinon. Pour un graphe pondéré, on peut placer le poids à la place du 1, en adoptant une convention claire pour l’absence d’arête.

### 3.3. Matrice d’adjacence et chemins

Si M est la matrice d’adjacence d’un graphe, le coefficient (i,j) de Mⁿ donne le nombre de chaînes (ou chemins orientés selon le graphe) de longueur n allant du sommet i au sommet j. C’est une propriété centrale du lien entre graphes et matrices.

> Interprétation de la puissance : (Mⁿ)ᵢⱼ = nombre de chaînes de longueur n de i vers j

### 3.4. Connexité, parcours et recherche de chemin

Pour tester si un graphe non orienté est connexe, on lance un parcours depuis un sommet et on vérifie si tous les sommets sont atteints. Deux méthodes classiques : parcours en profondeur (DFS) et parcours en largeur (BFS).

| Parcours | Structure utilisée | Principe |
| --- | --- | --- |
| DFS - profondeur d’abord | Pile ou récursion | On avance aussi loin que possible avant de revenir en arrière. |
| BFS - largeur d’abord | File FIFO | On visite les sommets par distance croissante en nombre d’arêtes. |

Un parcours doit mémoriser les sommets déjà visités pour éviter les boucles et les visites répétées. Pour chercher un chemin, on peut conserver le prédécesseur de chaque sommet découvert, puis reconstruire le chemin en remontant depuis la destination.

### 3.5. Plus court chemin et Dijkstra

> REPÈRE DE PROGRAMME  La modélisation par graphes et les chaînes sont au programme de Maths expertes. L’algorithme de Dijkstra est présenté ici comme méthode classique d’approfondissement sur les graphes pondérés ; le programme officiel de Maths expertes énumère surtout les notions de base et les matrices. En NSI, la recherche de chemins et les parcours de graphes sont explicitement travaillés.

Dijkstra cherche un plus court chemin depuis un sommet de départ dans un graphe pondéré dont les poids sont positifs ou nuls. À chaque étape, on fixe le sommet non traité dont la distance provisoire est la plus petite, puis on met à jour les distances de ses voisins.

1. Initialiser la distance du départ à 0 et celles des autres sommets à +∞. Le prédécesseur est inconnu.

1. Choisir le sommet non traité ayant la plus petite distance provisoire.

1. Pour chaque voisin, tester si passer par ce sommet donne une distance plus courte ; si oui, mettre à jour la distance et le prédécesseur.

1. Marquer le sommet comme traité. Recommencer jusqu’à traiter la destination ou tous les sommets accessibles.

#### Exemple corrigé - plus court chemin

Arêtes pondérées : S-A = 4 ; S-B = 1 ; B-A = 2 ; B-C = 5 ; A-C = 1.

Départ S : d(S)=0 ; d(A)=4 ; d(B)=1 ; d(C)=∞.

On fixe B (distance 1). Mise à jour : d(A)=min(4,1+2)=3 ; d(C)=min(∞,1+5)=6.

On fixe A (distance 3). Mise à jour : d(C)=min(6,3+1)=4.

On fixe C : la distance minimale de S à C est 4, avec le chemin S-B-A-C.

> RÉSULTAT  Le plus court chemin vaut 4, et non 6 ou 5.

### 3.6. Coloration et nombre chromatique

> COMPLÉMENT DEMANDÉ  La coloration est un approfondissement utile, mais elle n’est pas explicitement détaillée dans la liste des contenus du programme officiel de Maths expertes cité ici. Vérifie les exigences de ton professeur.

Colorier un graphe consiste à attribuer une couleur à chaque sommet de sorte que deux sommets adjacents n’aient jamais la même couleur. Le nombre chromatique χ(G) est le plus petit nombre de couleurs nécessaires.

- Un graphe complet Kₙ nécessite n couleurs : χ(Kₙ) = n.

- Un graphe biparti peut être colorié avec deux couleurs ; un graphe sans arête peut utiliser une seule couleur s’il possède au moins un sommet.

- La méthode gloutonne consiste à traiter les sommets dans un ordre choisi et à donner à chacun la première couleur disponible. Elle fournit une coloration, mais pas forcément optimale.

- Pour prouver qu’il faut au moins k couleurs, on peut exhiber un sous-graphe complet Kₖ. Pour prouver qu’il en faut au plus k, on construit explicitement une coloration à k couleurs.

### 3.7. Pièges et checklist

- Ne pas confondre un graphe orienté avec un graphe non orienté.

- Dans un graphe orienté, i vers j n’implique pas j vers i.

- Une chaîne de longueur n contient n arêtes et n+1 occurrences de sommets si les répétitions sont comptées.

- La puissance Mⁿ compte les marches de longueur n, pas seulement les chemins sans répétition.

- Un parcours DFS ou BFS doit utiliser un ensemble/liste de sommets visités.

- Dijkstra ne convient pas avec des poids négatifs.

- Une coloration gloutonne ne prouve pas forcément que le nombre de couleurs utilisé est minimal.

- ☐ Identifier sommets, arêtes, arcs, degrés et connexité.

- ☐ Construire une liste de successeurs et une matrice d’adjacence.

- ☐ Interpréter une puissance de matrice d’adjacence.

- ☐ Effectuer un parcours DFS ou BFS et reconstruire un chemin.

- ☐ Justifier une coloration et un nombre minimal de couleurs.

---

## Annexe — Synthèse des réflexes en contrôle

### Maths expertes

| Type de question | Réflexe |
| --- | --- |
| Calculer un quotient complexe | Multiplier en haut et en bas par le conjugué du dénominateur. |
| Calculer une puissance simple | Développer puis réduire en utilisant i² = −1 et la périodicité des puissances de i. |
| Trouver un argument | Calculer le module, identifier le quadrant, vérifier sinus et cosinus. |
| Résoudre une équation avec z et z̄ | Poser z = x + iy, puis identifier réel et imaginaire. |
| Multiplier deux matrices | Vérifier les dimensions, puis ligne × colonne. |
| Compter des chaînes dans un graphe | Construire la matrice d’adjacence M et utiliser Mⁿ. |

### Plan de révision conseillé

1. Relire les définitions et les formules du chapitre sans chercher à tout apprendre mot pour mot.

2. Refaire les exemples conservés sans regarder les étapes.

3. S’entraîner à expliquer à voix haute les méthodes : pourquoi choisir cette forme, cette matrice ou cette structure ?

4. Pour la NSI, tracer manuellement les appels récursifs et l’état des piles/files avant d’écrire du code.

5. Terminer par des exercices mélangés, puis noter les erreurs récurrentes et les revoir.

### Sources officielles

Mathématiques expertes — Programme officiel : Bulletin officiel spécial n° 8 du 25 juillet 2019. https://www.education.gouv.fr/bo/19/Special8/MENE1921264A.htm  |  Document d’accompagnement du programme : https://www.education.gouv.fr/sites/default/files/document/Math%C3%A9matiques%20expertes-236082.pdf

> DERNIER RAPPEL  La fiche couvre les thèmes demandés mais ne remplace pas les exercices de ton professeur : les conventions de notation, la représentation d’un arbre et le niveau de détail attendu peuvent être spécifiques à ta classe.