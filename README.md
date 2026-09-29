# THE-SHOW-MAN

🎭 JEU DE SPECTACLE IA
THE SHOW MAN
🎤
# 🎤 THE SHOW MAN

Jeu vidéo de comédie utilisant l'intelligence artificielle.

## Fonctionnalités

- Spectacles générés par IA
- Thèmes humoristiques
- Réactions du public
- Note de 1 à 10
- XP
- Niveaux
- Pièces
- Boutique
- Costumes
- Scènes
- Classement

## Installation

Installer Node.js.

Puis :

npm install

Créer un fichier `.env` :

OPENAI_API_KEY=ta_cle_api
OPENAI_MODEL=gpt-5-mini

Puis lancer :

npm start

Le jeu sera disponible sur :

http://localhost:3000

## Structure

the-show-man/
│
├── package.json
├── server.js
├── .env
├── .env.example
├── README.md
│
└── public/
    └── index.html

## Important

La clé API ne doit jamais être placée
dans index.html ni publiée sur GitHub.
Jeu de comédie multiplateforme : le joueur incarne un artiste, reçoit des histoires générées par IA, les interprète devant un public virtuel et reçoit une note de 1 à 10.

## Tester maintenant
Ouvrir `web/index.html` dans un navigateur.

## Version moteur
Ouvrir le dossier `godot/` avec Godot 4.x puis lancer le projet.

## Important
Cette livraison est un prototype/MVP. La connexion à une véritable API IA, les comptes en ligne, les classements réels, les paiements et les publications sur les stores nécessitent un backend et les comptes développeur correspondants.

THE SHOW MAN — Roadmap multiplateforme

## MVP
- Personnage comédien
- Génération d'histoires (prototype local)
- Performance
- Réactions du public
- Note de 1 à 10
- Coins, niveaux, meilleur score

## V1
- Compte joueur
- Sauvegarde cloud
- IA réelle côté serveur (clé API jamais dans le jeu)
- Voix/TTS
- Personnalisation du personnage et de la scène
- Missions quotidiennes
- Classements
- Modération automatique du contenu IA

## V2
- Spectateurs en direct
- Défis entre joueurs
- Système de vote
- Tournois
- Boutique cosmétique
- Événements saisonniers

## Plateformes
- Web : prototype HTML immédiatement testable
- Windows/macOS/Linux : export Godot
- Android : export Godot + signature + publication Google Play
- iOS/iPadOS : export Godot/Xcode + compte Apple Developer
- Consoles : accès aux programmes développeurs et SDK officiels de chaque constructeur, puis certification.

## Architecture recommandée
Client Godot -> API backend -> service IA -> modération -> base de données.
Ne jamais mettre une clé d'API IA secrète dans le client.







