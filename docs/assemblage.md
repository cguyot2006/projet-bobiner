---
layout: default
nav_order: 6
title: Assemblage
has_children: true
---

# Assemblage du Debobiner

<div style="text-align: justify;">
Une fois toutes les pièces imprimées en 3D, nous avons rapidement réalisé qu'un assemblage dans le monde réel est bien plus complexe qu'une simulation sur Onshape. Entre les tolérances d'impression et les imprévus matériels, cette étape a été riche en enseignements.
</div>

---

## 1. Péripétie #1 : Le Stand et les Roulements Latéraux

<div style="display: flex; align-items: center; gap: 20px; flex-wrap: wrap;">
  <div style="flex: 1; min-width: 300px; text-align: justify;">
    Les parois principales du Stand Bobines représentent un défi logistique : chaque pièce nécessite 2h40 d'impression et impose un plateau large, disponible uniquement sur les Bambu Lab P1P du Makerspace. 
    <br><br>
    Lors de l'assemblage, nous avons découvert une erreur de modélisation : le diamètre des axes était légèrement trop important pour laisser passer les roulements à billes. Après avoir tenté de limer manuellement les axes sans succès, nous avons dû improviser une solution thermique.
    <br><br>
    En utilisant un fer à souder, nous avons chauffé la bague interne du roulement. Une fois la température suffisante atteinte, une légère pression a permis d'enfoncer le roulement dans le plastique ramolli. Cette technique "à chaud" nous a permis de sauver des pièces volumineuses et d'éviter un gaspillage important de filament.
  </div>
  <div style="flex: 1; min-width: 300px; text-align: center;">
    <img src="https://github.com/user-attachments/assets/34d5c3ba-704e-42d0-80a7-17bb18986302" alt="Ajustement thermique" style="width: 100%; border-radius: 8px; border: 1px solid #ddd;">
  </div>
</div>

{: .note }
> **À faire :** Il faudra prendre une photo de cette technique spécifique (fer à souder, marteau et pince) pour illustrer le processus de sauvetage des pièces.

---

### Résultat de la Péripétie #1

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

### Conclusion de la Péripétie #1

<div style="text-align: justify;">
Cette expérience nous a appris deux leçons fondamentales pour la suite de nos projets :
<br><br>
1. <u>Prototypage partiel :</u> Avant de lancer une impression de plusieurs heures, il est crucial d'imprimer uniquement la zone critique (un "sample" de l'axe par exemple) pour vérifier l'ajustement avec les pièces standards comme les roulements.
<br>
2. <u>Résilience technique :</u> Une erreur de dimension ne signifie pas forcément que la pièce doit finir à la poubelle. En utilisant les outils à notre disposition (fer à souder, usinage manuel), nous avons favorisé une approche <u>éco-responsable</u> en limitant la consommation de plastique inutile.
</div>

---
