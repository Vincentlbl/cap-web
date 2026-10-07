# Bilan du binôme b17 : Vincent Lebel et Sami Hamizi

## Niveau de départ (mardi)

| Notion | Membre 1 : Vincent | Membre 2 : Sami |
|---|---|---|
| Structure HTML | à l'aise | à l'aise |
| CSS et responsive | à l'aise | à l'aise |
| JavaScript | à l'aise | à l'aise |
| DOM et événements | à l'aise | à l'aise |
| Git | à l'aise | à l'aise |
| Tests | à l'aise | à l'aise |

Chacun, en une phrase, son objectif personnel pour J2 et J3.


# Objectifs du binôme
Membre 1: Vincent : Solidifier mes acquis sur les tests et la revue de code, en m'assurant de bien comprendre chaque ligne que je fusionne.

Objectif prouvé par : `4c350bc` (route /api/conseil ajoutée avec son test), `235fefb` (test rouge devenu vert : `textContent` au lieu de `innerHTML`), et la relecture de la pull request #2 de Sami (commentaire « bravo » citant les deux variables de couleur du `:root`).

Membre 2: Sami : Renforcer ma rigueur dans la revue de code et m'assurer que chaque modification est validée par des tests et le lint avant d'être fusionnée.

Objectif prouvé par : `ceccb86` (feat: nouvelle couleur, dont la description annonce « npm test doit afficher fail 0 »), et son commentaire « bravo » sur la pull request #1 (arborescence), qui cite les fichiers de `public/js`. À renforcer : relire la pull request de l'autre avant de fusionner (la #2 a été fusionnée avant relecture).


## Deux acquis prouvés

1. Trouver la cause d'un test rouge et la corriger avec un commit `fix:` par défaut : `35bd5f5` (message d'espaces seuls), `137c73a` (espaces autour du message), `4d76b48` (repli distinct), `235fefb` (`textContent` au lieu de `innerHTML`).
2. Ajouter une route serveur avec son test, puis l'utiliser dans la page : `4c350bc` (`/api/conseil`), `88440f3` (Cap Web donne un conseil).

## Rappels sur la rigueur de la review

- On relit le diff de **l'autre** avant de fusionner : l'auteur ne valide pas son propre code. Aujourd'hui, une pull request a été approuvée et fusionnée sans relecture croisée ; on le fait dans l'ordre la prochaine fois.
- On vérifie dans cet ordre : ce qui est annoncé correspond à ce qui est fait, rien de dangereux (texte d'utilisateur en `textContent`, aucune clé), le code est lisible, les tests et le lint passent.
- Un commentaire de review commence par son type (*bravo*, *question*, *suggestion*, *problème*) et cite un fait précis (un fichier, une ligne, une valeur).
- On lance `npm run lint` **et** `npm test` avant chaque commit : les tests étaient verts alors que `app.js` était cassé par un ancien `fetch` resté dans le fichier (`67f3669`), seul le lint ou la page le montrait.
- On nomme les fichiers dans `git add --`, on vérifie le dossier courant et `git status --short` avant de commiter : un mauvais README a été commité par erreur (`ab003d2`) puis corrigé (`14c397f`).
- Un `commit` reste sur le poste : rien n'est partagé tant qu'on n'a pas fait `git push`.

## Deux points à renforcer

1. Relire un diff avec méthode (la checklist ci-dessus), avant de cliquer sur Merge.
2. Vérifier chaque modification dans la page ET avec le lint, pas seulement avec les tests.

## Objectif

Pouvoir expliquer chaque ligne que l'on fait fusionner, et refuser un changement en donnant une raison précise.