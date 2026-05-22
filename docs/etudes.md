---
layout: default
nav_order: 4
title: Études et choix techniques
---

# De l'idée à la machine

Avant de débuter la conception assistée par ordinateur (CAO), notre équipe a mené une analyse du marché. L'objectif était d'analyser les solutions d'enrouleurs ("rewinder" ou "re-spooling") de filament déjà développées par les communites et dans l'industrie afin d'en extraire les meilleures pratiques.


*(Note : Vous pouvez insérer ici les images ou liens des modèles qui vous ont inspirés)*

---

## Retour de l'étude

En gardant a l'esprit les exigences du cahier des charges, nous avons identifié trois piliers techniques indispensables à la réussite du projet :

### 1. La synchronisation des moteurs (Contrôle de la tension)
> **Le constat :** Pour maintenir une tension constante sans étirer ni détendre le filament, l'utilisation d'un seul moteur est insuffisante. 
* **La solution retenue :** Intégration de deux moteurs fonctionnant en parfaite synchronisation. Le premier gère le déroulage de la bobine source (plusieurs kilos), tandis que le second gère l'enroulage de la bobine cible (1 kg).

### 2. Le capteur de tension
* **Le constat :** Les capteurs de tension dynamiques pour filament plastique fins n'existent pas de manière standardisée ou abordable sur le marché.
* **La solution retenue :** Concevoir et fabriquer notre propre capteur de tension mécanique (généralement basé sur un bras oscillant ou un système de "dancer" associé à un capteur d'angle ou une jauge de contrainte) pour envoyer une information en temps réel à notre boucle de rétroaction **PID**.

### 3. Le système de distribution (Guide-fil)
* **Le constat :** Sans guidage, le filament s'enroule de manière centré sur la bobine, provoquant des chevauchements et des blocages futurs lors de l'impression 3D.
* **La solution retenue :** Développement d'un mécanisme de guide-fil qui distribue le filament de manière rigoureuse et équitable, de droite à gauche, sur toute la largeur de la bobine réceptrice.

---

---
