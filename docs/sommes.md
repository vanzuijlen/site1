# Sommes en tout genre

La plupart des algorithmes de calcul de somme sont basés sur le principe suivant:

* On initialise une variable ```somme``` à $0$
* On parcourt les éléments à additionner en les ajoutant au fur et à mesure à ```somme```

**Rappel :** Parcours de listes

Il y a deux façons de parcourir des listes.

Sur les éléments :
```python
for el in liste:
    instructions
```
Sur les indices :
```python
for i in range(len(liste)):
    instructions
```

##  Somme des éléments d'une liste d'entiers

On considère une liste d'entiers ```[ 5, 0, 4, -5, 1, -3]``` et on souhaite calculer la somme de ses éléments.

Sans utiliser la fonction ```sum``` de python, écrire une fonction ```somme1(liste)``` ci-dessous qui  devra réussir les tests :

```python
assert somme1([0,1,2,3]) == 6
assert somme1([ 5, 0, 4, -5, 1, -3]) == 2
assert somme1([]) == 0
assert somme1([1]) == 1

```

{{ IDEv('exo2_1') }}



##  Sommes des éléments négatifs et positifs d'une liste d'entiers

On considère une liste d'entiers ```[ 5, 0, 4, -5, 1, -3]``` et on souhaite calculer les sommes de ses éléments négatifs et positifs, le résultat sera donné sous forme de tuple (somme_neg,somme_pos)

Écrire une fonction ```somme2(liste)``` ci-dessous qui  devra réussir les tests suivants :

```python
assert somme2([0,1,2,3]) == (0,6)
assert somme2([ 5, 0, 4, -5, 1, -3]) == (-8,10)
assert somme2([]) == (0,0)
assert somme2([0, 1, -1, 1, 0, 1]) == (-1 , 3)

```


{{ IDEv('exo2_2') }}


##  Calcul de moyenne 

Il s'agit de calculer la moyenne des valeurs d'une liste.

Écrire une fonction ```moyenne1(liste)``` qui renvoie la moyenne des éléments de la liste, cette fonction devra réussir les tests suivants :

```python
assert moyenne1([10,12,9,8,15]) == (10 + 12 + 9 + 8 + 15)/5
assert moyenne1([]) == 'liste vide' 
```


{{ IDEv('exo2_3') }}



##  Moyenne coefficientée

On dispose d'une liste de tuples (note, coefficient), on doit calculer la moyenne coefficientée .

Écrire une fonction ```moyenne2(liste)``` qui renvoie la moyenne coefficientée des éléments de la liste, cette fonction devra réussir les tests suivants :

```python
assert moyenne2([(10,2),(12,1),(9,1),(8,3),(15,1)]) == (10*2 + 12 + 9 + 8*3 + 15)/8
assert moyenne2([]) == 'liste vide' 
```


{{ IDEv('exo2_4') }}




## Avec des dictionnaires

On considère le tableau suivant dont les éléments sont des dictionnaires :

```python
animaux = [ {'nom':'Medor', 'espece':'chien', 'age':5, 'enclos':2},
            {'nom':'Titine', 'espece':'chat', 'age':2, 'enclos':5},
            {'nom':'Tom', 'espece':'chat', 'age':7, 'enclos':4},
            {'nom':'Belle', 'espece':'chien', 'age':6, 'enclos':3},
            {'nom':'Mirza', 'espece':'chat', 'age':6, 'enclos':5}]
```
Écrire une fonction ```moyenne3(tableau)``` qui renvoie l'âge moyen des chats, cette fonction devra réussir le test suivant :
```python
assert moyenne3(animaux) == 5.0
```
**Rappel :** 

Parcourir un dictionnaire :
```pyhon
for key in dico:
    instructions
```
Accéder aux valeurs :
```python
# Dans notre exemple
animaux[1] # est un dictionnaire
animaux[1]["nom"] # renvoie 'Titine
```

{{ IDEv('exo2_5') }}

