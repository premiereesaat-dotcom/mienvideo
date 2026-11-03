# Notre vidéothèque

Le site de la vidéothèque familiale : la liste de nos DVD et Blu-ray, l'endroit où ils sont rangés, et l'avis de chacun (Martha, Rémi, Danuta, Bernard, Stéphane, Lucie, Eva et Jeanne) sur cinq critères notés de 0 à 5 étoiles : plaisant, amusant, angoissant, émouvant et avis général.

Le site tient en deux fichiers :

- `index.html` : la page elle-même ;
- `films.json` : les données (films, emplacements, avis). La page le met à jour toute seule.

---

## Installation (à faire une seule fois, environ 15 minutes)

### 1. Créer le dépôt sur GitHub

1. Connectez-vous sur [github.com](https://github.com) (ou créez un compte gratuit).
2. En haut à droite, cliquez sur **+** puis **New repository**.
3. Nom du dépôt : `videotheque`. Laissez-le en **Public**. Cliquez sur **Create repository**.
4. Sur la page du dépôt, cliquez sur **uploading an existing file** (ou **Add file → Upload files**).
5. Glissez les trois fichiers `index.html`, `films.json` et `README.md`, puis cliquez sur **Commit changes**.

### 2. Mettre le site en ligne

1. Dans le dépôt, ouvrez **Settings**, puis **Pages** dans le menu de gauche.
2. Sous **Build and deployment**, choisissez **Deploy from a branch**, puis la branche **main** et le dossier **/ (root)**. Cliquez sur **Save**.
3. Après une ou deux minutes, le site est accessible à l'adresse :
   `https://VOTRE-PSEUDO.github.io/videotheque/`

À ce stade, tout le monde peut **consulter** la vidéothèque. Pour pouvoir **ajouter des films et donner son avis**, il faut les deux clés ci-dessous.

### 3. Créer le jeton GitHub (la clé pour enregistrer)

Le jeton permet à la page d'écrire dans `films.json`, et seulement dans ce dépôt.

1. Sur GitHub, cliquez sur votre photo en haut à droite, puis **Settings**.
2. Tout en bas du menu de gauche : **Developer settings**, puis **Personal access tokens → Fine-grained tokens**.
3. Cliquez sur **Generate new token**.
4. Remplissez :
   - **Token name** : `Vidéothèque` ;
   - **Expiration** : la durée de votre choix (par exemple 1 an) ;
   - **Repository access** : **Only select repositories**, puis choisissez `videotheque` ;
   - **Permissions → Repository permissions → Contents** : **Read and write**.
5. Cliquez sur **Generate token** et **copiez le jeton tout de suite** (il commence par `github_pat_`). GitHub ne le montre qu'une fois.

### 4. Créer la clé TMDB (pour les fiches automatiques)

TMDB (The Movie Database) fournit gratuitement les synopsis en français, les affiches et les notes des spectateurs.

1. Créez un compte gratuit sur [themoviedb.org](https://www.themoviedb.org/signup).
2. Ouvrez votre profil, puis **Paramètres → API**.
3. Demandez une clé pour un usage **personnel / non commercial** et remplissez le court formulaire.
4. Copiez la **Clé d'API** (ou le « jeton d'accès en lecture », les deux fonctionnent).

Sans clé TMDB, le site fonctionne quand même : il suffit de remplir les fiches à la main.

### 5. Brancher les clés sur le site

1. Ouvrez votre site, cliquez sur **⚙** (Réglages).
2. Le compte et le dépôt sont normalement déjà remplis. Collez le **jeton GitHub** et la **clé TMDB**.
3. Cliquez sur **Tester** : vous devez voir « connexion réussie » et « clé acceptée ».
4. Cliquez sur **Enregistrer les réglages**, puis choisissez votre prénom dans **Je suis**.

### 6. Inviter le reste de la famille

1. Dans **⚙ Réglages**, cliquez sur **Copier le code d'invitation**.
2. Envoyez ce code **en message privé** (SMS, WhatsApp, e-mail) avec l'adresse du site.
3. Chacun ouvre le site, clique sur **⚙**, colle le code dans **Rejoindre la vidéothèque**, puis choisit son prénom.

À faire une fois par appareil (téléphone, tablette, ordinateur).

---

## Utilisation

- **Ajouter un film** : bouton **+ Ajouter un film**, tapez le titre, choisissez le bon résultat. Indiquez le format (DVD, Blu-ray…) et, si vous voulez, l'emplacement.
- **Donner son avis** : ouvrez un film, choisissez votre prénom, touchez les étoiles, puis **Enregistrer l'avis**. Toucher à nouveau la même étoile efface la note ; le bouton « 0 » donne zéro étoile. On peut aussi noter pour quelqu'un d'autre (pour un enfant, par exemple) en choisissant son prénom.
- **Changer l'emplacement** : ouvrez le film, modifiez le champ **Emplacement**, puis **Enregistrer l'emplacement**. Les emplacements déjà utilisés sont proposés automatiquement.
- **Trouver un film pour ce soir** : triez par « Les plus amusants », « Les moins angoissants », « Préférés de la famille »… La case **À noter par moi** affiche les films sur lesquels vous n'avez pas encore donné votre avis.
- **Critiques** : chaque fiche a un lien vers la recherche AlloCiné du film.

---

## Bon à savoir

- **Le dépôt est public** : la liste des films, les avis et les prénoms sont visibles par toute personne qui connaît l'adresse du site. Les jetons, eux, restent sur vos appareils et ne sont jamais publiés.
- **Le code d'invitation est une clé de la maison** : il permet de modifier la vidéothèque. Ne le publiez pas. En cas de fuite, supprimez le jeton sur GitHub (Developer settings), créez-en un nouveau et renvoyez un code.
- **Quand le jeton expire**, le site affiche une erreur à l'enregistrement : créez un nouveau jeton (étape 3), collez-le dans les réglages et renvoyez un code d'invitation.
- **Plusieurs personnes en même temps** : aucun souci, chaque enregistrement relit d'abord la dernière version, rien n'est écrasé.
- **Délai** : les membres connectés voient les changements tout de suite ; en simple consultation, il faut parfois une minute ou deux.
- **Sauvegarde et historique** : chaque modification est enregistrée dans l'historique du dépôt (onglet **Commits** sur GitHub), avec qui a fait quoi. On peut retrouver n'importe quelle version précédente de `films.json`. Le bouton **Télécharger films.json** des réglages fait aussi une copie sur votre appareil.
- **Ajouter un membre de la famille** : sur GitHub, ouvrez `films.json`, cliquez sur le crayon, ajoutez le prénom dans la liste `"membres"` (entre guillemets, séparé par une virgule), puis **Commit changes**. Évitez de renommer un membre existant : ses avis sont rangés sous son prénom.

---

Synopsis, affiches et notes des spectateurs : [TMDB](https://www.themoviedb.org/). This product uses the TMDB API but is not endorsed or certified by TMDB.
