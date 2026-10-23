---
title: "Notifications LFG Alarm"
description: "Faire sonner une vraie alarme sur votre téléphone, et sur celui de tous ceux qui l'ont rejointe, quand Apprise envoie une notification."
sidebar:
  label: "LFG Alarm"

source: https://lfg.gm

schemas:
  - lfg

sample_urls:
  - lfg://{token}
  - https://api.lfg.gm/horn/{token}
---

<!-- SPONSORS:BANNER -->
<!-- SERVICE:DETAILS -->

## Configuration du compte

[LFG Alarm](https://lfg.gm) est un réveil social pour iPhone et Android. Une alarme Anything possède un lien privé, et appeler ce lien fait sonner l'alarme sur chaque téléphone qui l'a rejointe. Sur Android, elle sonne en plein écran. Sur iPhone, elle arrive sous forme d'alerte urgente (time-sensitive) avec le son de l'alarme.

LFG Alarm n'affiche ni le titre ni le corps de la notification. L'alarme sonne avec le nom, le bouton et la note que son propriétaire lui a donnés dans l'application. Nommez-la donc d'après la situation qu'elle couvre, par exemple « Site web en panne ».

1. Installez LFG Alarm sur votre téléphone ([Google Play](https://play.google.com/store/apps/details?id=gm.lfg.app) ou l'[App Store](https://apps.apple.com/app/id6821089085)) et connectez-vous.
2. Créez une alarme Anything et copiez son lien privé. Il ressemble à `https://api.lfg.gm/horn/abcdefghijklmnopqrstuvwxyz012345`. Les 32 caractères à la fin constituent votre jeton. Les alarmes Anything nécessitent un abonnement payant (voir [lfg.gm](https://lfg.gm)).
3. Toute personne qui possède le lien peut faire sonner l'alarme, gardez-le donc privé.

Vous pouvez aussi coller le lien tel quel dans Apprise.

Après avoir sonné, une alarme attend la fin d'un court délai de récupération avant de pouvoir sonner à nouveau. Une rafale de notifications ne produit donc qu'une seule sonnerie. Une notification envoyée pendant ce délai, ou pendant que l'alarme est désactivée, est signalée comme non distribuée.

## Syntaxe

La syntaxe valide est la suivante :

- `lfg://{token}`
- `https://api.lfg.gm/horn/{token}`

## Détails des paramètres

| Variable | Requis | Description                                                                                                                               |
| -------- | ------ | ----------------------------------------------------------------------------------------------------------------------------------------- |
| token    | Oui    | Les 32 caractères à la fin du lien privé de votre alarme. Gardez-le secret, car toute personne qui le possède peut faire sonner l'alarme. |

<!-- TEMPLATE:SERVICE-PARAMS -->

## Exemples

Faire sonner une alarme :

```bash
apprise -vv -b "Sonner" lfg://abcdefghijklmnopqrstuvwxyz012345
```

Faire sonner une alarme en utilisant le lien tel quel :

```bash
apprise -vv -b "Sonner" https://api.lfg.gm/horn/abcdefghijklmnopqrstuvwxyz012345
```
