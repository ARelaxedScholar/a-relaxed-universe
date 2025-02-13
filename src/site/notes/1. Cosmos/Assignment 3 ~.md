---
{"dg-publish":true,"permalink":"/1-cosmos/assignment-3/","created":"2025-01-22T11:17:14.238-05:00","updated":"2024-11-23T23:50:31.634-05:00"}
---

```ad-info
Class: CSI3505 ~ Conceptions et Design d'Algorithmes
Name: Kouakou Jedidiah Ange-Emmanuel
Student ID: 300314061
```
# Assignment 3 ~ À Propos de la Programmation Dynamique

## a) Programmation dynamique
On a des timbres de 7,3 et 1 cent. Ainsi on sera toujours capable d'arriver à $N$ cents.

- Prendre un timbre réduit nécessairement la valeur du problème de $N$ à soit $N-1$, $N-3$ ou $N-7$.
- On peut régler le problème en utilisant une approche vorace en prenant à chaque étape la plus grosse face de timbre que l'on peut prendre. Mais en inversant la logique (avec quelques ajustements) nous obtenons cet algorithme de programmation dynamique.

```python
def number_of_stamps(N):
	stamps = [1,3,7]
	dp = [float('inf')]*(N+1)
	dp[0] = 0
	for i in range(1, N+1):
		for denomination in stamps:
			if i >= denomination:
				# we optimize based on which denomination 
				# best solves the problem at step i
				dp[i] = min(dp[i], dp[i-denomination]+1) 
	
	return dp[N] 
			
N = 12
print(f"So for {N} cents, we need {number_of_stamps(N)} stamps to match them")	
```

## b) Explanation for 17
1. Nous commençons par fixer $dp[0]=0$ après avoir initialisé le tableau de $0$ à $N+1$. Nous pourrions nous en tenir strictement à $N$, mais il est beaucoup plus intuitif d'ajouter une cellule.
2. A chaque itération, pour $i$ compris entre $1$ et $N+1$, nous vérifions si $i$ est suffisamment grand par rapport aux dénominations dont nous disposons. Sur la base de cette information, nous vérifions quelle est la solution optimale en fonction des solutions passées.

   Par exemple, pour $i=3$, le tableau serait le suivant (après l'itération dans la boucle interne):
   $$[0,1,2,1]$$
   Donc comment obtenons-nous ce résultat? Notons qu'à ce stade, nous vérifions si, compte tenu des dénominations possibles actuelles ($1,3$), il serait plus efficace de continuer à utiliser des 1 (auquel cas $dp[3]$ passerait de l'infini à $3$), puis, lorsque nous arrivons à la plus grosse dénomination, nous vérifions si le fait d'ajouter $1$ au coût obtenu $denomination$ étapes avant (donc ici $3$) donnerait un coût inférieur à celui qui a déjà été enregistré. Ici, le coût $denomination$ étapes avant nous donnerait le coût de $N=0$ qui est évidemment $0$, auquel nous ajoutons $1$ pour le timbre de taille $3$. Voilà ce que fait l'algorithme en résumé, mais pour toutes les coupures.
   3. Lorsque nous arrivons à $i=7$, avant de commencer la boucle interne, le tableau ressemble à ceci : $$[0,1,2,1,2,3,2, \infty,\dots]$$ Ainsi, lorsque nous finissons d'exécuter la boucle pour le timbre $1$, $2+1=3$ est évidemment plus petit que $\infty$, nous mettons donc $3$ dans le tableau. À ce stade, ces trois timbres constitueraient deux timbres d'une valeur de $3$ et un timbre d'une valeur de $1$. Lorsque nous exécutons la boucle pour le timbre $3$, aucune mise à jour n'est effectuée. En effet, lorsque nous regardons $dp[4]$, nous avons déjà $2$, donc en ajoutant un timbre, nous obtenons $3$ de timbres identiques à ce que nous avions obtenu avec $1$. Non seulement cela, mais c'est la même configuration, puisque nous avons toujours deux timbres 3 et un timbre 1. Ce n'est qu'à partir de la dénomination $7$ qu'il y a une mise à jour. À ce stade, comparer à $dp[0]$ et ajouter $1$, c'est repartir de zéro et régler nos dettes avec un seul timbre. C'est la meilleure solution à ce stade.
   4. L'algorithme continue à fonctionner ainsi jusqu'à ce que nous arrivions à $i=17$. A ce moment-là, avant que le tableau ne soit modifié dans la boucle, nous aurions : $$[0,1,2,1,2,3,2,1,2,3,2,3,4,3,2,3,4,\infty]$$Donc, au premier passage avec $1$, nous initialisons $dp[17]$ à $5$, ce qui est toujours possible avec $7+7+1+1+1 = 17$. Cela nous donne $5$ timbres en tout. Cela est très visible dans l'équation ci-dessus, mais les trois timbres de $1$ peuvent être remplacés par un seul timbre de $3$. En effet, lorsque la dénomination atteint $3$, nous passons à $dp[14]=7+7=14$ et ajoutons $3$ pour obtenir $17$ en utilisant $3$ timbres au total. Nous mettons à jour $dp[17]=3$. Ensuite, lorsque la dénomination passe à $7$, nous vérifions $dp[10]=3+7$, nous pouvons également ajouter $7$ ici et cela nous donne également $17$ pour des pièces de $3$. Aucune mise à jour du tableau à ce stade puisque le nombre de pièces est le même.
5. À ce stade, nous avons fini de parcourir le tableau et nous retournons $dp[N]=dp[17]$.

### c) Complexité
La complexité de cette algorithme est bien évidemment linéaire. Notre but est de trouver la complexité dans le pire cas.
À ces fins nous allons étendre le pire cas des itérations ce qui est lorsque $i >= 7$ à chaque $i$ (même ceux avant $i$ pour simplicité.)

Pour chaque $i$, nous avons trois dénominations. Pour chaque dénominations nous faisons deux comparaisons, une pour vérifier que $i$ est plus grand ou égal à la dénomination et ensuite comparer la valeur déjà enregistré dans le tableau à la valeur calculée. Cela fait en tout $6$ comparaisons par boucle.

Donc:
$$
T(n) \in O(6n)=O(n)
$$

## 2. 
### a) The Algorithm
L'algorithme utilise la logique suivante. 
On commence par définir les cas de base, pour une chaine de longueur $n$, nous avons une longeur de $0$ évidemment et pour une chaine de longueur $1$, il y a deux options soit $0,1$.

Donc, là maintenant, lorsque qu'on étend à deux, trois et plus, le truc est-ce rendre compte que en construisant la chaine on a deux options.
Soit on place un $1$, à quel point le problème est identique à régler $num chains$ pour un example de taille $n-1$.

Si on place $0$, le choix est forcé, on **doit** le placer ainsi $01$. Si on place $10$, on est techniquement correct, mais cette option est déjà compté dans notre première cas. Si on place $00$, là on a un mouvement illégal.

Ainsi, si l'on place un $0$, on a le même problème, mais réduit par deux au lieu de un, ainsi $n-2$.
Là maintenant que cet logique est claire, on peut l'implémenter de manière itérative au lieu de récursive en utilisant un tableau et remontant jusqu'à $n$. C'est l'implémentation choisie, si nous l'avions fait de manière récursive, nous aurrions eu un complexité exponentielle ($2^n$).
```python
def num_chains(n): 
	if n == 0: return 0 
	if n == 1: return 2 
	dp_prev2=1
	dp_prev1=2
	for i in range(2, n+1):
		dp_curr = dp_prev1 + dp_prev2
		dp_prev2, dp_prev1 = dp_prev1, dp_curr
	return dp_prev1

N = 4
print(f"We can do {num_chains(N)} chains of length {N}")	
```

### b) Pourquoi complexité linéaire?
On observe que l'algorithme utilise une simple boucle de $2$ à $n+1$ et la loupe contient des opérations à temps constant qui n'augmente pas la complexité du problème.


## Exercice 3 ~

### a) Programmation dynamique
On cherche à calculer les nombres de Catalan $C_n$, qui représentent le nombre de façons de mettre des parenthèses sur un produit de $n$ termes.

Voici l'algorithme utilisant la programmation dynamique avec une complexité $\Theta(n^2)$:

```python
def catalan_number(n):
    # Initialisation du tableau
    dp = [0] * (n + 1)
    dp[0] = 1  # C_0 = 1

    # Calcul des nombres de Catalan
    for i in range(1, n + 1):
        for j in range(i):
            dp[i] += dp[j] * dp[i - j - 1]
    
    return dp[n]

n = 5
print(f"Le nombre de façons pour {n} termes est : {catalan_number(n)}")
```
### b) 
Cela est clair. La loupe externe va de $1, n+1$ ce qui donne $n$ itérations. Cette boucle externe contient une autre boucle de $j$ à $i$, dans laquelle les opérations sont faite de manière combiné. (La boucle interne dépend de la boucle externe)

Ainsi, nous avons une sommation gaussienne dans la boucle interne qui fait que nous faisons $1, 2, \dots, n$ itérations dans la boucle interne, ce qui est démontrablement $n²$.

Tout dépendant de comment on compte les opérations élémentaires, on aura un multiple de $n²$.

## 4) Programmation dynamique 
### a)
L'approche naïve serait de dire qu'à chaque étape nous avons 1 élément de plus, et nous pouvons en prendre un de chaque raison, ce qui donne $n!$, mais à cause de l'arrangement des éléments cela n'est pas si simple.

On peut approcher le problème différemment en observant qu'à chaque point, il y à deux options, soit on va à gauche, soit on va à droite. Cette chaine continue jusqu'à la dernière rangée.

Pour une pyramide de hauteur $n$, nous devons choisir gauche-droite $n-1$ fois.

Donc, il y a $2^{n-1}$ options au total.
### b) The Algorithm
Pour maximiser la somme des nombres traversés dans une pyramide, on utilise une approche **top-down** de programmation dynamique.

- On commence par le sommet et on descend progressivement.
- À chaque élément, on met à jour la somme maximale possible en atteignant les éléments de la ligne suivante.
- La somme maximale finale sera trouvée en prenant le maximum des valeurs dans la dernière ligne.

```python
def max_path_sum(pyramid):
    n = len(pyramid)
    # Create a DP array initialized to 0
    dp = [[0] * len(row) for row in pyramid]
    dp[0][0] = pyramid[0][0]

    for i in range(1, n):
        for j in range(len(pyramid[i])):
            # Update the current element in dp
            if j > 0:
                dp[i][j] = max(dp[i][j], dp[i-1][j-1] + pyramid[i][j])
            if j < len(pyramid[i-1]):
                dp[i][j] = max(dp[i][j], dp[i-1][j] + pyramid[i][j])

    return max(dp[-1])  

pyramid = [
    [3],
    [7, 4],
    [2, 4, 6],
    [8, 5, 9, 3]
]
print(f"Somme maximale : {max_path_sum(pyramid)}")
```

---

### c) Fonctionnement avec l'exemple donné
Pour la pyramide suivante :
```
    3
   7 4
  2 4 6
 8 5 9 3
```
1. **Première étape :** Initialiser la valeur du sommet. $dp[0][0] = pyramid[0][0]$
   $dp = [[3], [0, 0], [0, 0, 0], [0, 0, 0, 0\|3], [0, 0], [0, 0, 0], [0, 0, 0, 0]]$

2. **Deuxième étape :** Descendre à la première ligne ($[7, 4]$).
   - $dp[1][0] = dp[0][0] + 7 = 3 + 7 = 10$
   - $dp[1][1] = dp[0][0] + 4 = 3 + 4 = 7$
   $dp = [[3], [10, 7], [0, 0, 0], [0, 0, 0, 0\|3], [10, 7], [0, 0, 0], [0, 0, 0, 0]]$


3. **Troisième étape :** Descendre à la deuxième ligne ($[2, 4, 6]$).
   - $dp[2][0] = dp[1][0] + 2 = 10 + 2 = 12$
   - $dp[2][1] = \max(dp[1][0] + 4, dp[1][1] + 4) = \max(10 + 4, 7 + 4) = 14$
   - $dp[2][2] = dp[1][1] + 6 = 7 + 6 = 13$
   
   $dp = [[3], [10, 7], [12, 14, 13], [0, 0, 0, 0\|3], [10, 7], [12, 14, 13], [0, 0, 0, 0]]]$

4. **Quatrième étape :** Descendre à la dernière ligne ($[8, 5, 9, 3]$).
   - $dp[3][0] = dp[2][0] + 8 = 12 + 8 = 20$
   - $dp[3][1] = \max(dp[2][0] + 5, dp[2][1] + 5) = \max(12 + 5, 14 + 5) = 19$
   - $dp[3][2] = \max(dp[2][1] + 9, dp[2][2] + 9) = \max(14 + 9, 13 + 9) = 23$
   - $dp[3][3] = dp[2][2] + 3 = 13 + 3 = 16$
   $dp = [[3], [10, 7], [12, 14, 13], [20, 19, 23, 16\|3], [10, 7], [12, 14, 13], [20, 19, 23, 16]]$

5. **Cinquième étape :** Prendre la valeur maximale de la dernière ligne.
   - Somme maximale = $23$.
   - S'il advient que nous souhaitons trouver le chemin qui nous a permis d'obtenir la valeur (nous nous sommes simplement soucié de trouver le maximum vu que la question parle de maximisation,) il suffirait de rebrousser chemin en regardant à chaque fois dans les options disponibles en haut, laquelle est la différence du max obtenu (ici 23) et de la valeur qui était enregistré originalement dans la matrice. Ici on obtiendrait $14$, et donc on prendrait note de l'index où $14$ se trouve et rebrousserions chemin jusqu'à l'origine avec une complexité de $n$. Il pourrait avoir des complications comme des entrées dupliqués ce qui nous obligerait à considérer plusieurs chemin en même temps, mais au plus on aurait un multiple de $n$ tel chemin à traquer.
En tout la complexité de l'algorithme reste quadratique, car on ne fait rien d'autre qu'ajouter un terme linéaire à notre équation.

### d) Complexité
### Analyse
1. **Nombre de calculs à chaque niveau :**
   - Chaque niveau $i$ contient $i$ éléments, et pour chaque élément, nous effectuons un nombre constant de calculs.

2. **Nombre total de calculs :**
   - $[  \sum_{i=1}^{n} i = \frac{n(n+1)}{2}]$
   - Cela correspond à une complexité de $O(n^2)$.

3. **Complexité totale :**
   - Temps : $O(n^2)$ vu que chaque niveau est traversé une fois et comme on l'a dit on obtient une gaussienne.
   - Espace : $O(n^2)$ si on utilise une structure de tableau supplémentaire (comme ici) ou $O(1)$ si on modifie directement la pyramide.

## 5. Diviser pour régner
### a)
On nous demande de déterminer si deux entiers dans un tableau trié $S$ ont un produit $P$ en utilisant un algorithme de complexité $O(n)$.

Donc l'idée de l'algorithme utilise une approche de deux pointeurs. Et la logique va comme suit:
On initialise deux pointeurs: un pointeur $i$  au début du tableau $S[0]$ et un autre pointeur $j$ à la fin $S[n-1]$ .

Ensuite on calcule le produit:
   - À chaque étape, on calcule $S[i] \times S[j]$.
     - Si $S[i] \times S[j] == P$, alors les deux nombres sont trouvés et on retourne $True$.
     - Si $S[i] \times S[j] < P$ , cela signifie que $S[i]$ est trop petit, donc on incrémente  $i$.
     - Si $S[i] \times S[j] > P$, cela signifie que $S[j]$ est trop grand, donc on décrémente $j$.
2. **Condition d’arrêt** :
   - On s’arrête lorsque $i \geq j$, auquel cas on retourne $False$, car il n’existe aucun couple dont le produit est $P$.

### Pseudo-code :
```python
def produit_existe(S, P):
    i, j = 0, len(S) - 1
    while i < j:
        produit = S[i] * S[j]
        if produit == P:
            return True
        elif produit < P:
            i += 1
        else:
            j -= 1
    return False

# Exemple d'exécution
S = [1, 2, 3, 6, 8]
P = 18
print(f"Deux nombres ayant un produit égal à {P} existent : {produit_existe(S, P)}")
```

---

### b) Analyse de la complexité
### 1. **Initialisation** :
- Les deux pointeurs $i$ et $j$ sont initialisés en $O(1)$.

### 2. **Boucle principale** :
- À chaque itération, une comparaison $O(1)$ et un déplacement $O(1)$ sont effectués.
- Les pointeurs $i$ et $j$ avancent ou reculent linéairement à travers le tableau. Ainsi, au maximum, $n$ itérations seront nécessaires.

### 3. **Complexité totale** :
- **Temps** : La boucle s'exécute $O(n)$  fois, et chaque opération à l'intérieur de la boucle est $O(1)$. Donc la complexité est $O(n)$ .
- **Espace** : L’algorithme utilise un espace constant $O(1)$ car il ne nécessite pas de structure de données supplémentaire.

### Pire cas :
Le pire cas se produit lorsque $P$  ne peut pas être atteint. Par exemple, pour $P = 100$ et $S = [1, 2, 3, 6, 8]$, on parcourt tout le tableau sans trouver de couple valide. Même dans ce cas, l’algorithme effectue au plus $n$ itérations, donc la complexité reste $O(n)$ .

