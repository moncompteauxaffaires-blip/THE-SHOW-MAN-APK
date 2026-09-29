# THE-SHOW-MAN

🎭 JEU DE SPECTACLE IA
THE SHOW MAN
🎤🕴️
👀👀👀
Lis l’histoire puis lance la prestation !
Un robot entre dans un café et demande : « Vous avez du Wi-Fi ? » Le serveur répond : « Oui. » Le robot dit : « Parfait, alors je vais prendre un mot de passe. »
NOTE DU PUBLIC
— / 10
0 spectateur

# Architecture technique

Frontend jeu : Godot 4.
Backend : API REST/HTTPS.
Auth : compte email/social.
Données : profil, progression, scores, inventaire.
IA : génération de blagues/histoires avec prompts contrôlés.
Modération : filtre avant affichage/publication.
TTS : service vocal optionnel.
Leaderboard : score quotidien, hebdomadaire et saison.

Boucle : Choisir thème -> Générer -> Répéter -> Jouer -> Réaction public -> Note 1-10 -> Récompense -> Déblocage -> Classement.

Publications — THE SHOW MAN

## TikTok / Instagram Reels
🎤 THE SHOW MAN arrive !
Tu montes sur scène, une IA te prépare une histoire, tu la joues… et le public te note de 1 à 10 😂

Tu penses pouvoir atteindre 10/10 ?
#TheShowMan #AIGame #ComedyGame #Gaming #IA

## YouTube
Titre : THE SHOW MAN — Le jeu où l'IA écrit tes blagues et le public te note !

Description : Monte sur scène, choisis ton style, fais rire ton public et tente d'obtenir la meilleure note. Développe ton personnage, gagne des récompenses et grimpe dans les classements.

## Facebook / X
🎤 THE SHOW MAN — un nouveau jeu de comédie alimenté par l'IA.
Une histoire. Une scène. Un public. Une note de 1 à 10.
Qui réussira le 10/10 ?

THE SHOW MAN

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







