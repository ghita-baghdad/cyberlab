# CyberLab — Séance 01

Plateforme pédagogique statique en français pour construire un laboratoire VirtualBox. Design sombre, accents rouge/vert/bleu, navigation par étapes, architecture interactive, progression locale, commandes personnalisées et compte rendu exportable.

## Contenu

- `index.html` : structure de l’interface.
- `style.css` : thème et adaptation aux petits écrans.
- `app.js` : huit étapes, commandes, architecture, notes et interactions.
- `.nojekyll` : publication statique directe sur GitHub Pages.

Aucun serveur applicatif, compte étudiant, dépendance à compiler ou clé API. Les machines virtuelles sont exécutées sur les ordinateurs des étudiants, pas dans la page Web.

## Publication sur GitHub Pages — une seule procédure

1. Connectez-vous à votre compte GitHub et créez un dépôt **public** nommé `cyberlab`.
2. Décompressez ce ZIP sur votre ordinateur.
3. Dans le dépôt, cliquez **Add file → Upload files** et ajoutez `index.html`, `style.css`, `app.js` et ce README **à la racine**, pas dans un sous-dossier. Validez avec **Commit changes** sur `main`.
4. Ajoutez aussi `.nojekyll`. S’il est masqué par votre système, utilisez **Add file → Create new file**, saisissez `.nojekyll` comme nom et validez un fichier vide.
5. Ouvrez **Settings → Pages → Build and deployment**.
6. Pour **Source**, choisissez **Deploy from a branch**.
7. Choisissez la branche **main**, le dossier **/ (root)** et cliquez **Save**.
8. Attendez que le déploiement `pages build and deployment` réussisse dans **Actions**.
9. Dans **Settings → Pages**, copiez l’URL publiée : `https://VOTRE-COMPTE.github.io/cyberlab/`.
10. Ouvrez cette adresse dans une fenêtre privée pour vérifier l’accès étudiant, puis partagez-la via l’ENT ou un QR code.

La source et le site sont publics avec cette procédure : n’ajoutez aucun mot de passe personnel, copie étudiante ou information confidentielle au dépôt. Les identifiants Kali et Metasploitable indiqués dans le cours sont les identifiants publics des images d’entraînement.

Référence : https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site

## Modifier le cours après publication

1. Ouvrez `app.js` sur GitHub et cliquez sur l’icône de modification.
2. Modifiez le texte dans le tableau `steps` ; conservez les délimiteurs JavaScript et les balises HTML.
3. Validez avec **Commit changes**.
4. Attendez la réussite du nouveau déploiement.
5. Demandez aux étudiants d’actualiser la page, au besoin avec `Ctrl + F5`.

La publication automatique met à jour le cours ; elle ne collecte pas les résultats. Les notes et coches sont enregistrées dans `localStorage` sur chaque navigateur. Les étudiants exportent leur compte rendu en Markdown et déposent leurs pièces sur le canal que vous désignez.

Pour une autre séance, dupliquez le projet et changez la clé `cyberlab-session1-v1` afin de ne pas réutiliser la progression de cette séance. Pour changer uniquement les couleurs, modifiez les variables `:root` de `style.css`.

## Déroulé pédagogique fixé

Prérequis du guide : ordinateur Windows, macOS ou Linux ; **8 Go de RAM minimum, 16 Go recommandés** ; **50 Go libres minimum, 100 Go recommandés** ; processeur relativement récent (2015 ou après comme repère), compatible avec la virtualisation.

Avec 8 Go, les deux VM peuvent être plus lentes : commencer par installer Kali, puis ajouter Metasploitable et fermer les applications inutiles sur le poste hôte. Les étapes détaillées restent illustrées pour Windows. Les images choisies nécessitent un processeur Intel/AMD x86 : prévoir un poste compatible pour les étudiants sur ARM/Apple Silicon.

Téléchargements avant le créneau : VirtualBox, image VirtualBox Kali amd64 `.7z`, Metasploitable 2 `.zip`.

Séance estimée à 3 h, après préparation :

1. Installer VirtualBox — 15 min.
2. Créer le Réseau NAT — 20 min.
3. Ajouter Kali — 30 min.
4. Préparer Metasploitable — 25 min.
5. Vérifier les communications — 25 min.
6. Inventorier les services et capturer ICMP — 40 min.
7. Finaliser les preuves et instantanés — 25 min.

Le premier écran présente les prérequis ; le parcours comporte donc huit écrans au total.

## Architecture imposée

- Réseau : **CyberLab**, mode **Réseau NAT / NAT Network**, IPv4 **10.10.10.0/24**.
- DHCP activé, IPv6 désactivé, aucune redirection de port.
- Une seule carte par VM, attachée à CyberLab, câble branché.
- Kali : 2 vCPU, 4096 Mo, disque fourni dans l’image.
- Metasploitable 2 : Ubuntu 32 bits, BIOS, 1 vCPU, 512 Mo, disque VMDK fourni, carte PCnet-FAST III.
- Les IP sont relevées dans les VM et saisies dans le guide ; aucune IP de VM n’est imposée statiquement.
- Accès Internet et communication entre VM via Réseau NAT. Aucun mode pont.

Le NAT simple par VM ne répond pas à ce besoin d’échanges entre VM. Le Réseau NAT ne constitue pas une isolation complète : il autorise des connexions sortantes vers Internet et potentiellement vers le LAN. Les étudiants ne scannent que l’adresse de leur Metasploitable. Tester la compatibilité du réseau du campus et tout éventuel proxy avant le cours.

## Livrables étudiants

Compte rendu Markdown, captures réseau/connectivité/instantanés, `services.txt` et `ping.pcapng`. La plateforme n’exécute pas de commandes et ne vérifie pas les VM. Les coches sont déclaratives.

## Sources et attribution

Adaptation pédagogique originale du scénario fourni : https://mycybersecuritypath.com/labs/home-lab-setup/

La topologie diffère du guide initial : Réseau NAT avec accès sortant, à la demande de l’enseignante. Documentation technique consultée :

- https://docs.oracle.com/en/virtualization/virtualbox/7.2/user/networkingdetails.html
- https://www.kali.org/docs/virtualization/import-premade-virtualbox/
- https://docs.rapid7.com/metasploit/metasploitable-2/
- https://nmap.org/book/man.html
- https://www.wireshark.org/docs/wsug_html_chunked/

## Vérification et limites

Syntaxe JavaScript et logique de navigation, progression, validation des IP et export vérifiées lors de la création. Pas de validation visuelle dans un navigateur disponible dans l’environnement de création ; le montage VirtualBox n’a pas été exécuté ici. Avant la séance, réaliser le parcours sur un poste représentatif et vérifier l’affichage sur les navigateurs étudiants.

Le site fonctionne sans installation en ouvrant `index.html` ; la persistance de stockage d’une page `file://` dépend du navigateur. GitHub Pages est préférable. Les polices Google Fonts sont facultatives : une police système prend le relais si elles ne sont pas disponibles.
