# sauce-tournament

Elire la meilleur sauce !

## Principe

Faire affronter les sauces au cours de plusieurs rounds , en affrontement 2 par 2.

Le principe de selection utilisée est le [Sytème Suisse](https://en.wikipedia.org/wiki/Swiss-system_tournament) avec un pairing basé sur le score cumulé.

Le score final est la somme de tous les rounds

## Participants

1. Mayonnaise
1. ketchup
1. Sauce Blanche
1. Sauce Bearnaise
1. Sauce samourai
1. Moutarde
1. Sauce Algérienne
1. Sauce Poivre
1. Sauce barbecue
1. Harissa
1. Sauce Andalouse
1. Sauce Hollandaise
1. Sauce Aioli
1. Sauce Curry
1. Sauce Tartare
1. Sauce Cocktail

Soit 16 sauce, donc 4 round suisses.
La gagnante se

## Tirage Aléatoire premer round

Le code Python suivant a été utilisé pour  les pairs du 1er tirage :

```python

import random


def pop_random(lst):
    idx = random.randrange(0, len(lst))
    return lst.pop(idx)

pairs = []
lst=['mayonnaise','ketchup','blanche','bearnaise','samourai', 'moutarde','algerienne', 'poivre', 'barbecue', 'harissa', 'andalouse', 'hollandaise', 'aioli', 'curry', 'tartare', 'cocktail']
while lst:
    rand1 = pop_random(lst)
    rand2 = pop_random(lst)
    pair = rand1, rand2
    pairs.append(pair)
```

Et le 1er Round est : 

```
[('algerienne', 'curry'), ('cocktail', 'moutarde'), ('bearnaise', 'ketchup'), ('hollandaise', 'barbecue'), ('samourai', 'andalouse'), ('tartare', 'aioli'), ('harissa', 'poivre'), ('blanche', 'mayonnaise')]

```

## Résultats

### 1er Round

Table des rencontres pré résultats

|             | algerienne | curry | cocktail | moutarde | bearnaise | ketchup | hollandaise | barbecue | samourai | andalouse | tartare | aioli | harissa | poivre | blanche | mayonnaise |
| ----------- | ---------- | ----- | -------- | -------- | --------- | ------- | ----------- | -------- | -------- | --------- | ------- | ----- | ------- | ------ | ------- | ---------- |
| algerienne  |            |       |          |          |           |         |             |          |          |           |         |       |         |        |         |            |
| curry       |            |       |          |          |           |         |             |          |          |           |         |       |         |        |         |            |
| cocktail    |            |       |          |          |           |         |             |          |          |           |         |       |         |        |         |            |
| moutarde    |            |       |          |          |           |         |             |          |          |           |         |       |         |        |         |            |
| bearnaise   |            |       |          |          |           |         |             |          |          |           |         |       |         |        |         |            |
| ketchup     |            |       |          |          |           |         |             |          |          |           |         |       |         |        |         |            |
| hollandaise |            |       |          |          |           |         |             |          |          |           |         |       |         |        |         |            |
| barbecue    |            |       |          |          |           |         |             |          |          |           |         |       |         |        |         |            |
| samourai    |            |       |          |          |           |         |             |          |          |           |         |       |         |        |         |            |
| andalouse   |            |       |          |          |           |         |             |          |          |           |         |       |         |        |         |            |
| tartare     |            |       |          |          |           |         |             |          |          |           |         |       |         |        |         |            |
| aioli       |            |       |          |          |           |         |             |          |          |           |         |       |         |        |         |            |
| harissa     |            |       |          |          |           |         |             |          |          |           |         |       |         |        |         |            |
| poivre      |            |       |          |          |           |         |             |          |          |           |         |       |         |        |         |            |
| blanche     |            |       |          |          |           |         |             |          |          |           |         |       |         |        |         |            |
| mayonnaise  |            |       |          |          |           |         |             |          |          |           |         |       |         |        |         |            |


| Sauce | Part | nb Votant | Total Votant | Rank |
| ----- | ---- | --------- | ------------ | ---- |