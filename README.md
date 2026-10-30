# Cockpit de Jules

Tableau de bord personnel : planning de cours (lu en direct dans Google Agenda) avec événements perso, tâches Lumivo / Tilo / général classées de « Pressant » à « Dans longtemps », tableau des charges (poids, Push, Pull) et courbes de progression.

Site : https://jules125447.github.io/cockpit/

## Installer l'app sur le téléphone

- **iPhone** : ouvre le site dans Safari, bouton Partager, puis « Sur l'écran d'accueil ».
- **Android** : ouvre le site dans Chrome, menu ⋮, puis « Installer l'application ».

L'app s'ouvre en plein écran, fonctionne hors ligne avec les dernières données, et se met à jour toute seule.

## Comment ça marche

- Une seule page (`index.html`), sans compilation. `manifest.webmanifest` et `sw.js` en font une app installable.
- Les données sont dans Supabase (table `cockpit_docs`). La clé publique du fichier ne donne accès à rien seule : chaque requête doit porter le code d'accès, vérifié par la base (règle RLS). Le code n'est pas dans ce dépôt.
- Le planning vient de la fonction Supabase `cockpit-calendar`, qui lit le Google Agenda à chaque ouverture.
