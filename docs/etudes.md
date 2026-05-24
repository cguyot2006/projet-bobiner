---
layout: default
nav_order: 4
title: Études et choix techniques
---

# De l'idée à la machine

Avant de débuter la conception assistée par ordinateur (CAO), notre équipe a mené une analyse du marché. L'objectif était d'analyser les solutions d'enrouleurs ("rewinder" ou "re-spooling") de filament déjà développées par les communites et dans l'industrie afin d'en extraire les meilleures pratiques.


## Analyse du marché

L'étude des systèmes existants nous a permis de cartographier les architectures mécaniques récurrentes. Cliquez sur les images pour explorer nos sources d'inspiration :

<div style="display: flex; justify-content: space-between; align-items: flex-start; gap: 15px; margin-top: 20px;">
  
  <div style="flex: 1; text-align: center;">
    <a href="https://www.firgelli.fr/blogs/mechanisms/spool-winding-machine?srsltid=AfmBOop1c71301663T1KjvMkcobsRYWZ8Ml7dUmaxm11FXUkffIzeaoD" target="_blank">
      <img src="https://github.com/user-attachments/assets/5684eab9-1aa8-4a2b-aa09-c969e991920e" alt="Firgelli Spool" style="width: 100%; border-radius: 8px; border: 1px solid #ddd; aspect-ratio: 4/3; object-fit: cover;">
    </a>
    <p style="font-size: 0.85em; color: #666; margin-top: 10px;"><b>Système Firgelli</b><br>Étude du guide fil (de la rotation à la translation)</p>
  </div>

  <div style="flex: 1; text-align: center;">
    <a href="https://www.fer-plast.com/fr/produits/emballage/imprimantes-et-etiquetage/enrouleurs-et-dérouleurs-pour-bobines-detiquettes/rebobiner-rtr-detail?srsltid=AfmBOorn9pmhIZw2dOTRu1LkA-Q6eBvOfu8mOdHF3Se4XEPGS_fn9L6E&ct=1779642120338" target="_blank">
      <img src="https://github.com/user-attachments/assets/4274dddf-4036-4c06-b560-b708668bee5e" alt="Ferplast Winding" style="width: 100%; border-radius: 8px; border: 1px solid #ddd; aspect-ratio: 4/3; object-fit: cover;">
    </a>
    <p style="font-size: 0.85em; color: #666; margin-top: 10px;"><b>Solution Fer-Plast</b><br>Gestion du rebobinage d'étiquettes industrielles</p>
  </div>

  <div style="flex: 1; text-align: center;">
    <a href="https://www.printables.com/model/515427-awesome-filament-spool-rewinder-upgraded#preview.sZFeN" target="_blank">
      <img src="https://github.com/user-attachments/assets/4c473d85-58e7-4d9c-b0c8-ed36f38690bc" alt="Awesome Spool Rewinder" style="width: 100%; border-radius: 8px; border: 1px solid #ddd; aspect-ratio: 4/3; object-fit: cover;">
    </a>
    <p style="font-size: 0.85em; color: #666; margin-top: 10px;"><b>Awesome Rewinder</b><br>Inspiration pièce moteur-bobine</p>
  </div>

</div>


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
