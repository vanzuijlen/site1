# Des exercices

## Élocution chez le dentiste

Chez le dentiste, la bouche grande ouverte, lorsqu'on essaie de parler, il ne reste que les voyelles. Même les ponctuations sont supprimées. Vous devez écrire une fonction ```dentiste``` qui prend une chaine de caractères ```texte``` et qui renvoie une autre chaine ne contenant que les voyelles de texte, placées dans l'ordre. 

Les voyelles sont données par : 

```python
VOYELLES = ['a', 'e', 'i', 'o', 'u', 'y']
```
On ne considèrera que des textes écrits en minuscules, sans accents.

**Exemples**
```python
dentiste("j'ai mal")
# affiche
'aia'
dentiste("il fait chaud")
# affiche
'iaiau'
dentiste("")
# affiche
''
```
la fonction devra passer les tests suivants:
```python
assert dentiste("j'ai mal") == 'aia'
assert dentiste("il fait chaud") == 'iaiau'
assert dentiste("") == ''
```

{{ IDEv('exo4_1') }}

## Rendu de monnaie
On s’intéresse au problème du rendu de monnaie. On suppose qu’on dispose d’un
nombre infini de billets de 5 euros, de pièces de 2 euros et de pièces de 1 euro.
Le but est d’écrire une fonction nommée `rendu` dont le paramètre est un entier positif non
nul `somme_a_rendre` et qui retourne une liste de trois entiers `n1`, `n2` et `n3` qui
correspondent aux nombres de billets de 5 euros (`n1`) de pièces de 2 euros (`n2`) et de
pièces de 1 euro (`n3`) à rendre afin que le total rendu soit égal à `somme_a_rendre`.

On utilisera un algorithme glouton : on commencera par rendre le nombre maximal de
billets de 5 euros, puis celui des pièces de 2 euros et enfin celui des pièces de 1 euros.

Exemples :
```python
rendu(13)
# affiche
[2,1,1]
rendu(64)
# affiche
[12,2,0]
rendu(89)
#affiche
[17,2,0]
```
{{ IDEv('exo4_2') }}

## Conversion

Pour rappel, la conversion d’un nombre entier positif en binaire peut s’effectuer à l’aide
des divisions successives comme illustré ici :

![image](images/img21_2.png){: .center}

Voici une fonction Python basée sur la méthode des divisions successives permettant de convertir un nombre entier positif en binaire :

```python
def binaire(a):
    bin_a = str(...)
    a = a // 2
    while a ... :
        bin_a = ...(a%2) + ...
        a = ...
    return bin_a
```
Compléter la fonction binaire.

{{ IDEv('exo4_3') }}

## XOR
L'opérateur « ou exclusif » entre deux bits renvoie 0 si les deux bits sont égaux et 1 s'ils sont
différents :  
0 ⊕ 0 = 0 , 0 ⊕ 1 = 1 , 1 ⊕ 0 = 1 , 1 ⊕ 1 = 0

On représente ici une suite de bits par un tableau contenant des 0 et des 1.

Exemples :

```python
a = [1, 0, 1, 0, 1, 1, 0, 1]
b = [0, 1, 1, 1, 0, 1, 0, 0]
c = [1, 1, 0, 1]
d = [0, 0, 1, 1]
```

Écrire la fonction ```xor``` qui prend en paramètres deux tableaux de même longueur et qui renvoie
un tableau où l’élément situé à position `i` est le résultat, par l’opérateur « ou exclusif », des
éléments à la position `i` des tableaux passés en paramètres.

En considérant les quatre exemples ci-dessus, cette fonction doit passer les tests suivants :

```python
assert(xor(a, b) == [1, 1, 0, 1, 1, 0, 0, 1])
assert(xor(c, d) == [1, 1, 1, 0])
```
{{ IDEv('exo4_4') }}

## Tri itératif

On considère l'algorithme de tri de tableau suivant : à chaque étape, on parcourt depuis le début du tableau tous les éléments non rangés et on place en dernière position le plus grand élément.

Exemple avec le tableau : ```t = [41, 55, 21, 18, 12, 6, 25]``` 

- Étape 1 : on parcourt tous les éléments du tableau, on permute le plus grand élément avec le dernier.

Le tableau devient `t = [41, 25, 21, 18, 12, 6, 55]`

- Étape 2 : on parcourt tous les éléments **sauf le dernier**, on permute le plus grand élément trouvé avec l'avant dernier.

Le tableau devient : ```t = [6, 25, 21, 18, 12, 41, 55]``` 

Et ainsi de suite. La code de la fonction `tri_iteratif` qui implémente cet algorithme est donné ci-dessous.

```python
def tri_iteratif(tab):
    for k in range(..., 0 ,-1):
        imax = ...
        for i in range(0, ...):
            if tab[i] > ... :
                imax = i
        if tab[imax] > ... :
            ..., tab[imax] = tab[imax], ...
    return tab
```
Compléter le code qui doit passer ce test :
```python
assert tri_iteratif([41, 55, 21, 18, 12, 6, 25]) == [6, 12, 18, 21, 25, 41, 55]
```
On rappelle que l'instruction a, b = b, a échange les contenus de a et b. ``` 

{{ IDEv('exo4_5') }}

## Delta encoding

Le codage par différence (delta encoding en anglais) permet de compresser un tableau de données en indiquant pour chaque donnée, sa différence avec la précédente (plutôt que la donnée elle-même). On se retrouve alors avec un tableau de données assez petites nécessitant moins de place en mémoire. Cette méthode se révèle efficace lorsque les valeurs consécutives sont proches.

Programmer la fonction ```delta_encoding``` qui prend en paramètre un tableau non vide de nombres entiers et qui renvoie un tuple à deux éléments comprenant :

 *   En premier, la valeur initiale
 *   En second, le tableau des différences, contenant les valeurs entières  compressées à l'aide de cette technique.

la fonction devra passer le test suivant:
```python
assert delta_encoding([1000000, 1000042, 1000040, 1000055, 1000010]) ==  (1000000, [42, -2, 15, -45])

assert delta_encoding([42]) == (42, [])
```
{{ IDEv('exo4_6') }}