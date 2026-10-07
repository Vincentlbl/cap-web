# Carnet de bord · J2

Binôme : b17 · Membres : Sami Hamizi & Vincent Lebel · Nos réglages sont dans `atelier/cahier-personnel.json` : ne les recopiez pas ici.

## Mon positionnement (chacun de vous deux)

Pour chaque notion, chacun écrit « à l'aise » ou « à renforcer ». Ce n'est ni évalué ni classé : c'est votre point de départ pour le bilan individuel de fin de module.

| Notion | Membre 1 : Vincent | Membre 2 : Sami |
|---|---|---|
| Structure HTML | à l'aise | à l'aise |
| CSS et responsive | à l'aise | à l'aise |
| JavaScript | à l'aise | à l'aise |
| DOM et événements | à l'aise | à l'aise |
| Git | à l'aise | à l'aise |
| Tests | à l'aise | à l'aise |

Chacun, en une phrase, son objectif personnel pour J2 et J3.

Membre 1 : Solidifier mes acquis sur les tests et la revue de code, en m'assurant de bien comprendre chaque ligne que je fusionne.

Membre 2 : Renforcer ma rigueur dans la revue de code et m'assurer que chaque modification est validée par des tests et le lint avant d'être fusionnée.

## R1 · Les tests automatisés

Les tests rouges du départ, et ce que vous en avez fait :

| Test rouge | Cause trouvée (une phrase) | Fichier | Message du commit `fix:` |
|---|---|---|---|
| Les tests de `validateMessage` (message d'espaces seuls, limite de 190) | Le test « message vide » se faisait avant le `trim()`, donc un message d'espaces seuls passait | brain.js | fix: un message d'espaces seuls est refusé |
| « ignore la casse et les espaces autour » et « reconnaît les deux mots du cahier personnel » | `replyTo` ne retirait pas les espaces autour du message : le `trim()` manquait | brain.js | fix: replyTo ignore les espaces autour du message |
| « répond à une phrase inconnue par un repli distinct » | Un message inconnu recevait la réponse de l'aide : la réponse `repli` n'existait pas | brain.js | fix: un message inconnu reçoit un repli distinct de l'aide |
| « view.js affiche du texte et ne décide pas des réponses » | `innerHTML` interprétait le message comme du HTML (faille XSS) ; remplacé par `textContent` | view.js | fix: view.js affiche le texte sans innerHTML |

Avec l'agent : ce qu'il a proposé et que vous avez refusé, et pourquoi.
Aucun agent utilisé pour R1 : corrections faites à la main avec test rouge puis vert à chaque étape.

Pour aller plus loin : le nom renommé par votre commit `refactor:`, et pourquoi le nouveau est plus clair.

## R2 · Documenter le projet

Vos trois documents sont dans `atelier` : `README.md`, `SPEC.md` et `AGENTS.md`. Rien à recopier ici.

README.md : écrit et commité (`14c397f`).

Pour aller plus loin, avec l'agent, les demandes du formateur :

| Demande | Ce qu'a fait l'agent | Votre décision | Règle d'`AGENTS.md` concernée (ou ajoutée) |
|---|---|---|---|
| 1 | | | |
| 2 | | | |
| 3 | | | |

## R3 · Premiers tests unitaires

| À remplir | Votre réponse |
|---|---|
| Fonction tirée | |
| Le rouge vu (message exact) | |
| Identifiant du commit `test:` | |
| Identifiant du commit `feat:` | |
| Casse volontaire : la ligne changée | |
| Casse volontaire : le test devenu rouge | |
| Pour aller plus loin : la deuxième fonction | |

Les critères C1 à C5 de votre fonction, recopiés de la fiche :

## R4 · La revue de code

| Patch | Accepté ou refusé | Fichier et ligne | Raison |
|---|---|---|---|
| 1 | | | |
| 2 | | | |
| 3 | | | |

Pour aller plus loin : le patch que vous avez corrigé, et ce que vous avez changé.

## Fin de journée

Chacun, une phrase : ce que vous savez faire ce soir et que vous ne saviez pas faire ce matin. Relisez votre positionnement : une notion est-elle passée de « à renforcer » à « à l'aise » ?

## J3

### Étape 1 · Le troisième mot

Ma prédiction : (non écrite avant l'essai).

Résultat : après l'ajout du mot `pion` et le calcul du nombre avec `${Object.keys(MOTS).length}`, « aide » annonce 3 mots (commit `364c889`).

### Étape 2 · Le compteur de caractères

Le compteur suit la frappe (`0 / 190`) et revient à 0 après l'envoi (commit `863812a`).

### Étape 3 · Lighthouse (accessibilité)

- Score de départ : 100
- Score sans le `label` du champ : 93
- Alerte : « Form elements do not have associated labels »
- Essai au clavier : Tab jusqu'au champ, message tapé, Entrée : le message part.
- Commit : `af122a9`

### Étape 4 · La version mobile

À 375 px de large, le bouton Envoyer occupe toute la largeur ; rien ne change sur grand écran (commit `707fd39`).

### Étape 5 · Plan B : la version, même en cas de panne

`afficherVersion()` en `async/await` avec `try/catch` : « version dev » s'affiche, et « version indisponible » avec un mauvais chemin (commit `67f3669`). Ce commit avait laissé l'ancien `fetch` dans `app.js` : la page était cassée alors que les tests étaient verts. Corrigé dans `88440f3`.

### Étape 6 · La route /api/conseil

Route ajoutée dans `server/app.js`, avec son test `tests/conseil.test.js` (commit `4c350bc`).

### Étape 7 · Cap Web donne un conseil

Écrire « conseil » affiche un conseil ; avec le serveur arrêté, le message « Le serveur ne répond pas : conseil indisponible. » s'affiche, sans écran blanc (commit `88440f3`).

### Étape 8 · Le projet sur GitHub, à deux

Dépôt privé `cap-web` créé par Vincent, historique envoyé avec `git push`, Sami invité comme collaborateur.

### Étapes 9 et 10 · Branches et pull requests

- Pull request #1 de Vincent (`docs/arborescence`, commit `ee42f89`), fusionnée (`eb0c988`).
- Pull request #2 de Sami (`feat/couleur`, commit `ceccb86`), fusionnée (`3ed211d`) : Vincent l'a relue (commentaire « bravo », deux variables de couleur du `:root` changées).
- Sami a fusionné sa pull request avant la relecture croisée.

### Étape 11 · Les quatre attaques, puis le README

1. Serveur arrêté, puis « conseil » : message clair, pas d'écran blanc.
2. Message trop long : le champ s'arrête à `190 / 190` ; `validateMessage` refuse aussi 191 caractères.
3. `<b>test</b>` s'affiche tel quel, chevrons compris.
4. À 375 px, tout reste lisible.

README final dans `atelier` (commit `14c397f`). Incident : le README du formateur avait été commité par erreur (`ab003d2`), puis retiré du dépôt.

### Étape 12 · Le bilan

Bilan écrit dans `bilan/Vincent.md`.