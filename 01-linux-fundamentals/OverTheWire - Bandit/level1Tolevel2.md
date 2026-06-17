# Bandit – Level 1 → Level 2

## Objectif

Trouver le mot de passe du **Level 2**, stocké dans un fichier dont le nom est un simple tiret : `-`.

## Les commandes

```bash
bandit1@bandit:~$ ls
-
bandit1@bandit:~$ cat ./-
263JGJPfgU6LtdEvgfWU1XP5yac29mFx
```

## Explication détaillée

| Commande | Rôle |
|----------|------|
| `ls` | Liste les fichiers du répertoire courant. Ici, un seul fichier nommé `-`. |
| `cat ./-` | Affiche le contenu du fichier `-`, mais en le préfixant par `./` pour indiquer son chemin. |

## Le piège du fichier nommé `-`

En ligne de commande, le tiret `-` a une signification spéciale : beaucoup de programmes l'interprètent comme **« l'entrée standard »** (le clavier) plutôt que comme un nom de fichier.

Si on tape simplement :

```bash
cat -
```

…la commande **attend une saisie au clavier** au lieu d'afficher le fichier (elle semble « bloquée »).

### La solution

Il faut forcer le shell à comprendre que `-` est bien un **nom de fichier** en précisant son chemin :

```bash
cat ./-
```

Le préfixe `./` signifie « dans le répertoire courant ». Ainsi le nom complet devient `./-`, qui ne peut plus être confondu avec l'option spéciale `-`.

> Alternative possible : `cat < -` (redirection d'entrée).

## Résultat

**Mot de passe du Level 2 : `263JGJPfgU6LtdEvgfWU1XP5yac29mFx`**

## Astuces utiles

- Préfixer un nom de fichier « bizarre » par `./` est une technique générale pour gérer les noms commençant par `-` ou contenant des caractères spéciaux.
- Cette astuce fonctionne avec d'autres commandes : `rm ./-`, `mv ./- nouveau_nom`, etc.
- Le tiret `-` comme synonyme de l'entrée/sortie standard est une convention que partagent de nombreux outils Unix (`cat`, `tar`, `grep`…).