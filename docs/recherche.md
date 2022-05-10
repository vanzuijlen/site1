# Maximum et minimum

La plupart des algorithmes de recherche de maximum ou de minimum sont basés sur le principe suivant :

* On initialise une variable ```maxi``` ou ```mini``` suivant le contexte
*  On parcourt les éléments à comparer en remplaçant le ```maxi``` (ou ```mini```) si nécessaire

## Maximum et minimum d'une liste d'entiers

Écrire une fonction ```extremum(liste)``` qui renvoie le maximum et le minimum des éléments de la liste sous forme d'un tuple ```(maxi , mini)```, sans bien sûr utiliser les fonctions ```min``` et ```max``` de python

Cette fonction devra passer les tests suivants:

```python
assert extremum([1,-2,12,5,54,-10]) == (-10,54)
assert extremum([]) == 'liste vide'
```

{{ IDEv('exo3_1') }}

## Une tableau de tuples

Écrire une fonction ```maximum1(tableau)``` qui renvoie le tuple dont le second élément est le plus grand.

Cette fonction devra passer les tests suivants:

```python
assert extremum([(12,-5),(5,13),(-9,15),(0,0)]) == (-9,15)
assert extremum([]) == 'liste vide'
```

{{ IDEv('exo3_2') }}

## Un dictionnaire

On considère le dictionnaire suivant, dont les clés sont des noms d'élèves et les valeurs des notes. 
```python
classe = {"gérard":[12,8,6,15],
        "louis":[17,5,12],
        "sylvie":[2,18,15,13],
        "mariane":[12,13,7,10]}
```
Écrire une fonction ```maximum2(classe)``` qui renvoie l'élève qui a la meilleure moyenne et sa moyenne sous forme de tuple, le résultat attendu est ```('sylvie', 12.0)```

{{ IDEv('exo3_3') }}

**Recherche d'éléments dans un tableau** 

## Recherche d'un élément dans un tableau non trié

La recherche d'un objet dans un tableau, consiste à parcourir le tableau et à renvoyer ```True``` si l'objet est trouvé et ```False``` sinon.

Écrire une fonction ```recherche1(tab,element)``` qui renvoie ```True``` si l'élément est présent dans le ntableau et ```False``` sinon

Cette fonction devra passer les tests suivants:

```python
assert recherche1([1,-2,5,-4,0,10,45],0) == True
assert recherche1([1,-2,5,-4,0,10,45],2) == False
assert recherche(['lapin','autruche','castor','chat','chien'],'chien') == True
assert recherche1([],0) == 'tableau vide'
```

{{ IDEv('exo3_4') }}

## Recherche dans un tableau trié

On utilise ici l'algorithme de recherche par dichotomie, copier-coller le code à compléter ci-dessous et compléter-le.

```python
def recherche2(tab,element):
    debut = ...
    fin = ...
    while debut <= ...:
        milieu = (.......)//2
        if tab[milieu] == .....:
            return ....
        else:
            if ......:
                fin = milieu - 1
            else:
                debut = milieu + 1
    return False

t =[0,1,2,3,4,5,6,7,8,9,10,11,12,13,14]
assert recherche2(t,-1) == False
assert recherche2(t,0) == True
assert recherche2(t,7) == True
assert recherche2(t,14) == True
assert recherche2(t,15) == False
```
{{ IDEv('exo3_5') }}


Pour le 3.6 et 3.7, on n'utilisera ni la fonction index, ni la fonction find.

**Rappel**

On peut parcourir les tableaux(liste) et les chaînes de caractères par leur indices:
```python
ma_chaine = 'ceci est un exmple'
for i in range(len(ma_chaine)):
 print(machaine[i])
# affiche toutes les lettre de ma_chaine
```  

## Indice de la première occurrence

Écrire une fonction ```indice``` qui prend en paramètres ```element``` un nombre entier, ```tableau``` un tableau de nombres entiers, et qui renvoie l'indice de la première occurrence de ```element``` dans ```tableau```.

La fonction devra renvoyer ```None``` si ```element``` est absent de ```tableau```

```python
# Exemple 
indice(1, [10, 12, 1, 56]) 
#affiche
2
indice(1, [1, 50, 1])
#affiche
0
indice(15, [8, 9, 10, 15])
#affiche
3
indice(1, [2, 3, 4])
#affiche
None
```

Cette fonction devra passer les tests suivants:

```python
assert indice(1, [10, 12, 1, 56]) == 2
assert indice(1, [1, 50, 1]) == 0
assert indice(15, [8, 9, 10, 15]) == 3
assert indice(1, [2, 3, 4]) is None
```
{{ IDEv('exo3_6') }}


## Occurrences d'un caractère dans un mot

Écrire une fonction ```compte_occurrences``` qui prend en paramètres ```cible```, un caractère (une chaine de caractères de longueur 1), et ```mot```, une chaine de caractères, et qui renvoie le nombre d'occurrences de ```cible``` dans ```mot``` ; c'est-à-dire le nombre de fois où ```cible``` apparait dans ```mot```.

On n'utilisera pas la méthode ```count```.

Cette fonction devra passer les tests suivants:

```python
assert compte_occurrences("o", "bonjour") == 2
assert compte_occurrences("a", "abracadabra") == 5
assert compte_occurrences("i", "abracadabra") == 0
```
{{ IDEv('exo3_7') }}

