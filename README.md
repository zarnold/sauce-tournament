# sauce-tournament

Elire la meilleur sauce !

## Principe

Faire affronter les sauces au cours de plusieurs rounds , en affrontement 2 par 2.

Le principe de selection utilisée est le [Sytème Suisse](https://en.wikipedia.org/wiki/Swiss-system_tournament) avec un pairing basé sur le score cumulé (en nombre de voix )

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

Soit 16 sauce, donc 5 ( ln2(16) ) round suisses.

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
| algerienne  | X          | X     | _        | _        | _         | _       | _           | _        | _        | _         | _       | _     | _       | _      | _       | _          |
| curry       | X          | X     | _        | _        | _         | _       | _           | _        | _        | _         | _       | _     | _       | _      | _       | _          |
| cocktail    | _          | _     | X        | X        | _         | _       | _           | _        | _        | _         | _       | _     | _       | _      | _       | _          |
| moutarde    | _          | _     | X        | X        | _         | _       | _           | _        | _        | _         | _       | _     | _       | _      | _       | _          |
| bearnaise   | _          | _     | _        | _        | X         | X       | _           | _        | _        | _         | _       | _     | _       | _      | _       | _          |
| ketchup     | _          | _     | _        | _        | X         | X       | _           | _        | _        | _         | _       | _     | _       | _      | _       | _          |
| hollandaise | _          | _     | _        | _        | _         | _       | X           | X        | _        | _         | _       | _     | _       | _      | _       | _          |
| barbecue    | _          | _     | _        | _        | _         | _       | X           | X        | _        | _         | _       | _     | _       | _      | _       | _          |
| samourai    | _          | _     | _        | _        | _         | _       | _           | _        | X        | X         | _       | _     | _       | _      | _       | _          |
| andalouse   | _          | _     | _        | _        | _         | _       | _           | _        | X        | X         | _       | _     | _       | _      | _       | _          |
| tartare     | _          | _     | _        | _        | _         | _       | _           | _        | _        | _         | X       | X     | _       | _      | _       | _          |
| aioli       | _          | _     | _        | _        | _         | _       | _           | _        | _        | _         | X       | X     | _       | _      | _       | _          |
| harissa     | _          | _     | _        | _        | _         | _       | _           | _        | _        | _         | _       | _     | X       | X      | _       | _          |
| poivre      | _          | _     | _        | _        | _         | _       | _           | _        | _        | _         | _       | _     | X       | X      | _       | _          |
| blanche     | _          | _     | _        | _        | _         | _       | _           | _        | _        | _         | _       | _     | _       | _      | X       | X          |
| mayonnaise  | _          | _     | _        | _        | _         | _       | _           | _        | _        | _         | _       | _     | _       | _      | X       | X          |




| Sauce       | Part (%) | nb Votant | Total Votant (arrondi) |
| ----------- | -------- | --------- | ---------------------- |
| algerienne  | 34.5     | 113       | 39                     |
| curry       | 65.5     | 113       | 74                     |
| cocktail    | 29.5     | 112       | 33                     |
| moutarde    | 70.5     | 112       | 79                     |
| bearnaise   | 71.9     | 114       | 82                     |
| ketchup     | 28.1     | 114       | 32                     |
| hollandaise | 32.4     | 111       | 36                     |
| barbecue    | 67.6     | 111       | 75                     |
| samourai    | 62.9     | 105       | 66                     |
| andalouse   | 37.1     | 105       | 39                     |
| tartare     | 50       | 108       | 54                     |
| aioli       | 50       | 108       | 54                     |
| harissa     | 31.3     | 128       | 40                     |
| poivre      | 68.8     | 128       | 88                     |
| blanche     | 44.3     | 131       | 58                     |
| mayonnaise  | 55.7     | 131       | 73                     |





```python
import pandas as pd 
df= pd.DataFrame(index=['mayonnaise','ketchup','blanche','bearnaise','samourai', 'moutarde','algerienne', 'poivre', 'barbecue', 'harissa', 'andalouse', 'hollandaise', 'aioli', 'curry', 'tartare', 'cocktail'])

df['#1'] = 1

df.loc['algerienne']['#1'] =39
df.loc['curry']['#1'] =74
df.loc['cocktail']['#1'] =33
df.loc['moutarde']['#1'] =79

df.loc['bearnaise']['#1'] =82
df.loc['ketchup']['#1'] =32
df.loc['hollandaise']['#1'] =36 
df.loc['barbecue']['#1'] =75
df.loc['samourai']['#1'] =66 
df.loc['andalouse']['#1'] =39 
df.loc['tartare']['#1'] =54 
df.loc['aioli']['#1'] =54 
df.loc['harissa']['#1'] =40 
df.loc['poivre']['#1'] =88 
df.loc['blanche']['#1'] =58 
df.loc['mayonnaise']['#1'] =73 

res =17- df['#1'].rank()
res.name='rank'
df = df.join(res) 
df=df.sort_values('rank')
df.to_csv('result.csv')
```


|             |   #1 | rank |
| :---------- | ---: | ---: |
| poivre      |   88 |    1 |
| bearnaise   |   82 |    2 |
| moutarde    |   79 |    3 |
| barbecue    |   75 |    4 |
| curry       |   74 |    5 |
| mayonnaise  |   73 |    6 |
| samourai    |   66 |    7 |
| blanche     |   58 |    8 |
| aioli       |   54 |  9.5 |
| tartare     |   54 |  9.5 |
| harissa     |   40 |   11 |
| algerienne  |   39 | 12.5 |
| andalouse   |   39 | 12.5 |
| hollandaise |   36 |   14 |
| cocktail    |   33 |   15 |
| ketchup     |   32 |   16 |


Prochaines rencontres, en appairant par rang (*Système suisse*) :

- (Poivre, Bearnaise)
- (Moutarde, Barbecue)
- (Curry, Mayonnaise)
- (Samourai, Blanche)
- (Aioli, Harissa)
- (Tartare, Algérienne)
- (Andalouse, Hollandaise)
- (Cocktail, ketchup)

|             | algerienne | curry | cocktail | moutarde | bearnaise | ketchup | hollandaise | barbecue | samourai | andalouse | tartare | aioli | harissa | poivre | blanche | mayonnaise |
| ----------- | ---------- | ----- | -------- | -------- | --------- | ------- | ----------- | -------- | -------- | --------- | ------- | ----- | ------- | ------ | ------- | ---------- |
| algerienne  | X          | X     | _        | _        | _         | _       | _           | _        | _        | _         | O       | _     | _       | _      | _       | _          |
| curry       | X          | X     | _        | _        | _         | _       | _           | _        | _        | _         | _       | _     | _       | _      | _       | O          |
| cocktail    | _          | _     | X        | X        | _         | O       | _           | _        | _        | _         | _       | _     | _       | _      | _       | _          |
| moutarde    | _          | _     | X        | X        | _         | _       | _           | O        | _        | _         | _       | _     | _       | _      | _       | _          |
| bearnaise   | _          | _     | _        | _        | X         | X       | _           | _        | _        | _         | _       | _     | _       | O      | _       | _          |
| ketchup     | _          | _     | O        | _        | X         | X       | _           | _        | _        | _         | _       | _     | _       | _      | _       | _          |
| hollandaise | _          | _     | _        | _        | _         | _       | X           | X        | _        | O         | _       | _     | _       | _      | _       | _          |
| barbecue    | _          | _     | _        | O        | _         | _       | X           | X        | _        | _         | _       | _     | _       | _      | _       | _          |
| samourai    | _          | _     | _        | _        | _         | _       | _           | _        | X        | X         | _       | _     | _       | _      | O       | _          |
| andalouse   | _          | _     | _        | _        | _         | _       | O           | _        | X        | X         | _       | _     | _       | _      | _       | _          |
| tartare     | O          | _     | _        | _        | _         | _       | _           | _        | _        | _         | X       | X     | _       | _      | _       | _          |
| aioli       | _          | _     | _        | _        | _         | _       | _           | _        | _        | _         | X       | X     | O       | _      | _       | _          |
| harissa     | _          | _     | _        | _        | _         | _       | _           | _        | _        | _         | _       | O     | X       | X      | _       | _          |
| poivre      | _          | _     | _        | _        | O         | _       | _           | _        | _        | _         | _       | _     | X       | X      | _       | _          |
| blanche     | _          | _     | _        | _        | _         | _       | _           | _        | O        | _         | _       | _     | _       | _      | X       | X          |
| mayonnaise  | _          | O     | _        | _        | _         | _       | _           | _        | _        | _         | _       | _     | _       | _      | X       | X          |

