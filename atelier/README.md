# Cap Web

Ce README est à écrire par votre binôme au round 2, en 3 parties : à quoi sert Cap Web, comment l'installer et le lancer, et les 3 modules de `public/js` avec le rôle de chacun. La fiche est [documenter le projet](../defis/R2-ce-que-voit-l-agent.md).

En attendant, dans ce dossier : `npm start` lance Cap Web sur http://127.0.0.1:3000 (Ctrl+C l'arrête), et `npm test` lance les tests. On ne modifie jamais `tests/contrat/`, `browser/contrat.spec.js` ni `cahier-personnel.json`.



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