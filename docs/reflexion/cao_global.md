---
layout: default
title: CAO
parent: Études et choix techniques
nav_order: 3
---

# Réflexion Conception CAO

<div style="text-align: justify;">
La phase de réflexion CAO a débuté par une analyse du marché des enrouleurs 3D. Notre objectif était de comparer différents design pour trouver le meilleur compromis entre portabilité, fiabilité du guidage et facilité d'assemblage.
</div>

---

## 1. Première approche : L'horizontale (Design classique)

<div style="text-align: justify;">
Notre première intention s'est portée sur un design horizontal et linéaire, une configuration standard très connue sur les plateformes de partage de modèles 3D. 
<br><br>
<b>Avantages de cette architecture :</b>
<br>
• <u>Modularité et volume utile :</u> L'alignement à plat offre un espace généreux pour intégrer et déplacer les capteurs (capteur de tension, encodeurs) sans contrainte d'encombrement.
<br>
• <u>Stabilité mécanique :</u> Le centre de gravité bas réduit les vibrations induites par le moteur en cours d'enroulement.
<br>
• <u>Maintenance simplifiée :</u> Tous les sous-ensembles (moteurs, trains d'engrenages) sont facilement accessibles pour l'ajustement ou le démontage.
<br><br>
<b>Inconvénients de cette architecture :</b>
<br>
• <u>Sensibilité aux variations de flèche :</u> La distance importante entre la bobine source et la bobine cible crée une longueur de fil libre. La tension mesurée en amont peut diverger de la tension réelle d'enroulement à cause du battement du filament.
<br>
• <u>Encombrement au sol important :</u> Ce design consomme une surface de travail (footprint) conséquente, ce qui va à l'encontre de notre cahier des charges d'intégration en atelier ou dans une armoire d'usine.
</div>

### Inspirations horizontales

<div style="display: flex; flex-wrap: wrap; justify-content: space-between; gap: 15px; margin-top: 15px;">
  <div style="flex: 1; min-width: 250px; text-align: center;">
    <a href="https://makerworld.com/en/models/16606-pastamatic-filament-spool-winder-for-bambu-x1c-p1p#profileId-26699" target="_blank">
      <img src="https://github.com/user-attachments/assets/3d987bc1-b9ff-4c42-8871-a77c162fa93b" alt="Pastamatic Winder" style="width: 100%; border-radius: 8px; border: 1px solid #ddd; transition: transform 0.2s;">
    </a>
    <p style="margin-top: 8px; font-size: 0.85em; font-style: italic;">Pastamatic Filament Spool Winder</p>
  </div>
  <div style="flex: 1; min-width: 250px; text-align: center;">
    <a href="https://cults3d.com/fr/mod%C3%A8le-3d/outil/bobinadora-automatica-carrete-filamento-1-75-mm?srsltid=AfmBOorj_ybxVMW-IY-E5uCGADRQXs9YaYiswXdo8rvQrW8KGXKbNef7" target="_blank">
      <img src="https://github.com/user-attachments/assets/11e287ad-20a8-4d32-86c0-9176d93fbf23" alt="Bobinadora Automatica" style="width: 100%; border-radius: 8px; border: 1px solid #ddd;">
    </a>
    <p style="margin-top: 8px; font-size: 0.85em; font-style: italic;">Bobinadora Automática Automatique</p>
  </div>
  <div style="flex: 1; min-width: 250px; text-align: center;">
    <a href="https://www.crealitycloud.com/fr/model-detail/filament-spool-winder-best?profileId=67b214015b7e4d6485b974a8" target="_blank">
      <img src="https://github.com/user-attachments/assets/10dbae22-f00e-4852-b54e-da5863f72d50" alt="Creality Cloud Winder" style="width: 100%; border-radius: 8px; border: 1px solid #ddd;">
    </a>
    <p style="margin-top: 8px; font-size: 0.85em; font-style: italic;">Filament Spool Winder (Creality Cloud)</p>
  </div>
</div>

### Premiers croquis

<div style="display: flex; flex-wrap: wrap; justify-content: space-between; gap: 15px; margin-top: 15px;">
  <div style="flex: 1; min-width: 280px; text-align: center;">
    <img src="https://github.com/user-attachments/assets/382e345f-af5f-4e37-88aa-b2e5cb172bcb" alt="Croquis horizontal 1" style="width: 100%; border-radius: 8px; border: 1px solid #ddd;">
  </div>
  <div style="flex: 1; min-width: 280px; text-align: center;">
    <img src="https://github.com/user-attachments/assets/efff9cc1-e6bc-4633-840d-3dbd254d22eb" alt="Croquis horizontal 2" style="width: 100%; border-radius: 8px; border: 1px solid #ddd;">
  </div>
</div>

---

## 2. Design retenue : Le vertical 

<div style="text-align: justify;">
Pour répondre pleinement aux exigences de compacité, nous nous sommes dirigé vers un design vertical, positionnant les deux bobines l'une au-dessus de l'autre (étage inférieur pour la bobine cible, étage supérieur pour la bobine source).
<br><br>
<b>Avantages de cette architecture :</b>
<br>
• <u>Optimisation de l'empreinte au sol :</u> Le projet devient extrêmement compact et facilement transportable, maximisant l'utilisation de l'espace vertical disponible.
<br>
• <u>Guidage direct :</u> Le cheminement du fil est plus court et plus direct, réduisant les risques de vibrations parasites lors de la lecture de la tension.
<br><br>
<b>Inconvénients et contraintes associées :</b>
<br>
• <u>Densification mécanique :</u> La réduction du volume global nous impose une phase d'intégration CAO beaucoup plus rigoureuse. L'intégration du train d'engrenages, du moteur et du guide-fil doit être calculé au millimètre près pour éviter toute collision mécanique lors de l'assemblage.
</div>

### Inspirations et références (Verticales)

<div style="display: flex; flex-wrap: wrap; justify-content: space-between; gap: 15px; margin-top: 15px;">
  <div style="flex: 1; min-width: 280px; text-align: center;">
    <a href="https://www.amazon.fr/Eujgoov-Enrouleur-Filament-Dimprimante-%C3%A9lectrique/dp/B0GNTQ1TNF" target="_blank">
      <img src="https://github.com/user-attachments/assets/6de45b76-ba2b-4c21-ae8c-20131ca2803d" alt="Enrouleur Eujgoov" style="width: 100%; border-radius: 8px; border: 1px solid #ddd;">
    </a>
    <p style="margin-top: 8px; font-size: 0.85em; font-style: italic;">Enrouleur électrique Eujgoov</p>
  </div>
  <div style="flex: 1; min-width: 280px; text-align: center;">
    <a href="https://www.etsy.com/listing/1706943806/the-original-v-spooler-filament-winder?lang_mismatch=1" target="_blank">
      <img src="https://github.com/user-attachments/assets/fbe104b3-4776-4d86-8fda-fbaab05396ed" alt="The V-Spooler" style="width: 100%; border-radius: 8px; border: 1px solid #ddd;">
    </a>
    <p style="margin-top: 8px; font-size: 0.85em; font-style: italic;">The Original V-Spooler</p>
  </div>
</div>

### Premier tracé de l'architecture verticale

<div style="text-align: center; margin-top: 20px;">
  <img src="https://github.com/user-attachments/assets/b276a541-20cd-4181-b549-511e3a9abde6" alt="Premier dessin design vertical" style="max-width: 450px; width: 100%; border-radius: 8px; border: 1px solid #ddd;">
  <p style="margin-top: 8px; font-size: 0.85em; font-style: italic;">"Schéma châssis vertical"</p>
</div>

---
