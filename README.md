# Préparation du TD

Question 1: Dans votre replit contrôle créer un dossier `c16_03`

Votre dépôt va se décomposer en trois parties la commande run risque de ne plus
fonctionner comme on s'y attendait précédemment.

Question 2: Dans l'onglet shell

```
cd c16_03
touch main.py
touch test_main.py
```

Question 3

Toujours dans shell
 - `pip install --user pytest pytest-cov`
 - `python main.py`

# Introduction aux classes.

## Position du problème

Au cours des précédents TD nous avons manipulé plusieurs types de structures de données comme les
tuples, les listes et les dictionnaires. Ces structures sont très souples mais parfois on souhaite
cadrer un peu plus les structures que l'on manipule, que ce soit sur les données ou sur les opérations
que l'on souhaite réaliser sur celles ci.

Pour stocker une note et calculer une moyenne on pourrait créer des tuples:

```python
note1 = ('eleve1', 'math', 13)
note2 = ('eleve1', 'physique', 15)
note3 = ('eleve1', 'math', 13)
note4 = ('eleve1', 'eco', 12)
note5 = ('eleve1', 'eco', 13)
note6 = ('eleve1', 'math', 12)
note7 = ('eleve2', 'math', 13)
note8 = ('eleve2', 'math', 14)

notes = [note1, note2, note3, note4, note5, note6,note7,note8]

```

Question 4
a/
calculez la moyenne de eleve1
b/
calculez la moyenne de eleve1 en maths
c/
Créer une fonction "moyenne_tuples" qui calcule la moyenne de d'un élève dans une matière.

Le premier paramètre doit être la liste des notes.

Ensuite il faut donner un paramètre par défaut pour l'élève et la matière.
Si on ne fournit rien on calcule la moyenne de toutes les notes.
On ne s'intéresse pas au fait que les matières soient pas les même pour tous les élèves.


Que se passe-t-il si on fait une faute de frappe dans la saisie d'une matière ?
Que se passe-t-il si quelqu'un rentre une chaine de caractère au lieu d'une nombre '14' au lieu de 14 ?
Que se passe-t-il si on veut ajouter des coefficient aux notes et aux matières ?
Que se passe-t-il si on a un triplet qui n'est pas du tout une note ?

Pour traiter ce genre de problème on a crée la programmation orientée objet.

D'après Wikipédia:

Elle consiste en la définition et l'interaction de briques logicielles appelées objets ; un objet représente un concept, une idée ou toute entité du monde physique, comme une voiture, une personne ou encore une page d'un livre. Il possède une structure interne et un comportement, et il sait interagir avec ses pairs. Il s'agit donc de représenter ces objets et leurs relations ; l'interaction entre les objets via leurs relations permet de concevoir et réaliser les fonctionnalités attendues, de mieux résoudre le ou les problèmes. Dès lors, l'étape de modélisation revêt une importance majeure et nécessaire pour la POO. C'est elle qui permet de transcrire les éléments du réel sous forme virtuelle.

On appelle un classe la définition de ces concepts / modèles et instance les différentes représentations.

Plus proche de nous 5,7,8 sont des instances de nombre entiers, 4/3 5/7 des instances de rationnels.


```python
class Note:
  def __init__(self, eleve, matiere, valeur): #La méthode pour créer un objet
    self.eleve = eleve
    self.matiere = matiere
    self.valeur = valeur


  def afficher(self):
    print('eleve', self.eleve, 'matiere', self.matiere, 'note', self.valeur)


onote = Note('eleve1', 'maths', 13)
print(onote.eleve)
print(onote.matiere)
print(onote.valeur)
Note.afficher(onote)

```

La méthode `__init__` permet d'initialiser l'instance, quand on appelle Note()

On peut aussi appeler directement `onote.afficher()` l'interpréteur fera automatiquement la conversion


Question 5/
Reprenez la liste de notes pour créer une nouvelle liste `onotes` qui seront des instance de Note

Question 6/
On aimerai bien pouvoir directement afficher une note en utilisant print(note) plutot que note.affiche.
Ajouter une methode
```python
  def __str__(self):
    return #ce que vous voulez afficher"
```


