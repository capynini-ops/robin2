# Site de Robin Nini, avocat

Site statique en HTML, CSS et JavaScript, construit sur Bootstrap 5.3.8. Aucun outil de build : le dossier se dépose tel quel chez n'importe quel hébergeur de fichiers statiques.

## Pages

| Fichier | Contenu |
| --- | --- |
| `index.html` | Accueil : positionnement, domaines, vidéos, parcours, publications, premier contact, formulaire |
| `parcours.html` | Pratique, expérience, formation, repères, publications |
| `domaines.html` | Les trois domaines, chacun avec ses vidéos et articles (ancres `#donnees`, `#plateformes`, `#ia`) |
| `interventions.html` | Médiathèque filtrable et liste complète des publications |
| `intervention.html?v=<slug>` | Page d'une vidéo, construite à partir de `assets/js/data.js` |
| `mentions-legales.html`, `confidentialite.html`, `accessibilite.html` | Pages légales |
| `404.html` | Page d'erreur (à déclarer chez l'hébergeur) |

## Fichiers à connaître

- `assets/js/data.js` : coordonnées, domaines, vidéos et publications. C'est le seul fichier à modifier pour ajouter du contenu.
- `assets/js/site.js` : affichage des listes, filtres, lecteur vidéo chargé au clic, formulaire.
- `assets/css/site.css` : styles du site, par-dessus Bootstrap.
- `assets/vendor/bootstrap/` : Bootstrap 5.3.8 hébergé localement (pas de CDN).
- `assets/fonts/` : Source Serif 4, IBM Plex Sans et IBM Plex Mono, hébergées localement (licence OFL, aucun appel à Google Fonts).

## Ajouter une vidéo

Copier un bloc dans `window.VIDEOS` (fichier `assets/js/data.js`) et remplir :

- `slug` : identifiant unique pour l'adresse de la page (minuscules, tirets) ;
- `youtube` et/ou `dailymotion` : identifiant de la vidéo sur la plateforme ;
- `theme` : `donnees`, `plateformes` ou `ia` ;
- `subject` : contexte factuel du sujet ; `summary` : ce que Robin en retient ; `transcript` : transcription ;
- `date` (AAAA-MM-JJ) et `duration` (mm:ss) si connues ;
- `thumbnail` : chemin d'une image 16:9 locale, sinon une vignette typographique s'affiche.

La première vidéo du tableau est mise à la une sur l'accueil. Ajouter aussi l'adresse de la nouvelle page dans `sitemap.xml`.

## Photo

Déposer le portrait sous `assets/img/robin-nini.jpg` (format 4:5, 800 × 1000 px, moins de 150 Ko). Tant que le fichier est absent, les initiales s'affichent.

## Formulaire de contact

Sans serveur, le formulaire ouvre la messagerie du visiteur avec une demande pré-remplie (objet : sujet et situation). Pour un envoi direct sans passer par la messagerie, renseigner `formEndpoint` dans `data.js` avec l'adresse d'un service de formulaires (Formspree, Web3Forms ou un script maison). Le champ `_gotcha` sert de piège anti-spam.

## Sources des informations

| Information | Source |
| --- | --- |
| Poste, département, bio, formation (LL.M. 2018, Master 2 2016), classement Leading Associate, téléphone du standard | [The Legal 500](https://www.legal500.com/firms/13777-august-debouzy/c-france/lawyers/4280922-robin-nini) |
| Herbert Smith Freehills (2022-2024), Alain Bensoussan Avocats (2019-2022), CAPA HEDAC 2019, italien | Profil Malt de Robin (déclaratif) |
| Nomination comme avocat senior (décembre 2024) | [Le Monde du Droit](https://www.lemondedudroit.fr/nominations/96203-august-debouzy-promotion-seize-avocats.html) |
| Quatre articles Lexing de 2021 avec Céline Avignon | Pages des articles sur lexing.law |
| Trois articles August Debouzy (Russmedia, directive accessibilité, Clearview AI) | Recherche de mars 2026 ; le site d'August Debouzy bloque aujourd'hui la lecture automatique |
| Titres des vidéos B SMART | Métadonnées oEmbed de YouTube et Dailymotion |

## À faire avant la mise en ligne

- [ ] Faire relire tous les textes par Robin (rédigés à la première personne)
- [ ] Valider les trois domaines dominants et leurs intitulés
- [ ] Confirmer que Robin apparaît dans la vidéo « DSA, RGPD : lignes directrices de l'EDPB » (identifiée par recherche, pas encore confirmée)
- [ ] Compléter dates, durées, résumés et transcriptions des vidéos
- [ ] Ajouter le portrait
- [ ] Confirmer l'adresse du cabinet, l'e-mail de contact et le délai de réponse (`responseDelay`)
- [ ] Vérifier avec August Debouzy les conditions d'un site personnel et de la prise de contact directe
- [ ] Choisir le nom de domaine (il doit contenir le nom de Robin, RIN art. 10.5) et mettre à jour `SITE.url`, les balises `canonical`, `robots.txt` et `sitemap.xml`
- [ ] Compléter l'hébergeur dans `mentions-legales.html`
- [ ] Déclarer le site au conseil de l'Ordre et lui transmettre le nom de domaine et les termes utilisés pour les domaines dominants
- [ ] Ne pas employer « spécialiste », « spécialisé », « spécialité » ou « spécialisation » sans certificat de spécialisation
- [ ] Ne citer aucun client ou dossier sans son accord
- [ ] Réaliser l'audit RGAA et publier le taux de conformité dans `accessibilite.html`

## Mise en ligne

Déposer le contenu du dossier à la racine de l'hébergement (OVH, o2switch, Netlify, GitHub Pages…). Déclarer `404.html` comme page d'erreur. Le site fonctionne aussi en ouvrant `index.html` en local, à l'exception de la page `404.html` qui utilise des chemins absolus.
