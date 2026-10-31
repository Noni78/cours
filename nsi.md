---
title: Numérique et sciences informatiques (NSI)
permalink: /nsi.html
---

# Numérique et sciences informatiques (NSI)

*Fiche de révision — Terminale*

[← Retour au sommaire des cours](index.html) · Pour conserver une copie PDF, utiliser la fonction **Imprimer** du navigateur.

## Sommaire
- [4. Réseaux](#4-reseaux)
  - [4.1. Architecture d’un réseau](#41-architecture-dun-reseau)
  - [4.2. Adresse MAC, adresse IP et IPv4](#42-adresse-mac-adresse-ip-et-ipv4)
  - [4.3. Routage et rôle du routeur](#43-routage-et-role-du-routeur)
  - [4.4. Protocoles de routage : RIP et OSPF](#44-protocoles-de-routage--rip-et-ospf)
  - [4.5. TCP, UDP, IP, DNS et HTTP](#45-tcp-udp-ip-dns-et-http)
  - [4.6. Client-serveur : trajet d’une requête Web](#46-client-serveur--trajet-dune-requete-web)
  - [4.7. Sécurisation : chiffrement symétrique et asymétrique](#47-securisation--chiffrement-symetrique-et-asymetrique)
  - [4.8. Pièges et checklist](#48-pieges-et-checklist)
- [5. Programmation orientée objet (POO)](#5-programmation-orientee-objet-poo)
  - [5.1. Classe, objet, attribut, méthode](#51-classe-objet-attribut-methode)
  - [5.2. Définir une classe et utiliser self](#52-definir-une-classe-et-utiliser-self)
  - [5.3. Instanciation, lecture et modification](#53-instanciation-lecture-et-modification)
  - [5.4. Méthodes : paramètres, retour et effet de bord](#54-methodes--parametres-retour-et-effet-de-bord)
  - [5.5. Classes et structures de données](#55-classes-et-structures-de-donnees)
  - [5.6. Héritage : complément si vu en cours](#56-heritage--complement-si-vu-en-cours)
  - [5.7. Erreurs fréquentes et checklist](#57-erreurs-frequentes-et-checklist)
- [6. Récursivité](#6-recursivite)
  - [6.1. Principe](#61-principe)
  - [6.2. Exemple : factorielle](#62-exemple--factorielle)
  - [6.3. Pile d’appels](#63-pile-dappels)
  - [6.4. Écrire une fonction récursive : méthode](#64-ecrire-une-fonction-recursive--methode)
  - [6.5. Récursivité sur une structure](#65-recursivite-sur-une-structure)
  - [6.6. Récursif ou itératif ?](#66-recursif-ou-iteratif-)
  - [6.7. Coût et complexité](#67-cout-et-complexite)
  - [6.8. Checklist](#68-checklist)
- [7. Arbres](#7-arbres)
  - [7.1. Vocabulaire](#71-vocabulaire)
  - [7.2. Représentation par triplet (gauche, valeur, droit)](#72-representation-par-triplet-gauche-valeur-droit)
  - [7.3. Taille, hauteur et profondeur](#73-taille-hauteur-et-profondeur)
  - [7.4. Parcours en profondeur](#74-parcours-en-profondeur)
  - [7.5. Parcours en largeur](#75-parcours-en-largeur)
  - [7.6. Arbre binaire de recherche (ABR)](#76-arbre-binaire-de-recherche-abr)
  - [7.7. Coût de recherche dans un ABR](#77-cout-de-recherche-dans-un-abr)
  - [7.8. Pièges et checklist](#78-pieges-et-checklist)
- [8. Piles et files](#8-piles-et-files)
  - [8.1. Deux structures linéaires](#81-deux-structures-lineaires)
  - [8.2. Opérations d’une pile](#82-operations-dune-pile)
  - [8.3. Opérations d’une file](#83-operations-dune-file)
  - [8.4. Choisir la bonne structure](#84-choisir-la-bonne-structure)
  - [8.5. Implémenter une file efficacement en Python](#85-implementer-une-file-efficacement-en-python)
  - [8.6. Interface et implémentation](#86-interface-et-implementation)
  - [8.7. Pièges et checklist](#87-pieges-et-checklist)
- [Annexe A - Parcours de graphes en NSI](#annexe-a---parcours-de-graphes-en-nsi)
  - [A.1. Liste de successeurs](#a1-liste-de-successeurs)
  - [A.2. Parcours en profondeur (DFS)](#a2-parcours-en-profondeur-dfs)
  - [A.3. Parcours en largeur (BFS)](#a3-parcours-en-largeur-bfs)
  - [A.4. Reconstruire un chemin](#a4-reconstruire-un-chemin)
- [Annexe — Synthèse des réflexes en contrôle](#annexe--synthese-des-reflexes-en-controle)
  - [NSI](#nsi)
  - [Plan de révision conseillé](#plan-de-revision-conseille)
  - [Sources officielles](#sources-officielles)

Les chapitres NSI demandent de savoir expliquer un mécanisme, choisir une structure adaptée et lire ou écrire des programmes Python. Les exemples de code ci-dessous sont volontairement courts et peuvent être repris dans un éditeur Python.

## 4. Réseaux

### 4.1. Architecture d’un réseau

Un réseau informatique relie des équipements afin qu’ils échangent des données. Un réseau local (LAN) relie des appareils dans une zone limitée ; Internet est un réseau mondial de réseaux interconnectés. Un hôte peut être un ordinateur, un téléphone, un serveur ou un objet connecté.

| Équipement | Rôle |
| --- | --- |
| Carte réseau | Interface qui relie un appareil au réseau, par câble ou radio. |
| Commutateur (switch) | Relie plusieurs équipements d’un réseau local et transmet les trames vers le bon port. |
| Routeur | Relie des réseaux différents et transmet les paquets IP vers le prochain routeur ou la destination. |
| Point d’accès Wi-Fi | Fournit un accès radio au réseau local. |
| Serveur | Fournit un service : page Web, fichiers, résolution de noms, etc. |
| Client | Demande un service à un serveur. |

### 4.2. Adresse MAC, adresse IP et IPv4

L’adresse MAC identifie une interface réseau au niveau du réseau local (couche liaison). Une adresse IP identifie une interface de façon logique et permet le routage entre réseaux. Elles n’ont donc pas le même rôle.

| Élément | À connaître |
| --- | --- |
| Adresse MAC | Généralement 48 bits, écrite en hexadécimal (ex. 3C:52:82:…); utilisée sur le lien local. |
| IPv4 | 32 bits, souvent écrits en quatre octets décimaux (ex. 192.168.1.34). |
| Masque / préfixe | Indique quelle partie de l’adresse représente le réseau (ex. /24 = 24 bits réseau). |
| Adresse réseau | Adresse obtenue en conservant les bits réseau et en mettant les bits hôte à 0. |
| Adresse de diffusion | En IPv4 classique, bits hôte tous à 1 ; utilisée pour joindre tous les hôtes du sous-réseau. |
| Passerelle par défaut | Routeur vers lequel l’hôte envoie les paquets destinés à d’autres réseaux. |

#### Exemple corrigé - sous-réseau /24

Adresse : 192.168.1.34/24. Le préfixe /24 signifie que les 24 premiers bits identifient le réseau.

Masque : 255.255.255.0. Adresse réseau : 192.168.1.0.

Adresse de diffusion : 192.168.1.255. Les adresses d’hôtes utilisables sont classiquement de 192.168.1.1 à 192.168.1.254.

> RÉSULTAT  Le réseau est 192.168.1.0/24. Il contient 256 adresses au total, dont 254 adresses hôtes utilisables dans le cas classique.

> Taille d’un sous-réseau : Nombre total d’adresses IPv4 d’un /p = 2^(32−p)

Pour un /26, il reste 6 bits pour les hôtes : 2⁶ = 64 adresses au total, habituellement 62 utilisables. Les cas particuliers (/31, /32, IPv6, réseaux spéciaux) ne suivent pas tous la règle simplifiée des deux adresses réservées.

> COMPLÉMENT DE CULTURE RÉSEAU  DNS, HTTP, ports TCP/UDP, ARP et NAT sont utiles pour comprendre Internet. Le programme NSI de Terminale met explicitement l’accent, dans cette partie, sur les protocoles de routage et la sécurisation des communications. DNS et HTTP ne sont pas les points centraux de cet item.

### 4.3. Routage et rôle du routeur

Les données sont découpées en paquets. Un routeur examine l’adresse IP de destination et consulte sa table de routage pour décider vers quel prochain saut transmettre le paquet. Il ne choisit pas nécessairement le trajet complet : chaque routeur prend une décision locale. Des paquets d’une même communication peuvent éventuellement emprunter des chemins différents.

| Destination | Prochain saut | Interface | Interprétation |
| --- | --- | --- | --- |
| 192.168.1.0/24 | Directement connecté | LAN | Le réseau est local. |
| 10.0.0.0/8 | 10.1.1.1 | WAN1 | Envoyer au routeur 10.1.1.1. |
| 0.0.0.0/0 | 192.168.1.254 | LAN | Route par défaut si aucune route plus précise ne correspond. |

La règle générale est de choisir la route correspondant au préfixe le plus précis (plus long) parmi celles qui correspondent à l’adresse de destination. Pour des exercices de classe, la table de routage fournie peut être simplifiée.

### 4.4. Protocoles de routage : RIP et OSPF

| Protocole | Critère principal | Lecture d’une table |
| --- | --- | --- |
| RIP | Nombre de sauts (routeurs traversés). | Choisir la route ayant le plus petit nombre de sauts ; la métrique est limitée. |
| OSPF | Coût associé aux liens ; recherche d’un chemin de coût total minimal. | Additionner les coûts des liens et retenir le trajet de coût minimal. |

Le programme demande de savoir identifier, à partir d’une table de routage donnée et du protocole utilisé, la route empruntée par un paquet. Le lien est fait avec la recherche de chemin sur un graphe : les routeurs sont des sommets, les liaisons sont des arêtes pondérées.

### 4.5. TCP, UDP, IP, DNS et HTTP

| Protocole | Fonction essentielle | À retenir |
| --- | --- | --- |
| IP | Adressage logique et acheminement des paquets. | Best effort : IP ne garantit pas à lui seul la livraison. |
| TCP | Transport fiable et ordonné. | Accusés de réception, retransmissions, contrôle du flux. |
| UDP | Transport léger sans garantie de livraison ni d’ordre. | Utile quand la rapidité ou la simplicité prime. |
| DNS | Associe un nom de domaine à une adresse IP. | Résout par exemple un nom de site en adresse IP. |
| HTTP | Protocole de requête/réponse pour le Web. | Le client demande une ressource, le serveur répond. |
| HTTPS | HTTP protégé par TLS. | Confidentialité et intégrité du canal, authentification du serveur. |

Une adresse IP permet d’acheminer les paquets jusqu’à un hôte ; un port TCP ou UDP identifie ensuite un service ou une application sur cet hôte. Exemples courants : port 80 pour HTTP, 443 pour HTTPS et 53 pour DNS (les détails des ports sont un complément de culture).

### 4.6. Client-serveur : trajet d’une requête Web

1. L’utilisateur saisit un nom de domaine dans le navigateur.

2. Le navigateur obtient l’adresse IP du serveur, généralement grâce au DNS.

3. Il ouvre une communication vers le serveur, souvent avec TCP et une protection TLS pour HTTPS.

4. La requête HTTP est encapsulée dans des segments/paquets/trames et traverse le réseau local puis plusieurs routeurs.

5. Le serveur traite la requête et renvoie une réponse ; le navigateur interprète le contenu reçu.

> À RETENIR  DNS trouve une adresse IP ; IP achemine les paquets ; TCP fiabilise le transport ; HTTP décrit les requêtes et réponses Web ; HTTPS protège la communication HTTP grâce à TLS.

### 4.7. Sécurisation : chiffrement symétrique et asymétrique

Le chiffrement transforme un message lisible (texte en clair) en message illisible (texte chiffré) à l’aide d’une clé. Le déchiffrement retrouve le message initial avec la clé appropriée.

| Type | Clés | Avantage / limite |
| --- | --- | --- |
| Symétrique | Une même clé secrète sert à chiffrer et déchiffrer. | Rapide, mais il faut transmettre la clé secrètement. |
| Asymétrique | Une clé publique et une clé privée liées mathématiquement. | Permet un échange initial sans partager la clé privée, mais opérations plus coûteuses. |

Dans le principe d’HTTPS, le serveur présente un certificat qui permet au client de vérifier son identité et d’obtenir sa clé publique. Un échange asymétrique permet d’établir un secret de session ; les données sont ensuite chiffrées avec une clé symétrique, plus efficace pour les échanges volumineux. Il ne faut jamais confondre « clé publique » et « clé secrète » : la clé privée ne doit pas être divulguée.

> PROGRAMME  Le programme demande de décrire le chiffrement symétrique et asymétrique, puis l’échange d’une clé symétrique à l’aide d’un protocole asymétrique pour sécuriser HTTPS. Les détails techniques des versions TLS modernes ne sont pas à développer au-delà de ce qui a été étudié en classe.

### 4.8. Pièges et checklist

- Une adresse MAC et une adresse IP ne jouent pas le même rôle.

- Un masque /24 signifie 24 bits de réseau, et non 24 adresses.

- Un routeur transmet des paquets entre réseaux ; un switch relie des appareils dans un réseau local.

- RIP compare le nombre de sauts ; OSPF compare un coût de route.

- IP ne garantit pas la livraison ; TCP peut compenser certaines pertes grâce aux accusés de réception et retransmissions.

- UDP ne garantit pas que les paquets arrivent ni qu’ils arrivent dans l’ordre.

- Le chiffrement symétrique utilise une clé partagée ; l’asymétrique utilise une paire publique/privée.

- ☐ Lire une adresse IPv4 et un préfixe /p.

- ☐ Identifier réseau, diffusion et plage d’hôtes dans un exemple classique.

- ☐ Lire une table de routage et comparer RIP/OSPF.

- ☐ Expliquer le rôle de l’adresse IP et du routeur dans l’acheminement des paquets.

- ☐ Expliquer le principe hybride utilisé pour sécuriser HTTPS.

## 5. Programmation orientée objet (POO)

### 5.1. Classe, objet, attribut, méthode

La programmation orientée objet organise le programme autour d’objets. Une classe est un modèle qui décrit des données et des actions. Un objet est une instance concrète de cette classe.

| Notion | Définition | Exemple |
| --- | --- | --- |
| Classe | Modèle commun à une famille d’objets. | La classe Compte. |
| Objet / instance | Exemplaire créé à partir d’une classe. | mon_compte. |
| Attribut | Donnée stockée dans l’objet. | solde, titulaire. |
| Méthode | Fonction définie dans la classe et appelée sur un objet. | deposer, retirer. |
| Constructeur | Méthode spéciale qui initialise un nouvel objet. | __init__. |

### 5.2. Définir une classe et utiliser self

```python\nclass Compte:<br>    def __init__(self, titulaire, solde_initial=0):<br>        self.titulaire = titulaire<br>        self.solde = solde_initial<br> <br>    def deposer(self, montant):<br>        if montant > 0:<br>            self.solde += montant<br> <br>    def retirer(self, montant):<br>        if 0 < montant <= self.solde:<br>            self.solde -= montant<br> <br>    def afficher_solde(self):<br>        return self.solde<br> <br>mon_compte = Compte("Nolan", 50)<br>mon_compte.deposer(20)<br>mon_compte.retirer(15)<br>print(mon_compte.afficher_solde())  # 55\n```

Dans __init__, self désigne l’objet en cours de construction. Chaque attribut créé avec self.nom appartient à cet objet. Lorsqu’on écrit mon_compte.deposer(20), Python transmet automatiquement l’objet mon_compte comme premier argument self.

> Rôle de self : mon_compte.deposer(20) ≈ Compte.deposer(mon_compte, 20)

### 5.3. Instanciation, lecture et modification

> c1 = Compte("Ariane", 100)  # création d'un objet<br>c2 = Compte("Bilal", 40)    # autre objet indépendant<br> <br>print(c1.titulaire)         # Ariane<br>print(c2.solde)              # 40<br>c1.solde = 120               # modification directe<br>c2.deposer(10)               # appel d'une méthode

Les attributs de c1 et c2 sont distincts : modifier c1.solde ne modifie pas c2.solde. Les méthodes définissent les opérations que les objets savent effectuer.

### 5.4. Méthodes : paramètres, retour et effet de bord

- Une méthode peut recevoir des paramètres supplémentaires après self.

- Une méthode qui utilise return renvoie une valeur ; une méthode sans return explicite renvoie None.

- Une méthode peut modifier l’état de l’objet : c’est un effet de bord sur ses attributs.

- Il faut distinguer une méthode appelée avec des parenthèses (objet.methode()) et l’accès à un attribut (objet.attribut).

### 5.5. Classes et structures de données

La POO peut servir à implémenter des structures comme une pile, une file, un arbre ou un graphe. L’interface décrit les opérations accessibles ; l’implémentation explique comment les données sont effectivement stockées.

> PROGRAMME OFFICIEL  Le vocabulaire des classes, objets, attributs et méthodes ainsi que l’écriture d’une classe et l’accès à ses attributs/méthodes sont explicitement mentionnés. Le texte officiel précise que l’héritage et le polymorphisme ne sont pas abordés dans ce cadre.

### 5.6. Héritage : complément si vu en cours

L’héritage permet à une classe fille de reprendre les attributs et méthodes d’une classe mère, puis de les compléter ou redéfinir. Cette notion est utile en programmation générale, mais elle est indiquée ici comme complément et non comme attendu explicite du programme NSI de Terminale cité.

### 5.7. Erreurs fréquentes et checklist

- Oublier self comme premier paramètre d’une méthode.

- Écrire attribut = valeur au lieu de self.attribut = valeur dans le constructeur.

- Confondre classe (modèle) et objet (instance).

- Oublier les parenthèses lors de l’appel d’une méthode.

- Supposer que deux objets partagent automatiquement leurs attributs.

- ☐ Expliquer classe, objet, attribut et méthode.

- ☐ Écrire un constructeur __init__ avec self.

- ☐ Créer deux instances et montrer que leurs états sont séparés.

- ☐ Lire le résultat d’un appel de méthode et suivre les modifications d’attributs.

## 6. Récursivité

### 6.1. Principe

Une fonction est récursive lorsqu’elle s’appelle elle-même pour résoudre un problème plus petit. Une récursivité correcte contient toujours un ou plusieurs cas de base (arrêt) et un cas récursif qui rapproche du cas de base.

> Structure mentale : Problème = cas simple (arrêt) OU réduction vers un problème plus petit

| Élément | Rôle | Question à se poser |
| --- | --- | --- |
| Cas de base | Donne directement une réponse sans nouvel appel. | Quand puis-je répondre immédiatement ? |
| Cas récursif | Réduit le problème et rappelle la fonction. | Le sous-problème est-il vraiment plus simple ? |
| Mesure de progression | Prouve qu’on se rapproche de l’arrêt. | Quel entier diminue à chaque appel ? |

### 6.2. Exemple : factorielle

```python\ndef factorielle(n):<br>    if n == 0:              # cas de base<br>        return 1<br>    return n * factorielle(n - 1)<br> <br>print(factorielle(4))       # 24\n```

Définition mathématique : 0! = 1 et n! = n × (n−1)! pour n ≥ 1. Pour n = 4, les appels descendent vers le cas de base, puis les retours se calculent dans l’ordre inverse.

| Appel | Action au retour |
| --- | --- |
| factorielle(4) | 4 × factorielle(3) |
| factorielle(3) | 3 × factorielle(2) |
| factorielle(2) | 2 × factorielle(1) |
| factorielle(1) | 1 × factorielle(0) |
| factorielle(0) | renvoie 1 |
| Remontée | 1, puis 2, puis 6, puis 24 |

### 6.3. Pile d’appels

Chaque appel de fonction crée un cadre d’exécution qui mémorise ses paramètres, ses variables locales et l’endroit où reprendre après le retour. Ces cadres sont empilés dans la pile d’appels. Le dernier appel effectué est le premier à se terminer : comportement LIFO.

- La descente correspond aux appels récursifs successifs.

- La remontée correspond au retour des fonctions et à la combinaison des résultats.

- Une récursion trop profonde peut provoquer une erreur de profondeur maximale (RecursionError en Python).

### 6.4. Écrire une fonction récursive : méthode

1. Définir précisément ce que la fonction renvoie pour une entrée donnée.

2. Trouver le cas le plus simple et écrire le cas de base.

3. Exprimer le cas général en utilisant un appel sur une entrée plus petite.

4. Vérifier que chaque appel se rapproche du cas de base.

5. Tester le cas de base, le plus petit cas non trivial et un cas ordinaire.

### 6.5. Récursivité sur une structure

Les arbres sont naturellement récursifs : un arbre est soit vide, soit constitué d’une racine, d’un sous-arbre gauche et d’un sous-arbre droit. On peut donc écrire taille, hauteur, recherche et parcours avec des appels récursifs sur les sous-arbres.

```python\ndef taille(arbre):<br>    if arbre is None:<br>        return 0<br>    gauche, valeur, droit = arbre<br>    return 1 + taille(gauche) + taille(droit)\n```

### 6.6. Récursif ou itératif ?

| Approche | Avantages | Limites |
| --- | --- | --- |
| Récursive | Code souvent proche de la définition mathématique ; naturelle sur les arbres. | Pile d’appels et risque de profondeur excessive. |
| Itérative | Contrôle explicite de la mémoire et des répétitions ; souvent adaptée aux boucles. | Peut demander davantage de variables et de logique de gestion. |

Une fonction factorielle itérative peut utiliser une boucle for. Les deux versions donnent le même résultat, mais elles n’utilisent pas la même organisation du calcul.

```python\ndef factorielle_iterative(n):<br>    resultat = 1<br>    for k in range(2, n + 1):<br>        resultat *= k<br>    return resultat\n```

### 6.7. Coût et complexité

| Algorithme | Nombre d’opérations / coût indicatif | Mémoire liée aux appels |
| --- | --- | --- |
| Factorielle récursive | n appels : O(n). | O(n) cadres. |
| Somme récursive | n appels : O(n). | O(n) cadres. |
| Recherche dichotomique récursive | O(log₂ n) si le tableau est trié. | O(log₂ n) cadres. |
| Fibonacci naïf F(n)=F(n−1)+F(n−2) | Nombre d’appels exponentiel, environ O(2ⁿ). | Profondeur O(n). |

> PIÈGE MAJEUR  Un appel récursif ne doit pas répéter tout le problème d’origine. Il doit réduire la taille du problème. Si aucune condition d’arrêt n’est atteinte, la fonction s’appelle indéfiniment jusqu’à la limite de récursion.

### 6.8. Checklist

- ☐ Identifier les cas de base et les cas récursifs.

- ☐ Tracer la descente puis la remontée d’une fonction.

- ☐ Expliquer le contenu de la pile d’appels.

- ☐ Prouver que les appels se terminent.

- ☐ Comparer le coût en temps et en mémoire à une version itérative.

## 7. Arbres

### 7.1. Vocabulaire

Un arbre est une structure hiérarchique composée de nœuds reliés par une relation parent-enfant. Il possède une racine. Chaque nœud peut avoir zéro, un ou plusieurs enfants. Un arbre binaire possède au plus deux enfants par nœud : le sous-arbre gauche et le sous-arbre droit.

| Terme | Définition |
| --- | --- |
| Racine | Nœud sans parent. |
| Nœud | Élément de l’arbre. |
| Parent / enfant | Relation entre un nœud et ses descendants immédiats. |
| Feuille | Nœud sans enfant. |
| Sous-arbre | Arbre formé par un nœud et tous ses descendants. |
| Profondeur d’un nœud | Nombre d’arêtes entre la racine et ce nœud. |
| Hauteur d’un arbre | Plus grande profondeur d’une feuille (convention en nombre d’arêtes). |
| Taille | Nombre total de nœuds. |

> CONVENTION DE HAUTEUR  Ici, la hauteur d’un arbre vide vaut −1 et celle d’une feuille vaut 0. Certains cours comptent les niveaux : arbre vide 0, feuille 1. Les résultats sont équivalents à un décalage de 1 ; utiliser la convention de l’énoncé.

### 7.2. Représentation par triplet (gauche, valeur, droit)

Un arbre binaire peut être représenté par un triplet (gauche, valeur, droit). Chaque sous-arbre est lui-même représenté de la même façon. L’arbre vide est représenté par None.

> arbre = (<br>    (None, "D", None),   # sous-arbre gauche : D<br>    "B",                 # racine : B<br>    ((None, "E", None),  # sous-arbre droit : C<br>     "C",<br>     (None, "F", None))<br>)

La racine vaut B. Son sous-arbre gauche est la feuille D. Son sous-arbre droit a pour racine C, avec les feuilles E et F. Pour décomposer un arbre non vide : gauche, valeur, droit = arbre.

### 7.3. Taille, hauteur et profondeur

> Taille récursive : taille(arbre) = 0 si arbre est vide ; sinon 1 + taille(gauche) + taille(droit)

> Hauteur récursive : hauteur(arbre) = −1 si arbre vide ; sinon 1 + max(hauteur(gauche), hauteur(droit))

> Arbre binaire parfait : Pour une hauteur h : taille maximale = 2^(h+1) − 1

Un arbre de n nœuds a une hauteur comprise entre ⌈log₂(n+1)⌉−1 (hauteur minimale possible) et n−1 (arbre totalement dégénéré en chaîne), avec notre convention en nombre d’arêtes. La hauteur mesure le nombre maximal d’étapes depuis la racine jusqu’à une feuille.

### 7.4. Parcours en profondeur

Les parcours en profondeur visitent les nœuds selon l’ordre choisi entre racine, sous-arbre gauche et sous-arbre droit.

| Parcours | Ordre | Mémo |
| --- | --- | --- |
| Préfixe | Racine, Gauche, Droite | La racine est visitée en premier. |
| Infixe | Gauche, Racine, Droite | La racine est visitée entre gauche et droite. |
| Postfixe / suffixe | Gauche, Droite, Racine | La racine est visitée en dernier. |

```python\ndef prefixe(a):<br>    if a is not None:<br>        g, v, d = a<br>        print(v)<br>        prefixe(g)<br>        prefixe(d)<br> <br>def infixe(a):<br>    if a is not None:<br>        g, v, d = a<br>        infixe(g)<br>        print(v)<br>        infixe(d)<br> <br>def postfixe(a):<br>    if a is not None:<br>        g, v, d = a<br>        postfixe(g)<br>        postfixe(d)<br>        print(v)\n```

### 7.5. Parcours en largeur

Le parcours en largeur visite les nœuds niveau par niveau, de gauche à droite. Il utilise une file FIFO : on enfile la racine, puis on répète : défiler un nœud, le visiter, enfiler ses enfants s’ils existent.

```python\nfrom collections import deque<br> <br>def largeur(arbre):<br>    if arbre is None:<br>        return []<br>    file = deque([arbre])<br>    resultat = []<br>    while file:<br>        g, v, d = file.popleft()<br>        resultat.append(v)<br>        if g is not None:<br>            file.append(g)<br>        if d is not None:<br>            file.append(d)<br>    return resultat\n```

Pour l’exemple précédent, le parcours en largeur donne : B, D, C, E, F.

### 7.6. Arbre binaire de recherche (ABR)

Un arbre binaire de recherche est un arbre binaire ordonné : pour chaque nœud de valeur x, toutes les valeurs du sous-arbre gauche sont inférieures à x et toutes celles du sous-arbre droit sont supérieures à x (on adopte ici une convention sans doublons). Cette propriété permet de rechercher et d’insérer efficacement une valeur.

```python\ndef rechercher(a, cle):<br>    if a is None:<br>        return False<br>    g, v, d = a<br>    if cle == v:<br>        return True<br>    if cle < v:<br>        return rechercher(g, cle)<br>    return rechercher(d, cle)\n```

Pour insérer une clé : descendre à gauche si elle est plus petite, à droite si elle est plus grande ; quand on rencontre un sous-arbre vide, y créer une feuille. L’algorithme suit le même chemin que la recherche.

```python\ndef inserer(a, cle):<br>    if a is None:<br>        return (None, cle, None)<br>    g, v, d = a<br>    if cle < v:<br>        return (inserer(g, cle), v, d)<br>    if cle > v:<br>        return (g, v, inserer(d, cle))<br>    return a  # doublon : on ne modifie pas l'arbre\n```

### 7.7. Coût de recherche dans un ABR

La recherche visite au plus un nœud par niveau : son coût est O(h), où h est la hauteur de l’arbre. Dans un ABR équilibré, h est de l’ordre de log₂(n), donc la recherche est logarithmique. Dans un arbre dégénéré en liste, h peut être n−1 et la recherche devient linéaire O(n).

| Structure | Hauteur indicative | Coût recherche |
| --- | --- | --- |
| ABR équilibré | O(log n) | O(log n) |
| ABR dégénéré | O(n) | O(n) |

> ASTUCE DE CONTRÔLE  Dans un ABR, le parcours infixe restitue les clés dans l’ordre croissant. Cette propriété est très utile pour vérifier un arbre ou produire une liste triée.

### 7.8. Pièges et checklist

- Dans un triplet (gauche, valeur, droit), la valeur est au milieu, et non en première position.

- Toujours tester le cas arbre is None avant de décomposer le triplet.

- Ne pas confondre profondeur d’un nœud et hauteur de l’arbre.

- Le parcours en largeur utilise une file ; le parcours en profondeur utilise une pile ou la récursivité.

- Un arbre binaire n’est pas nécessairement un arbre binaire de recherche.

- La recherche dans un ABR est O(h), pas toujours O(log n) : cela suppose un arbre équilibré.

- ☐ Décomposer un arbre représenté par des triplets.

- ☐ Calculer taille, hauteur et profondeur.

- ☐ Écrire les parcours préfixe, infixe, postfixe et largeur.

- ☐ Effectuer une recherche et une insertion dans un ABR.

- ☐ Expliquer le coût d’une recherche selon la hauteur.

## 8. Piles et files

### 8.1. Deux structures linéaires

Une pile et une file sont des structures linéaires abstraites. La différence fondamentale concerne l’ordre dans lequel les éléments sortent.

| Structure | Principe | Analogie | Insertion / retrait |
| --- | --- | --- | --- |
| Pile (stack) | LIFO : Last In, First Out. | Pile d’assiettes. | Empiler et dépiler au même sommet. |
| File (queue) | FIFO : First In, First Out. | File d’attente. | Enfiler à l’arrière, défiler à l’avant. |

### 8.2. Opérations d’une pile

| Opération | Effet |
| --- | --- |
| empiler(x) / push(x) | Ajoute x au sommet. |
| depiler() / pop() | Retire et renvoie l’élément au sommet. |
| sommet() / peek() | Consulte le sommet sans le retirer. |
| est_vide() | Indique si la pile ne contient aucun élément. |

> pile = []<br>pile.append("A")  # empiler A<br>pile.append("B")  # empiler B<br>pile.append("C")  # empiler C<br>sommet = pile[-1] # consulter C<br>x = pile.pop()    # retirer C<br># pile contient maintenant ["A", "B"]

### 8.3. Opérations d’une file

| Opération | Effet |
| --- | --- |
| enfiler(x) / enqueue(x) | Ajoute x à la fin de la file. |
| defiler() / dequeue() | Retire et renvoie le premier élément. |
| premier() / front() | Consulte le premier sans le retirer. |
| est_vide() | Indique si la file est vide. |

```python\nfrom collections import deque<br> <br>file = deque()<br>file.append("A")       # enfiler A<br>file.append("B")       # enfiler B<br>file.append("C")       # enfiler C<br>premier = file[0]      # consulter A<br>x = file.popleft()     # défiler A<br># file contient maintenant deque(["B", "C"])\n```

### 8.4. Choisir la bonne structure

| Situation | Structure adaptée | Pourquoi ? |
| --- | --- | --- |
| Annuler la dernière action (undo) | Pile | La dernière action effectuée est la première annulée. |
| Gestion de tâches dans leur ordre d’arrivée | File | La première tâche arrivée est traitée en premier. |
| Parcours en profondeur d’un graphe/arbre | Pile ou récursivité | On explore un chemin avant de revenir. |
| Parcours en largeur | File | On visite par niveaux / distance croissante. |
| Historique de navigation | Pile(s) | On revient vers la page précédente. |

### 8.5. Implémenter une file efficacement en Python

Une liste Python peut jouer le rôle d’une pile avec append et pop, qui agissent en fin de liste. Pour une file, utiliser collections.deque : popleft retire efficacement le premier élément. Utiliser liste.pop(0) peut coûter O(n), car les éléments restants doivent être décalés.

```python\nfrom collections import deque<br> <br>class File:<br>    def __init__(self):<br>        self._donnees = deque()<br> <br>    def est_vide(self):<br>        return len(self._donnees) == 0<br> <br>    def enfiler(self, valeur):<br>        self._donnees.append(valeur)<br> <br>    def defiler(self):<br>        if self.est_vide():<br>            raise IndexError("file vide")<br>        return self._donnees.popleft()<br> <br>    def premier(self):<br>        if self.est_vide():<br>            raise IndexError("file vide")<br>        return self._donnees[0]\n```

### 8.6. Interface et implémentation

L’interface décrit les opérations qu’une structure garantit (empiler, dépiler, etc.) sans imposer comment les données sont stockées. L’implémentation est le choix technique concret : tableau, liste chaînée, deux piles, etc. Plusieurs implémentations peuvent respecter la même interface.

> POINT CLÉ DU PROGRAMME  En NSI, il faut distinguer FIFO et LIFO, choisir une structure adaptée et savoir comparer des implémentations. Le programme évoque notamment plusieurs implémentations d’une file, dont une avec un tableau et une avec deux piles.

### 8.7. Pièges et checklist

- Pile : le dernier entré sort en premier (LIFO).

- File : le premier entré sort en premier (FIFO).

- Ne pas confondre consulter et retirer : sommet/premier ne modifie pas la structure.

- Prévoir le cas de la structure vide avant un dépilement ou un défilement.

- Pour une file Python, préférer deque à une liste avec pop(0).

- ☐ Simuler plusieurs empilements/dépilements.

- ☐ Simuler plusieurs enfilements/défilements.

- ☐ Choisir entre pile et file pour un algorithme donné.

- ☐ Expliquer interface et implémentation.

- ☐ Écrire une classe simple qui encapsule une pile ou une file.

## Annexe A - Parcours de graphes en NSI

Le programme NSI demande de modéliser un graphe par une matrice d’adjacence ou une liste de successeurs, de passer d’une représentation à l’autre, puis d’effectuer des parcours en profondeur et en largeur, de détecter un cycle et de chercher un chemin.

### A.1. Liste de successeurs

> graphe = {<br>    "A": ["B", "C"],<br>    "B": ["A", "D"],<br>    "C": ["A", "D"],<br>    "D": ["B", "C"]<br>}

Ici, chaque clé est un sommet et sa valeur est la liste des sommets accessibles directement. Pour un graphe non orienté, chaque arête apparaît dans les deux listes correspondantes.

### A.2. Parcours en profondeur (DFS)

```python\ndef parcours_profondeur(graphe, depart):<br>    visites = set()<br> <br>    def visiter(sommet):<br>        if sommet in visites:<br>            return<br>        visites.add(sommet)<br>        for voisin in graphe[sommet]:<br>            visiter(voisin)<br> <br>    visiter(depart)<br>    return visites\n```

Le set visites empêche de revisiter un sommet. L’ordre précis de visite dépend de l’ordre des voisins dans les listes.

### A.3. Parcours en largeur (BFS)

```python\nfrom collections import deque<br> <br>def parcours_largeur(graphe, depart):<br>    visites = {depart}<br>    file = deque([depart])<br>    while file:<br>        sommet = file.popleft()<br>        for voisin in graphe[sommet]:<br>            if voisin not in visites:<br>                visites.add(voisin)<br>                file.append(voisin)<br>    return visites\n```

Le sommet est marqué visité au moment où il est ajouté à la file. Cela évite d’ajouter plusieurs fois le même sommet.

### A.4. Reconstruire un chemin

```python\nfrom collections import deque<br> <br>def chemin(graphe, depart, arrivee):<br>    file = deque([depart])<br>    precedent = {depart: None}<br> <br>    while file:<br>        s = file.popleft()<br>        if s == arrivee:<br>            break<br>        for v in graphe[s]:<br>            if v not in precedent:<br>                precedent[v] = s<br>                file.append(v)<br> <br>    if arrivee not in precedent:<br>        return None<br> <br>    resultat = []<br>    s = arrivee<br>    while s is not None:<br>        resultat.append(s)<br>        s = precedent[s]<br>    resultat.reverse()<br>    return resultat\n```

Avec une file, ce parcours retrouve un plus court chemin en nombre d’arêtes dans un graphe non pondéré. Dans un graphe pondéré, il faut un algorithme adapté aux poids, comme Dijkstra lorsque les poids sont non négatifs.

---

## Annexe — Synthèse des réflexes en contrôle

### NSI

| Type de question | Réflexe |
| --- | --- |
| Lire un code récursif | Identifier le cas de base, dérouler les appels, puis remonter les retours. |
| Écrire une récursion | Définir l’arrêt puis un appel sur un problème strictement plus petit. |
| Manipuler une classe | Distinguer la classe, l’instance, les attributs, les méthodes et self. |
| Choisir une structure | Pile pour LIFO ; file pour FIFO ; dictionnaire pour accès par clé ; arbre pour hiérarchie. |
| Parcourir un arbre | Préfixe = racine avant ; infixe = au milieu ; postfixe = racine après ; largeur = file. |
| Chercher dans un ABR | Comparer à la racine puis choisir gauche ou droite. |
| Parcourir un graphe | DFS = pile/récursion ; BFS = file ; toujours mémoriser les sommets visités. |
| Lire une table de routage | Appliquer la métrique indiquée : nombre de sauts RIP ou coût OSPF. |
| Expliquer HTTPS | Échange asymétrique pour établir une clé de session, puis chiffrement symétrique. |
| Débugger | Tester cas limite, type, bornes, conditions, valeurs de retour et effets de bord. |

### Plan de révision conseillé

1. Relire les définitions et les formules du chapitre sans chercher à tout apprendre mot pour mot.

2. Refaire les exemples conservés sans regarder les étapes.

3. S’entraîner à expliquer à voix haute les méthodes : pourquoi choisir cette forme, cette matrice ou cette structure ?

4. Pour la NSI, tracer manuellement les appels récursifs et l’état des piles/files avant d’écrire du code.

5. Terminer par des exercices mélangés, puis noter les erreurs récurrentes et les revoir.

### Sources officielles

NSI — Programme officiel : Bulletin officiel spécial n° 8 du 25 juillet 2019. https://www.education.gouv.fr/bo/19/Special8/MENE1921247A.htm  |  Ressources Éduscol : https://eduscol.education.gouv.fr/5823  |  Programme d’examen à compter de la session 2027 : note de service du 11 septembre 2026, https://www.education.gouv.fr/bo/2026/Special4/MENE2622643N

> DERNIER RAPPEL  La fiche couvre les thèmes demandés mais ne remplace pas les exercices de ton professeur : les conventions de notation, la représentation d’un arbre et le niveau de détail attendu peuvent être spécifiques à ta classe.