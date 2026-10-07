# Carnet de bord · J2

Binôme : b17 · Membres : Sami Hamizi & Vincent Lebel · Nos réglages sont dans `atelier/cahier-personnel.json` : ne les recopiez pas ici.

## Mon positionnement (chacun de vous deux)

Pour chaque notion, chacun écrit « à l'aise » ou « à renforcer ». Ce n'est ni évalué ni classé : c'est votre point de départ pour le bilan individuel de fin de module.

| Notion | Membre 1 : Vincent | Membre 2 : Sami |
|---|---|---|
| Structure HTML | à l'aise | |
| CSS et responsive | à l'aise | |
| JavaScript | à l'aise | |
| DOM et événements | à l'aise | |
| Git | à l'aise | |
| Tests | à l'aise | |

Chacun, en une phrase, son objectif personnel pour J2 et J3.

Membre 1 :

Membre 2 :

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

Ma prédiction : si j'ajoute un troisième mot dans `MOTS`, « aide » répondra …

### Étape 3 · Lighthouse (accessibilité)

- Score de départ : 100
- Score sans le `label` du champ : 93
- Alerte : « Form elements do not have associated labels »
- Essai au clavier : Tab jusqu'au champ, message tapé, Entrée : le message part.