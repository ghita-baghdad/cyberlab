<div align="center">

# 🛡️ CyberLab

### Laboratoire de cybersécurité — parcours guidé pour étudiants

*Construire · Attaquer · Défendre — dans un environnement isolé et légal.*

![Statut](https://img.shields.io/badge/statut-actif-12a06b)
![Niveau](https://img.shields.io/badge/niveau-M1-2f6fed)
![Licence](https://img.shields.io/badge/usage-pédagogique-e23b4e)
![Hébergement](https://img.shields.io/badge/déploiement-GitHub%20Pages-1a212e)

> *« The best defenders understand how attackers think — and this project brought both worlds together. »*

</div>

---

## 📖 À propos

**CyberLab** est un site web statique, en français, qui guide pas à pas des étudiants de
Master 1 dans la construction et l'utilisation d'un **laboratoire de cybersécurité**.
L'apprenant monte son infrastructure, relie une machine **attaquante** et une machine
**cible**, puis progresse de la reconnaissance réseau jusqu'au test d'intrusion complet.

Le principe directeur : **on ne défend bien que ce que l'on sait attaquer.** Chaque
activité fait jouer tour à tour le rôle offensif (Red) et défensif (Blue).

> ⚠️ **Aucune solution n'est publiée dans ce dépôt.** Les corrigés, mots de passe et
> clés de correction restent hors du site (usage enseignant uniquement).

---

## ✨ Fonctionnalités

- 🧭 **Parcours guidé en 8 étapes** — installation de VirtualBox, Kali et Metasploitable 2,
  configuration du **Réseau NAT isolé**, adressage, vérification de connectivité.
- 🗺️ **Schéma d'architecture interactif** — visualisation du réseau et des deux machines.
- 🔐 **Crackme #1** — initiation à la rétro-ingénierie (décompilation & débogage sur Kali).
- 🎯 **Projet final** — test d'intrusion complet sur Metasploitable 2 : mise en situation,
  familles de failles à rechercher, boîte à outils, démarche en 5 phases et livrables.
- 💾 **Progression sauvegardée** localement (navigateur), aucune donnée envoyée.
- 🌓 **Interface claire et responsive**, accessible au clavier.

---

## 🧩 Contenu pédagogique

| Module | Accès | Objectif |
| --- | --- | --- |
| **Séance 01 — Premiers pas** | Parcours principal (8 étapes) | Monter le lab et observer ses premiers services réseau |
| **Architecture** | Bouton d'en-tête | Comprendre le Réseau NAT et les deux rôles |
| **Crackme #1** | Bouton d'en-tête | Retrouver un secret dans un binaire (reverse engineering) |
| **Projet final** | Bouton d'en-tête | Mener un pentest complet et rédiger un rapport pro |

---

## 🚀 Déploiement (GitHub Pages)

1. Poussez le contenu de ce dépôt sur la branche `main`.
2. Dans **Settings → Pages**, choisissez la source **`main` / root**.
3. Le fichier `.nojekyll` garantit une publication statique directe.
4. Le site est en ligne à `https://<votre-utilisateur>.github.io/<nom-du-dépôt>/`.

---

## 💻 Aperçu en local

Aucune dépendance, aucune compilation. Servez simplement le dossier :

```bash
# Python 3
python3 -m http.server 8000
# puis ouvrez http://localhost:8000
```

> Ouvrir `index.html` directement par un double-clic (`file://`) fonctionne aussi, mais
> un petit serveur local évite les restrictions de certains navigateurs.

---

## 📂 Structure du dépôt

```
cyberlab/
├── index.html      # Structure de la page
├── style.css       # Thème clair (nuances bleu / vert / rouge) et mise en page
├── app.js          # Contenu des étapes, fenêtres et interactions
├── .nojekyll       # Publication statique sur GitHub Pages
└── README.md       # Ce fichier
```

---

## 🎨 Personnalisation

- **Couleurs** : variables CSS en bas de `style.css` (`--blue`, `--green`, `--red`, …).
- **Étapes** : tableau `steps` dans `app.js`.
- **Fenêtres** (Architecture, Crackme, Projet final) : fonctions dédiées dans `app.js`,
  rendues avec les mêmes briques (`box`, `code`, `note`).

---

## ⚖️ Cadre éthique & légal

Toutes les manipulations se déroulent dans un **réseau virtuel isolé** que vous
contrôlez. Ne scannez, ne sondez et n'attaquez **jamais** un système sans **autorisation
écrite** de son propriétaire. L'accès non autorisé à un système informatique est une
**infraction pénale** (France : art. 323-1 et s. du Code pénal ; équivalents
internationaux). Metasploitable 2 ne doit **jamais** être exposée à un réseau réel ni à
Internet.

---

## 📜 Licence & usage

Projet à vocation **strictement pédagogique**. Réutilisation et adaptation libres dans un
cadre d'enseignement, en conservant la mention d'origine et le présent cadre éthique.

<div align="center">

**CyberLab** · Guide étudiant · M1 Cybersécurité

</div>
