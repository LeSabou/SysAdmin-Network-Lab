# Bandit – Level 3 → Level 4

## Objectif

Trouver le mot de passe du **Level 4**, caché dans un **fichier caché** à l'intérieur d'un dossier nommé `inhere`.

## Les commandes

```bash
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere/
bandit3@bandit:~/inhere$ ls -ap
./  ../  ...Hiding-From-You
bandit3@bandit:~/inhere$ cat ./...Hiding-From-You
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
```

## Explication détaillée

| Commande | Rôle |
|----------|------|
| `ls` | Liste les fichiers : révèle un dossier `inhere`. |
| `cd inhere/` | **Change Directory** : entre dans le dossier `inhere`. |
| `ls -ap` | Liste les fichiers en incluant les fichiers cachés (`-a`) et en marquant les dossiers d'un `/` (`-p`). |
| `cat ./...Hiding-From-You` | Affiche le contenu du fichier caché `...Hiding-From-You`. |

## Le piège du fichier caché

Sous Unix/Linux, un fichier dont le nom **commence par un point (`.`)** est considéré comme **caché**. Il n'apparaît pas avec un simple `ls`.

Un `ls` classique dans `inhere` n'aurait rien affiché. Il faut l'option **`-a`** (*all*) pour voir tous les fichiers, y compris les cachés.

### Détail des options de `ls`

- **`-a`** (*all*) : affiche **tous** les fichiers, y compris ceux commençant par `.` (comme `./`, `../` et `...Hiding-From-You`).
- **`-p`** : ajoute un `/` à la fin des noms de dossiers, pour les distinguer facilement des fichiers.

On voit alors apparaître :
- `./` → le dossier courant
- `../` → le dossier parent
- `...Hiding-From-You` → le fichier caché recherché (son nom commence par trois points)

### Lire le fichier

Le nom commençant par `...`, on le préfixe par `./` pour éviter toute ambiguïté, puis on l'affiche avec `cat`.

## Résultat

**Mot de passe du Level 4 : `2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ`**

## Astuces utiles

- `ls -a` est le réflexe à avoir dès qu'un dossier semble vide : un fichier caché s'y trouve peut-être.
- `cd ..` permet de remonter au dossier parent ; `cd` seul (ou `cd ~`) ramène au répertoire personnel.
- `ls -la` combine l'affichage des fichiers cachés avec les détails (permissions, taille, date).