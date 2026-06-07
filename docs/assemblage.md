---
layout: default
nav_order: 5
title: Assemblage
has_children: true
---

# L'Assemblage du Débobineur : Entre CAO et Réalité

<div style="text-align: justify; margin-bottom: 20px;">
Une fois toutes les pièces imprimées en 3D, nous avons rapidement réalisé qu'un assemblage dans le monde réel est bien plus complexe qu'une simulation sur Onshape. Entre les tolérances d'impression et les imprévus matériels, cette étape a été riche en enseignements.
</div>

---

## 1. Péripétie #1 : Le Stand et les Roulements Latéraux

<div style="text-align: justify; margin-bottom: 20px;">
Les parois principales du <u>Stand Bobines</u> représentent un défi logistique : chaque pièce nécessite 2h40 d'impression et impose un plateau large, disponible uniquement sur nos <b>Bambu Lab P1P</b>.
<br><br>
Lors de l'assemblage, nous avons découvert une erreur de modélisation : le diamètre des axes était légèrement trop important pour laisser passer les <u>roulements à billes</u>. Après avoir tenté de limer manuellement les axes sans succès, nous avons dû improviser une solution thermique.
<br><br>
En utilisant un <u>fer à souder</u>, nous avons chauffé la bague interne du roulement. Une fois la température suffisante atteinte, une légère pression a permis d'enfoncer le roulement dans le plastique ramolli. Cette technique "à chaud" nous a permis de sauver des pièces volumineuses et d'éviter un gaspillage important de filament.
</div>

<div style="display: flex; gap: 20px; flex-wrap: wrap; justify-content: center; margin-top: 20px;">

  <div style="flex: 1; min-width: 280px; max-width: 450px; text-align: center;">
    <img src="https://github.com/user-attachments/assets/97cac7f2-2fc5-4bf9-b2b9-d9592c877280" alt="Chauffement du roulement à bille avec fer à souder" style="width: 100%; border-radius: 8px; border: 1px solid #ddd; display: block; margin: 0 auto;">
    <p style="margin-top: 8px; font-style: italic; font-size: 0.9em; color: #555;">"Chauffement du roulement à bille avec fer à souder"</p>
  </div>

  <div style="flex: 1; min-width: 280px; max-width: 450px; text-align: center;">
    <img src="https://github.com/user-attachments/assets/34d5c3ba-704e-42d0-80a7-17bb18986302" alt="Ajustement thermique" style="width: 100%; border-radius: 8px; border: 1px solid #ddd; display: block; margin: 0 auto;">
    <p style="margin-top: 8px; font-size: 0.9em; color: #d9534f; line-height: 1.4;">
      <strong>Diamètre roulement à bille :</strong> 8 mm<br>
      <strong>Diamètre pied stand bobine :</strong> 9.2 mm
    </p>
  </div>

</div>

---

###  Résultat de la Péripétie #1

<div style="display: flex; flex-wrap: wrap; justify-content: space-between; gap: 15px; margin-top: 20px;">

  <div style="flex: 1; min-width: 250px; text-align: center;">
    <img src="https://github.com/user-attachments/assets/0c5a0024-e6d6-472d-b448-b48db86de27e" alt="Vue de côté" style="width: 100%; border-radius: 8px;">
    <p style="margin-top: 8px; font-style: italic;">"Vue de côté de la fixation des roulements à bille"</p>
  </div>

  <div style="flex: 1; min-width: 250px; text-align: center;">
    <img src="https://github.com/user-attachments/assets/61c74db2-d64c-42dd-8f1b-cb06a8ec6794" alt="Vue du haut" style="width: 100%; border-radius: 8px;">
    <p style="margin-top: 8px; font-style: italic;">"Vue du haut du roulement à bille fixé sur le stand bobine"</p>
  </div>

</div>

---

###  Conclusion de la Péripétie #1

<div style="text-align: justify;">
Cette expérience nous a appris deux leçons fondamentales pour la suite de nos projets :
<br><br>
1. <u>Prototypage partiel :</u> Avant de lancer une impression de plusieurs heures, il est crucial d'imprimer uniquement la zone critique (un "sample" de l'axe par exemple) pour vérifier l'ajustement avec les pièces standards comme les roulements.
<br>
2. <u>Résilience technique :</u> Une erreur de dimension ne signifie pas forcément que la pièce doit finir à la poubelle. En utilisant les outils à notre disposition (fer à souder, usinage manuel), nous avons favorisé une approche <u>éco-responsable</u> en limitant la consommation de plastique inutile.
</div>

## 2. Péripétie #2 : La chaîne de transmission par engrenages

<div style="text-align: justify;">
La première étape de la fabrication de notre chaîne cinématique consistait à manufacturer les pignons. Nous avions le choix entre deux procédés de fabrication : l'impression 3D FDM ou la découpe laser (sur panneaux d'acrylique ou de bois médium).
<br><br>
<b>L'expérimentation de la découpe laser :</b>
<br>
Nos premiers essais ont été réalisés en bois découpé au laser. Malheureusement, en raison des tolérances de saignée du laser (kerf) ou d'une légère erreur de cotation sur la CAO, le diamètre intérieur du logement s'est avéré trop important. L'ajustement étant glissant voire lâche, le roulement à billes ne tenait pas en place et sortait de son orbite. Ces pièces ont donc dû être écartées.
</div>

<br>

<div style="text-align: center;">
  <img src="https://github.com/user-attachments/assets/7e3c53c2-cb25-428c-9caa-615b4392a19a" alt="engrenage en bois" style="max-width: 500px; width: 100%; border-radius: 8px; border: 1px solid #ddd;">
  <p style="margin-top: 8px; font-style: italic; font-size: 0.9em;">"Prototype de pignon découpé au laser dans du bois"</p>
</div>

---

<div style="display: flex; align-items: center; gap: 20px; flex-wrap: wrap;">
  <div style="flex: 1; min-width: 300px; text-align: justify;">
    <b>Le passage à l'impression 3D et l'ajustement thermique :</b>
    <br>
    Nous nous sommes ensuite réorientés vers la fabrication additive. Cette fois, l'erreur s'est inversée : le diamètre intérieur du pignon imprimé était trop restreint pour permettre l'insertion mécanique du roulement. 
    <br><br>
    Pour résoudre cet ajustement serré sans réimprimer, nous avons réitéré la technique du <u>frettage thermique</u> : le roulement a été chauffé à l'aide d'une panne de fer à souder, puis inséré de force dans le logement en plastique de l'engrenage à l'aide d'un maillet. Le plastique s'est localement rétracté autour de la bague extérieure du roulement, assurant une parfaite cohésion.
  </div>
  <div style="flex: 1; min-width: 300px; text-align: center;">
    <img src="https://github.com/user-attachments/assets/09469058-6f14-46cc-8c41-5b39bc924786" alt="engrenange en impression 3D + roulement a bille" style="width: 100%; border-radius: 8px; border: 1px solid #ddd;">
    <p style="margin-top: 8px; font-style: italic; font-size: 0.9em;">"Intégration du roulement par insertion thermique dans le pignon imprimé 3D"</p>
  </div>
</div>

---

<div style="text-align: justify;">
<b>Le problème d'implantation sur le bâti :</b>
<br>
Une fois les roulements solidarisés avec leurs engrenages, nous avons tenté de monter ces sous-ensembles sur les axes cylindriques du <u>Stand Bobine</u>. Nouveau problème : les portées d'arbres modélisées en CAO étaient trop courtes et trop étroites. Les roulements ne parvenaient pas à se positionner correctement, bloquant complètement la rotation du train d'engrenages.
<br><br>
La solution idéale aurait été de corriger la CAO et de lancer une nouvelle impression du stand. Cependant, face aux restrictions de temps et aux délais de livraison des machines, nous avons appliqué une solution de secours directement sur le châssis existant. 
<br><br>
À l'aide du fer à souder, nous avons appliqué une source de chaleur sur l'extrémité de l'axe en plastique. En insérant le roulement en position fonctionnelle, nous avons délicatement écrasé et étalé le plastique ramolli de l'axe (opération s'apparentant à un <u>matage ou rivetage thermique</u>). Cela a permis de créer un épaulement de maintien improvisé pour empêcher le pignon de glisser hors de son axe.
<br><br>
<b>Limites du système lors des essais dynamiques :</b>
<br>
Bien que géométriquement fonctionnelle à basse vitesse, cette fixation artisanale a montré ses limites lors du premier test motorisé. L'accélération et le couple du moteur ont généré des efforts axiaux trop importants pour notre butée en plastique : l'un des engrenages s'est désolidarisé et a été projeté hors de son logement sous l'effet de la force centrifuge.
<br><br>
Nous avons tenté une réparation à l'aide d'un système vis-boulon traversant pour sécuriser l'axe de rotation. Malheureusement, l'encombrement du moteur pas-à-pas situé immédiatement derrière le pignon empêchait le passage physique de l'écrou, provoquant une interférence mécanique insoluble.
</div>

---

### Résultat de la Péripétie #2

<div style="text-align: center; display: flex; flex-direction: column; align-items: center; gap: 20px;">
  
  <img src="https://github.com/user-attachments/assets/7ba8ed69-9ec1-4c14-878f-2a8eb9425cf9" alt="Défaut d'alignement et de maintien" style="max-width: 500px; width: 100%; border-radius: 8px; border: 1px solid #ddd;">
  <p style="font-style: italic; font-size: 0.9em; margin-top: -10px;">"Détail de la zone d'interférence mécanique entre le pignon et la fixation du moteur"</p>

  <video src="https://github.com/user-attachments/assets/02851e6d-d33d-4a11-8a32-b1a3a989a75a" controls style="max-width: 600px; width: 100%; border-radius: 8px; border: 1px solid #ddd;"></video>
  <p style="font-style: italic; font-size: 0.9em; margin-top: -10px;">"Vidéo démonstrative du comportement dynamique et des vibrations de la transmission"</p>

</div>

---

### Conclusion de la Péripétie #2

<div style="text-align: justify;">
Cet échec technique met en exergue l'importance capitale des <u>chaînes de cotes</u> et du calcul des tolérances d'ajustement en ingénierie mécanique. Une modélisation approximative ou l'omission du jeu fonctionnel nécessaire au mouvement d'une pièce crée systématiquement des effets en cascade lors de l'assemblage final, forçant à l'improvisation de correctifs qui altèrent la durabilité du système. 
<br><br>
La règle d'or apprise lors de cette étape reste la rigueur absolue des phases de contrôle métrologique en amont de toute fabrication.
</div>

---

## 3. Péripétie #3 : Ajustement du bâti et frottements structurels

<div style="text-align: justify;">
Une fois la chaîne cinématique et la transmission par engrenages assemblées, nous avons procédé aux premiers essais dynamiques de rotation. La phase initiale à vide (sans charge mécanique) s'est déroulée avec succès, validant le comportement nominal des moteurs pas-à-pas. 
<br><br>
<b>La confrontation avec les bobines réelles :</b>
<br>
Les difficultés ont surgi lors de l'intégration des consommables nécessaires au test fonctionnel de débobinage/rembobinage. Pour ce faire, nous avons équipé l'étage inférieur d'une bobine vide provenant du Makerspace et l'étage supérieur d'une bobine de PLA pleine issue de l'usine. 
<br><br>
Si la bobine inférieure s'est insérée parfaitement dans son logement sans aucune contrainte mécanique, la bobine supérieure, en configuration de charge maximale, entrait en interférence physique directe avec les rouleaux de guidage latéraux. Ce contact indésirable a généré un <u>couple résistant par frottement</u> extrêmement élevé, suffisant pour provoquer la surcharge et le blocage complet du moteur.
<br><br>
<b>Arbitrage technique et résolution :</b>
<br>
Deux alternatives s'offraient à nous pour éliminer cette friction structurelle :
<br>
1. Modifier la CAO et réimprimer de nouveaux rouleaux de guidage optimisés, ce qui imposait un démontage complet et risqué du <i>Stand Bobine</i> (opération complexe compte tenu des fixations thermiques précédentes).
<br>
2. Procéder à une rectification rapide et locale directement sur la matière.
<br><br>
Fidèles à notre démarche de résilience sur le terrain, nous avons opté pour la seconde solution en exploitant à nouveau l'apport thermique du <u>fer à souder</u>. En utilisant la panne chaude du fer comme outil de pelage, nous avons réalisé une <u>ablation thermique localisée</u> du plastique excédentaire sur les parois des rouleaux. Cette modification géométrique a permis de redonner le jeu fonctionnel nécessaire au débattement de la bobine supérieure, libérant totalement sa rotation.
</div>

---

###  Résultat de la Péripétie #3 : Rectification thermique des rouleaux

<div style="display: flex; flex-wrap: wrap; justify-content: space-between; gap: 15px; margin-top: 20px;">

  <div style="flex: 1; min-width: 200px; text-align: center;">
    <img src="https://github.com/user-attachments/assets/5cd76f45-97a4-4a9b-949e-d570bbce3ef1" alt="Avant rectification" style="width: 100%; border-radius: 8px; border: 1px solid #ddd;">
    <p style="margin-top: 8px; font-weight: bold; color: #2c3e50;">1. Avant</p>
    <p style="font-size: 0.85em; font-style: italic; margin-top: -5px;">Zone de friction et d'interférence mécanique avec la bobine.</p>
  </div>

  <div style="flex: 1; min-width: 200px; text-align: center;">
    <img src="https://github.com/user-attachments/assets/96f1665b-5819-4b3d-99c8-4b2bceddfbc0" alt="Pendant rectification" style="width: 100%; border-radius: 8px; border: 1px solid #ddd;">
    <p style="margin-top: 8px; font-weight: bold; color: #2c3e50;">2. Pendant</p>
    <p style="font-size: 0.85em; font-style: italic; margin-top: -5px;">Usinage par ablation thermique au fer à souder pour libérer du jeu.</p>
  </div>

  <div style="flex: 1; min-width: 200px; text-align: center;">
    <img src="https://github.com/user-attachments/assets/734ee530-587a-42d3-89f5-9119be78919e" alt="Après rectification" style="width: 100%; border-radius: 8px; border: 1px solid #ddd;">
    <p style="margin-top: 8px; font-weight: bold; color: #2c3e50;">3. Après</p>
    <p style="font-size: 0.85em; font-style: italic; margin-top: -5px;">Résultat final : espace suffisant pour une rotation fluide et sans contact.</p>
  </div>

</div>

---

###  Conclusion de la Péripétie #3

<div style="text-align: justify;">
Cette troisième anomalie confirme une règle fondamentale de la conception industrielle : la nécessité absolue de prendre en compte la **variabilité dimensionnelle des composants tiers**. Bien que standardisées en apparence, les dimensions extérieures des bobines du commerce (largeur des flancs, épaisseur des rebords) varient sensiblement d'un fabricant à l'autre. 
<br><br>
Une modélisation CAO rigoureuse ne doit pas seulement s'appuyer sur un échantillon unique, mais doit intégrer des <u>cotes maximales enveloppes</u> et des marges de sécurité géométriques suffisantes (jeux fonctionnels) pour garantir l'interopérabilité totale du système, quelles que soient les tolérances des pièces intégrées.
</div>

---









---
