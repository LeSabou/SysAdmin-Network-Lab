# Bandit – Level 0 → Level 1

## Objectif

Trouver le mot de passe du **Level 1**, stocké dans un fichier situé dans le répertoire personnel de `bandit0`.

## Les commandes

```bash
bandit0@bandit:~$ ls
readme
bandit0@bandit:~$ cat readme
```

## Explication détaillée

| Commande | Rôle |
|----------|------|
| `ls` | **List** : affiche la liste des fichiers et dossiers présents dans le répertoire courant. Ici, il révèle un seul fichier nommé `readme`. |
| `cat readme` | **conCATenate** : affiche le contenu du fichier `readme` directement dans le terminal. |

## En résumé

> « Liste les fichiers (`ls`), puis affiche le contenu du fichier `readme` (`cat readme`) pour y lire le mot de passe. »

## Résultat

Le fichier `readme` contient un message de félicitations et, à la fin, le mot de passe recherché :

```
The password you are looking for is: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
```

**Mot de passe du Level 1 : `ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If`**

## Astuces utiles

- `ls -a` affiche aussi les fichiers cachés (commençant par un `.`), souvent utiles dans les niveaux suivants.
- `ls -l` donne des détails (permissions, taille, date) sur chaque fichier.
- `cat` peut afficher plusieurs fichiers à la suite : `cat fichier1 fichier2`.