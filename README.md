# 🖥️ Sysadmin & Network Lab

Repository de progression en administration système et réseau.
Chaque module regroupe des exercices pratiques, mes notes, mes scripts et les erreurs rencontrées (et résolues).

> **Objectif :** monter en compétences de façon structurée et documentée, avec des livrables réutilisables en environnement pro.

---

## 📊 Progression globale

| Module | Statut | Compétences clés |
|--------|:------:|------------------|
| [01 — Fondamentaux Linux](./01-linux-fundamentals) | ⬜ | systemd, permissions, LVM, bash |
| [02 — Réseau](./02-networking) | ⬜ | TCP/IP, subnetting, nftables, WireGuard |
| [03 — Services](./03-services) | ⬜ | DNS, Nginx/TLS, NFS/Samba, DHCP |
| [04 — Virtualisation & conteneurs](./04-virtualization) | ⬜ | KVM, Proxmox, Docker, k3s |
| [05 — Automatisation / IaC](./05-automation) | ⬜ | Ansible, Terraform, Git |
| [06 — Monitoring & Sécurité](./06-monitoring-security) | ⬜ | Prometheus, Grafana, hardening, backups |
| [07 — Projets intégrateurs](./07-projects) | ⬜ | Homelab complet, déploiements automatisés |

**Légende :** ⬜ À faire · 🟡 En cours · ✅ Terminé

---

## ✍️ Méthode de travail

1. **Un objectif clair** par exercice.
2. **Documenter en faisant** : commandes, erreurs, résolutions (c'est ce qui a le plus de valeur).
3. **Commits atomiques** : `feat:`, `docs:`, `fix:`.
4. **Jamais de secrets** : voir `.gitignore`, utiliser des fichiers `*.example`.
5. **Refaire de mémoire** une fois l'exercice terminé pour valider l'acquisition.

> **Principe directeur :** ne pas se contenter de lire — **casser son système puis le réparer**. Le dépannage est la façon la plus efficace de progresser.

---

# 📚 Ressources par module

## ⭐ Plateformes multi-modules (à connaître en priorité)
- [Killercoda](https://killercoda.com/) — vrai shell, VM temporaires, validation auto. Ansible, Terraform, Nginx, K8s, Docker, Grafana. (modules 03→06)
- [iximiuz Labs](https://labs.iximiuz.com/) — vrais serveurs, parcours Linux/Docker/K8s/réseau, navigateur ou SSH. (01, 02, 04)
- [LabEx](https://labex.io/) — terminal réel en navigateur, 200+ labs, sans inscription pour démarrer. (01, 02, 04)
- [KodeKloud (free)](https://kodekloud.com/free-courses) — labs Docker, kubectl, Ansible gratuits. (04, 05)

## 🐧 01 — Fondamentaux Linux
- [OverTheWire — Bandit](https://overthewire.org/wargames/bandit/) — wargame SSH, maîtrise CLI (niveaux 0→20). Le passage obligé.
- [LabEx / Linux Journey](https://labex.io/linuxjourney) — labs gamifiés, terminal réel.
- [Linux Upskill Challenge](https://linuxupskillchallenge.org/) — tu montes ton propre serveur comme un vrai sysadmin.
- [Programme LFCS](https://training.linuxfoundation.org/certification/linux-foundation-certified-sysadmin-lfcs/) — checklist de compétences à cocher.

## 🌐 02 — Réseau
- [Subnetting Practice](https://subnettingpractice.com/) — subnetting jusqu'à le faire de tête.
- [Cisco Packet Tracer](https://www.netacad.com/courses/packet-tracer) — topologies complètes (VLAN, routage), gratuit via Networking Academy.
- [GNS3](https://www.gns3.com/) + [Wireshark](https://www.wireshark.org/) — simulation réseau avancée, combo open source.
- [iximiuz Labs](https://labs.iximiuz.com/) — parcours réseau sur vrais serveurs.

## 🛠️ 03 — Services
- [nginx-basics-workshops](https://github.com/nginxinc/nginx-basics-workshops) — labs séquentiels : Nginx opérationnel + reverse proxy + DNS entre conteneurs.
- [Killercoda](https://killercoda.com/) — scénarios Nginx et services en VM temporaires.

## 📦 04 — Virtualisation & conteneurs
- [LabEx — Kubernetes](https://labex.io/free-labs/kubernetes) — gestion de cluster, orchestration.
- [KodeKloud (free)](https://kodekloud.com/free-courses) — Docker et kubectl en hands-on.
- [iximiuz Labs](https://labs.iximiuz.com/) — parcours Docker & Kubernetes.
- ⚠️ *Play with Kubernetes ferme le 1er mars 2026 — privilégier LabEx/Killercoda.*

## ⚙️ 05 — Automatisation / IaC
- [KodeKloud — Ansible labs](https://kodekloud.com/studio/labs/ansible) — YAML, inventaire, playbooks, modules, variables, boucles.
- [Killercoda](https://killercoda.com/) — scénarios Ansible **et** Terraform (HashiCorp).

## 🔐 06 — Monitoring & Sécurité
- [Killercoda](https://killercoda.com/) — scénarios Grafana, monitoring.
- [TryHackMe](https://tryhackme.com/) — parcours guidés, le plus accessible pour débuter.
- [Hack The Box](https://www.hackthebox.com/) — machines réalistes, niveau intermédiaire.
- [Lynis (CISOfy)](https://cisofy.com/lynis/) — outil d'audit à lancer sur tes serveurs.

## 🏗️ 07 — Projets
- [freeCodeCamp — DevOps HomeLab 2026](https://www.freecodecamp.org/news/how-to-build-a-local-devops-homelab-with-docker-kubernetes-and-ansible/) — app multi-services (frontend/API/PostgreSQL/Redis) avec Docker Compose, K8s, Prometheus/Grafana, GitOps.

---

# 🎯 Projet de fin de module

Chaque module se conclut par un projet concret à déposer dans `07-projects/`. C'est le livrable qui prouve la compétence (et qui parle en entretien).

### 01 — Linux → **Serveur Linux durci & automatisé à la main**
Monter un serveur from scratch : users + sudo limité, service systemd custom, timer de sauvegarde journalisé, LVM extensible. Documenter chaque étape et au moins une panne réparée.
*Compétences : permissions, systemd, LVM, bash.*

### 02 — Réseau → **Mini-infra routée et filtrée**
Une VM "routeur" entre deux réseaux, firewall nftables en politique DROP par défaut, tunnel WireGuard entre deux machines. Fournir le plan d'adressage (subnetting) et un schéma.
*Compétences : routage, nftables, WireGuard, subnetting.*

### 03 — Services → **Stack web auto-hébergée**
Reverse proxy Nginx en HTTPS (Let's Encrypt) devant une app, DNS local résolvant le service, partage de fichiers (NFS ou Samba). Viser un score ≥ A sur testssl.sh.
*Compétences : Nginx/TLS, DNS, partage de fichiers, hardening.*

### 04 — Virtualisation → **Déploiement conteneurisé reproductible**
Une stack docker-compose multi-conteneurs (app + db + proxy) qui remonte intègre après reboot, puis portage de la même app sur k3s (Deployment + Service). Inclure ton serveur RustDesk comme étude de cas.
*Compétences : Docker, compose, k3s, Proxmox/LXC.*

### 05 — Automatisation → **Pipeline IaC de bout en bout**
Terraform provisionne une VM, Ansible la configure (Nginx + hardening SSH via un rôle réutilisable), secrets chiffrés avec Vault. Playbooks idempotents (2ᵉ run = `changed=0`).
*Compétences : Terraform, Ansible, Vault, Git.*

### 06 — Monitoring & Sécurité → **Observabilité + plan de reprise**
Prometheus + node_exporter + dashboard Grafana avec une alerte réelle, logs centralisés (Loki), sauvegardes chiffrées restic **avec restauration testée**, audit lynis corrigé.
*Compétences : Prometheus/Grafana, Loki, restic, hardening.*

### 07 — Projet final → **Homelab complet documenté**
Assembler tout : Proxmox héberge l'infra, réseau segmenté et filtré, services déployés via IaC, monitoring et sauvegardes en place. Un README qui permet à quelqu'un d'autre de **reproduire** l'infra, avec schéma d'architecture et choix techniques justifiés.
*Compétences : tous les modules.*

---

## 🔒 Sécurité
Aucun secret (mot de passe, clé privée, token) ne doit être commité.
Les configs sensibles sont fournies en version `*.example`.
