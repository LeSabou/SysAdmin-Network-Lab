# Bandit – Level 2 → Level 3

## Objectif

Trouver le mot de passe du **Level 3**, stocké dans un fichier dont le nom contient des **espaces** : `spaces in this filename`.

## Les commandes

```bash
bandit2@bandit:~$ ls
--spaces in this filename--
bandit2@bandit:~$ cat ./--spaces\ in\ this\ filename--
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
```

## Explication détaillée

| Commande | Rôle |
|----------|------|
| `ls` | Liste les fichiers. Ici un fichier nommé `--spaces in this filename--`. |
| `cat ./--spaces\ in\ this\ filename--` | Affiche le contenu du fichier, en gérant correctement les espaces du nom. |

## Le piège des espaces dans un nom de fichier

Dans le shell, **l'espace sert à séparer les arguments** d'une commande. Si on tape :

```bash
cat --spaces in this filename--
```

…le shell croit qu'on lui passe **plusieurs fichiers différents** (`--spaces`, `in`, `this`, `filename--`) au lieu d'un seul. De plus, `--spaces` ressemble à une option de commande, ce qui provoque une erreur.

### Les solutions

Il faut indiquer au shell que les espaces font partie du nom. Plusieurs méthodes possibles :

1. **Échappement avec `\`** (la méthode utilisée ici) — on place un antislash devant chaque espace :
   ```bash
   cat ./--spaces\ in\ this\ filename--
   ```

2. **Guillemets** — on entoure le nom complet de guillemets :
   ```bash
   cat "./--spaces in this filename--"
   cat './--spaces in this filename--'
   ```

Le préfixe `./` reste utile ici car le nom commence par `--`, ce qui pourrait être pris pour une option.

> Astuce : taper le début du nom puis appuyer sur **Tab** (autocomplétion) ajoute automatiquement les antislash au bon endroit.

## Résultat

**Mot de passe du Level 3 : `MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx`**

## Astuces utiles

- `\` échappe un seul caractère ; les guillemets `"` ou `'` protègent tout ce qu'ils entourent.
- L'autocomplétion (touche **Tab**) est la façon la plus simple et la moins risquée de saisir des noms compliqués.
- Le `./` au début protège aussi contre les noms qui commencent par `-` ou `--`.