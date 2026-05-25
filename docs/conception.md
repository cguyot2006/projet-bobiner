---
layout: default
nav_order: 5
title: Conception CAO
---

# Conception CAO

Une fois notre vision du projet clarifiée, nous avons débuté la phase de modélisation 3D sur Onshape.

---

## La première pièce : "L'Attrape-Bobine"

L'Attrape-Bobine est l'élément mécanique qui assure la liaison entre l'axe du moteur et la bobine pour transmettre le mouvement de rotation. 

Pour concevoir cette pièce universelle, nous avons analysé deux types de bobines aux dimensions différentes :
* **La bobine cible :** Un modèle vide provenant du Makerspace (format 1kg).
* **La bobine source :** Le format plein fourni par un fournisseur de l'école (format industriel).

Le but: Concevoir une interface unique capable de s'adapter aux deux diamètres intérieurs afin d'équiper nos deux moteurs de manière standardisée.

### Modèles 3D Interactifs

<div style="display: flex; flex-wrap: wrap; justify-content: space-between; gap: 20px;">

  <div style="flex: 1; min-width: 300px; text-align: center;">
    <iframe height="450" width="100%" src="https://modelembedder.net/embed?did=a2ca14590071317756405ddb&wvm=v&wvmid=36db1a26917329635d174889&eid=ac5b7edd050a7108625beb73&elementType=PARTSTUDIO" frameborder="0" style="border: 1px solid #eee; border-radius: 8px;"></iframe>
    <p style="margin-top: 10px; font-weight: bold; color: #2c3e50;">Zoom sur la pièce : L'Attrape-Bobine (Part Studio)</p>
  </div>

  <div style="flex: 1; min-width: 300px; text-align: center;">
    <iframe height="450" width="100%" src="https://modelembedder.net/embed?did=a2ca14590071317756405ddb&wvm=v&wvmid=856be950d975c9576b279a8c&eid=a49029c09177bc4eebaac3f4&elementType=ASSEMBLY" frameborder="0" style="border: 1px solid #eee; border-radius: 8px;"></iframe>
    <p style="margin-top: 10px; font-weight: bold; color: #2c3e50;">Vue d'ensemble : Assemblage avec bobine et moteur</p>
  </div>
</div>
---

## La deuxième pièce : "Le Btand Bobines"

Cette pièce constitue le châssis principal du projet : c'est la structure porteuse sur laquelle tous les autres composants viennent s'assembler. 

Le stand est composé de deux parois latérales. Pour surmonter les limites de volume d'impression de nos machines, chaque paroi a été divisée en trois segments distincts. 
* Fixation verticale : Les parties supérieures sont solidarisées à la base via des inserts de 4 mm, garantissant la rigidité de l'ensemble.
* Système de rotation : Les parois sont reliées entre elles par des rouleaux transversaux. Ces derniers servent de support aux bobines, permettant une rotation fluide et sans friction excessive grâce des roulements à billes situé à l'intérieur.

### Double étage d'enroulage
La structure est optimisée pour exploiter la verticalité afin de gagner de la place dans l'armoire de l'usine :
1. **Partie inférieure :** Reçoit la bobine cible (1kg) qui sera entraînée par le moteur.
2. **Partie supérieure :** Supporte la bobine source (pleine), facilitant le déroulage vers l'étage inférieur.


### Modèles 3D Interactifs

<div style="display: flex; flex-wrap: wrap; justify-content: space-between; gap: 20px;">

  <div style="flex: 1; min-width: 300px; text-align: center;">
    <iframe height="450" width="100%" src="https://modelembedder.net/embed?did=a2ca14590071317756405ddb&wvm=v&wvmid=77c72214a6dd4a384f372649&eid=37382988493c4a7cacba8a10&elementType=ASSEMBLY" frameborder="0" style="border: 1px solid #eee; border-radius: 8px;"></iframe>
    <p style="margin-top: 10px; font-weight: bold; color: #2c3e50;">Assemblage du stand (Structure seule)</p>
  </div>

  <div style="flex: 1; min-width: 300px; text-align: center;">
    <iframe height="450" width="100%" src="https://modelembedder.net/embed?did=a2ca14590071317756405ddb&wvm=v&wvmid=606471c42e0f39a07bfc4b3a&eid=37382988493c4a7cacba8a10&elementType=ASSEMBLY" frameborder="0" style="border: 1px solid #eee; border-radius: 8px;"></iframe>
    <p style="margin-top: 10px; font-weight: bold; color: #2c3e50;">Assemblage du stand avec bobines</p>
  </div>

</div>


{: .note }
> **Transmission et Guidage :**
> On peut observer de nombreuses perforations sur la partie inférieure du châssis. Celles-ci ont été calculées avec précision pour accueillir le **train d'engrenages**.
> 
> Ce mécanisme est fondamental : il transforme la rotation du moteur principal en un mouvement linéaire pour actionner le **guide-fil**. Cela permet de distribuer le filament proprement sur toute la largeur de la bobine, évitant ainsi les chevauchements et les blocages lors de l'utilisation future.


---
