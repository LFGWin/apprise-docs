---
title: "LFG Alarm Notifications"
description: "Ring a real alarm on your phone, and on everyone's who joined it, when Apprise sends a notification."
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

## Account Setup

[LFG Alarm](https://lfg.gm) is a social alarm clock for iPhone and Android. An Anything alarm has a private link, and calling it rings the alarm on every phone that joined it: a real alarm sound, not a quiet notification. On Android it rings full screen; on iPhone it arrives as a time-sensitive alert with the alarm's sound.

LFG Alarm does not show the notification's title or body. The alarm rings with the name, button and note its owner gave it in the app, so name it for the moment it covers, for example "Website is down".

1. Install LFG Alarm on your phone ([Google Play](https://play.google.com/store/apps/details?id=gm.lfg.app) or the [App Store](https://apps.apple.com/app/id6821089085)) and sign in.
2. Make an Anything alarm and copy its private link. It looks like `https://api.lfg.gm/horn/abcdefghijklmnopqrstuvwxyz012345`. The 32 characters at the end are your token. Anything alarms need a paid plan; see [lfg.gm](https://lfg.gm).
3. Anyone with the link can ring the alarm, so keep it private.

You can also paste the link into Apprise as-is.

After it rings, an alarm waits out a short cooldown before it can ring again, so a burst of notifications is one ring. A notification sent during the cooldown, or while the alarm is switched off, is reported as not delivered.

## Syntax

Valid syntax is as follows:

- `lfg://{token}`
- `https://api.lfg.gm/horn/{token}`

## Parameter Breakdown

| Variable | Required | Description                                                                                                         |
| -------- | -------- | ------------------------------------------------------------------------------------------------------------------- |
| token    | Yes      | The 32 characters at the end of your alarm's private link. Keep it secret; anyone with it can ring the alarm.       |

<!-- TEMPLATE:SERVICE-PARAMS -->

## Examples

Ring an alarm:

```bash
apprise -vv -b "Ring" lfg://abcdefghijklmnopqrstuvwxyz012345
```

Ring an alarm using the link as is:

```bash
apprise -vv -b "Ring" https://api.lfg.gm/horn/abcdefghijklmnopqrstuvwxyz012345
```
