---
name: Pilalheur
description: Un réveil Android qui sonne plus tôt quand le matin le mérite — givre, verglas ou bouchons sur le trajet.
tags: [Android, App mobile, Réveil, Météo, Trafic]
links:
  - label: Télécharger l'APK
    url: https://github.com/The-Ston/Pilalheur-releases/releases/latest
  - label: Mode d'emploi
    url: https://github.com/The-Ston/Pilalheur-releases#installer
cover: cover.png
coverAlt: L'icône de Pilalheur, flocon de neige au cadran d'horloge, à côté de deux écrans de l'app — l'accueil annonçant un réveil 13 min plus tôt, et l'écran du réveil qui sonne.
icon: icon.png
screenshots:
  - src: screenshots/accueil.png
    alt: Écran d'accueil avec l'heure du prochain réveil
    caption: Le prochain réveil, avancé de 13 min à cause des bouchons
  - src: screenshots/composition.png
    alt: Détail du calcul de l'heure de réveil
    caption: Préparation, équipement, trajet, marge et bouchons — chaque minute est justifiée
  - src: screenshots/reveil.png
    alt: Écran du réveil qui sonne
    caption: Au réveil, la raison de l'avance et l'heure de départ
  - src: screenshots/trajet.png
    alt: Carte de l'itinéraire domicile-travail
    caption: L'itinéraire du matin, mesuré avec le trafic
  - src: screenshots/transports.png
    alt: Liste des moyens de transport classés
    caption: Les moyens de transport, par ordre de préférence
  - src: screenshots/options-moto.png
    alt: Options de la moto
    caption: Quand renoncer à la moto — pluie, verglas, froid
technologies: [Kotlin, Jetpack Compose, Material 3, Hilt, WorkManager, DataStore, OkHttp, kotlinx.serialization, MapLibre, Cloudflare Workers]
platforms: [Android]
status: En pause
---

Pilalheur est un réveil Android qui sonne **plus tôt quand le matin le mérite** :
givre à gratter sur le pare-brise, verglas sur la route, bouchons sur le trajet.
Les autres jours, il sonne à l'heure habituelle.

## Comment il décide

Vous indiquez l'heure à laquelle vous devez être au travail, ou une heure de
réveil fixe. L'application calcule à rebours la préparation, le temps de
s'équiper, le trajet et une marge de sécurité, puis ajoute ce que coûtent les
conditions du jour. Elle ne se contente pas d'avancer l'alarme : elle dit de
combien, et pourquoi.

- **Givre** — estimé à partir de la température, de la couverture nuageuse, du
  vent et du point de rosée. Le temps de grattage double si le givre est modéré,
  triple s'il est important.
- **Verglas** — pluie verglaçante, neige, ou froid humide.
- **Trafic** — la durée du trajet est mesurée avec le trafic réel, bouchons
  compris.
- **Moyen de transport** — vous classez les vôtres par préférence, et le premier
  que la météo autorise est retenu. Une moto peut être écartée s'il pleut, s'il
  y a du verglas ou s'il fait trop froid.

## Un réveil qui sonne quoi qu'il arrive

L'heure est recalculée la veille au soir, puis une seconde fois peu avant le
réveil. Si le réseau manque, l'application se rabat sur le dernier bulletin
connu avec une marge de sécurité : l'alarme sonne quand même.

## Sans compte

Aucune inscription ni clé à fournir. L'application est distribuée hors Play
Store et demande Android 8.0 ou plus récent. Interface en français, avec une
traduction anglaise complète.

Météo et qualité de l'air : Open-Meteo. Trafic et adresses : TomTom. Fond de
carte : OpenFreeMap et OpenStreetMap.

*Captures réalisées avec un trajet de démonstration, de Villefranche-sur-Saône
à la gare de Lyon Part-Dieu.*
