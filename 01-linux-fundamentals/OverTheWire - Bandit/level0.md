# Bandit – Level 0

## La commande

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

## Explication détaillée

Cette commande ouvre une connexion à distance vers le serveur du wargame OverTheWire (Bandit) en utilisant le protocole **SSH** (Secure Shell), qui chiffre toute la communication.

| Élément | Rôle |
|---------|------|
| `ssh` | Le programme client qui établit une connexion sécurisée et chiffrée vers une machine distante. |
| `bandit0` | Le **nom d'utilisateur** avec lequel on se connecte. Pour le Level 0, c'est `bandit0`. |
| `@` | Séparateur entre le nom d'utilisateur et l'adresse du serveur. Se lit « bandit0 *chez* … ». |
| `bandit.labs.overthewire.org` | Le **nom d'hôte** (adresse) du serveur distant auquel on se connecte. |
| `-p 2220` | L'option `-p` précise le **port** à utiliser. Ici `2220` au lieu du port SSH par défaut (`22`). |

## En résumé

> « Connecte-moi de façon sécurisée au serveur `bandit.labs.overthewire.org`, sur le port `2220`, en tant qu'utilisateur `bandit0`. »

## Étapes pour le Level 0

1. Lancer la commande ci-dessus dans un terminal.
2. À l'invite `password:`, saisir le mot de passe : **`bandit0`** (le mot de passe du premier niveau est identique au nom d'utilisateur).
   - Le mot de passe ne s'affiche pas à l'écran pendant la frappe, c'est normal.
3. Une fois connecté, l'objectif du Level 0 est de trouver le mot de passe du niveau suivant (`bandit1`), généralement stocké dans un fichier du répertoire personnel.

## Astuces utiles

- Première connexion : SSH peut demander de confirmer l'empreinte du serveur. Taper `yes` pour l'accepter.
- Pour quitter la session distante : taper `exit` ou utiliser `Ctrl + D`.
- `-p` (minuscule) = **port**. À ne pas confondre avec d'autres options SSH.
