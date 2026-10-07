# Cap Web

Cap Web est un assistant fictif pour apprendre le web : il répond avec des règles écrites à la main, ce n'est pas une IA réelle.
On lui écrit un message dans la page ; il répond à « salut », « aide », « test », à trois mots à nous (ponton, lanterne, pion), et à « conseil », qui demande un conseil au serveur.
Les messages sont validés (non vides, 190 caractères au maximum) et la conversation est gardée dans le navigateur.

## Installer, lancer, tester

Il faut Node 24.20 ou plus (`node --version`). Dans le dossier `atelier` :

```
npm ci
```

Les réglages du binôme (limite, mots) sont déjà dans `cahier-personnel.json` : rien à créer ni à copier.

```
npm start        lance Cap Web sur http://127.0.0.1:3000 (Ctrl+C l'arrête)
npm test         lance les tests
npm run lint     vérifie le style du code
```
npm start        lance Cap Web sur http://127.0.0.1:3000 (Ctrl+C l'arrête)
npm test         lance les tests
npm run lint     vérifie le style du code
```

## Les 3 modules de `public/js`

- `brain.js` : valide les messages et choisit les réponses ; il ne touche jamais à la page.
- `view.js` : affiche les messages dans la page, avec `textContent` (jamais de HTML venu de l'utilisateur).
- `app.js` : relie le formulaire, l'historique, le compteur et la version ; il appelle `brain.js` et `view.js`.

## La route /api/conseil

Le serveur répond à `GET /api/conseil` par un JSON `{ "conseil": "..." }`, tiré au hasard parmi trois conseils. Dans la page, écrire « conseil » affiche ce conseil ; si le serveur est arrêté, Cap Web affiche un message d'erreur clair.

## Arborescence du projet

```
atelier/
├── public/            la page, servie au navigateur
│   ├── index.html     structure de la page
│   ├── styles.css     mise en forme
│   └── js/
│       ├── app.js     relie la page, le cerveau et l'affichage
│       ├── brain.js   valide les messages et choisit les réponses
│       └── view.js    affiche les messages
├── server/            le serveur local
│   ├── app.js         les routes (dont /api/conseil)
│   └── start.js       démarrage du serveur
├── tests/             les tests automatiques
├── scripts/           outils du projet
├── browser/           tests dans le navigateur
└── cahier-personnel.json   nos réglages (limite, mots)
```

On ne modifie jamais `tests/contrat/`, `browser/contrat.spec.js` ni `cahier-personnel.json`.