# Les tris

Voilà une animation de 3 algorithmes de tris.

Dans chaque cas prenez le temps de 'verbaliser' ce qui se passe...

<iframe
  src="https://isn-icn-ljm.pagesperso-orange.fr/tri2/index.html"
  style="width:100%; height:600px;"
></iframe>

**Rappel :** voici un code qui permet de créer un tableau de 15 entiers aléatoirement choisis entre 0 et 100.  

```python
from random import randint
tab = [randint(0,100) for i in range(15)]
```

## Le tri par insertion

Compléter le code suivant qui réalise le tri par insertion et le tester. 

```python
def tri_insertion(t):
    n = ...
    for i in range(...,n):
        k = ...
        while k > 0 :
            if t[...] > t[k]:
                t[...],t[k-1] = t[...],t[k]
            k = ...
    return t 

```

{{ IDEv('exo1_1') }}


## Le tri par sélection

Compléter le code suivant qui réalise le tri par selection et le tester.

```python
def tri_selection(t):
    n = len(t)
    for i in range(...):
        k = ...
        while k < n :
            if t[i] < t[...]:
                t[...],t[i] = t[...],t[k]
            k = ...
     return t 
```

{{ IDEv('exo1_1') }}

## Le tri à bulles

Compléter le code suivant qui réalise le tri à bulles et le tester.

```python
def tri_bulle(t):
    n = ...
    k = n - 1 
    while k > ... :
        for j in range(...):
            if t[...] > t[...]:
                t[...],t[...] = t[...],t[...]
        k = ...
    return t  
```

{{ IDEv('exo1_1') }}