---
layout: default
nav_order: 5
title: Conception CAO
---

# Conception CAO

<div style="text-align: justify;">
Une fois notre vision du projet clarifiée, nous avons débuté la phase de modélisation 3D sur Onshape.
</div>

---

## La première pièce : "L'Attrape-Bobine"

<div style="text-align: justify;">
L'Attrape-Bobine est l'élément mécanique qui assure la liaison entre l'axe du moteur et la bobine pour transmettre le mouvement de rotation. 
<br><br>
Pour concevoir cette pièce universelle, nous avons analysé deux types de bobines aux dimensions différentes :
</div>

* <u>La bobine cible :</u> Un modèle vide provenant du Makerspace (format 1kg).
* <u>La bobine source :</u> Le format plein fourni par un fournisseur de l'école (format industriel).

<div style="text-align: justify;">
Le but : Concevoir une interface unique capable de s'adapter aux deux diamètres intérieurs afin d'équiper nos deux moteurs de manière standardisée.
</div>

### Modèles 3D 

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

## La deuxième pièce : "Le Stand Bobines"

<div style="text-align: justify;">
Cette pièce constitue le châssis principal du projet : c'est la structure porteuse sur laquelle tous les autres composants viennent s'assembler. 
<br><br>
Le stand est composé de deux parois latérales. Pour surmonter les limites de volume d'impression de nos machines, chaque paroi a été divisée en trois segments distincts. 
</div>

* <u>Fixation verticale :</u> Les parties supérieures sont solidarisées à la base via des inserts de 4 mm, garantissant la rigidité de l'ensemble.
* <u>Système de rotation :</u> Les parois sont reliées entre elles par des rouleaux transversaux. Ces derniers servent de support aux bobines, permettant une rotation fluide et sans friction excessive grâce à des roulements à billes situés à l'intérieur.

### Double étage d'enroulage

<div style="text-align: justify;">
La structure est optimisée pour exploiter la verticalité afin de gagner de la place dans l'armoire de l'usine :
</div>

1. <u>Partie inférieure :</u> Reçoit la bobine cible (1kg) qui sera entraînée par le moteur.
2. <u>Partie supérieure :</u> Supporte la bobine source (pleine), facilitant le déroulage vers l'étage inférieur.

### Modèles 3D 

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
> <div style="text-align: justify;">On peut observer de nombreuses perforations sur la partie inférieure du châssis. Celles-ci ont été calculées avec précision pour accueillir le train d'engrenages qui actionne le guide-fil. Une fois le guide-fil en mouvement, cela distribue le filament proprement sur toute la largeur de la bobine, évitant ainsi les chevauchements et les blocages lors de l'utilisation future.</div>

---

## La troisième pièce : Le chemin d'engrenage - du moteur au guide fil

<div style="text-align: justify;">
Pour assurer la synchronisation parfaite entre la rotation de la bobine et le déplacement du guide-fil, nous avons conçu un train d'engrenages précis. Ce mécanisme permet de transformer la rotation motrice en un mouvement linéaire.
<br><br>
L'engrenage intégré à la pièce "Attrape-Bobine" est monté directement sur l'axe du moteur, constituant ainsi le point de départ de notre transmission. 
</div>

### Caractéristiques techniques :
* <u>Module 1 :</u> Le premier engrenage possède 25 dents pour un diamètre primitif (pitch circle diameter) de 25 mm. Cela définit un module de 1. 
* <u>Compatibilité :</u> Par conséquent, tous les engrenages du train ont été modélisés avec ce même module de 1 pour garantir un engrènement parfait.
* <u>Rotation sans friction :</u> Chaque engrenage intermédiaire intègre un roulement à billes logé en son centre. Ces roulements sont emmanchés sur des axes fixes, imprimés en 3D directement sur la structure du "Stand Bobine".

### Modèles 3D 

<div style="display: flex; flex-wrap: wrap; justify-content: space-between; gap: 20px;">
  <div style="flex: 1; min-width: 300px; text-align: center;">
    <iframe height="450" width="100%" src="https://modelembedder.net/embed?did=a2ca14590071317756405ddb&wvm=v&wvmid=59245a2e6b4441e9558d25dd&eid=7b8f7417ac2f0cad51f23a83&elementType=PARTSTUDIO" frameborder="0" style="border: 1px solid #eee; border-radius: 8px;"></iframe>
    <p style="margin-top: 10px; font-weight: bold; color: #2c3e50;">Détail du train d'engrenages<br><span style="font-weight: normal; font-size: 0.85em;">Du premier pignon (Attrape-Bobine) au dernier (rotation du Guide-Fil).</span></p>
  </div>
  <div style="flex: 1; min-width: 300px; text-align: center;">
    <iframe height="450" width="100%" src="https://modelembedder.net/embed?did=a2ca14590071317756405ddb&wvm=v&wvmid=f55d95e54ddd2697724d21c4&eid=e2fb31241970e6b4d31bf182&elementType=ASSEMBLY" frameborder="0" style="border: 1px solid #eee; border-radius: 8px;"></iframe>
    <p style="margin-top: 10px; font-weight: bold; color: #2c3e50;">Assemblage mécanique complet<br><span style="font-weight: normal; font-size: 0.85em;">Intégration du châssis, des moteurs, des engrenages et du système de guidage.</span></p>
  </div>
</div>

{: .note }
> <div style="text-align: justify;">Le choix du Module 1 offre un excellent compromis entre la robustesse des dents pour l'impression 3D et la précision nécessaire pour éviter le "jeu" (backlash) dans le mécanisme. L'utilisation de roulements à billes standards sur des axes fixes permet de réduire drastiquement la charge sur le moteur, évitant ainsi toute surchauffe lors de longs cycles de bobinage.</div>

---

## La quatrième pièce : Le Capteur de Tension

<div style="text-align: justify;">
Le contrôle de la tension est l'élément critique pour garantir un enroulage régulier sans étirer le filament. Pour cela, nous avons conçu un capteur sur-mesure basé sur une cellule de charge (load cell).
</div>

<div style="display: flex; align-items: center; gap: 20px; flex-wrap: wrap;">
  <div style="flex: 1; min-width: 300px; text-align: justify;">
    Le capteur est constitué d'une cellule de charge intégrée entre plusieurs pièces imprimées en 3D. Une extrémité de la cellule est ancrée sur un support fixe, lui-même solidarisé au plateau principal. L'autre extrémité supporte un bloc mobile équipé d'un <u>roulement à billes central</u>. 
    <br><br>
    Le filament circule autour de ce roulement. Pour garantir une mesure stable, deux roulements de guidage sont positionnés de part et d'autre à la même hauteur. Toute variation de tension du fil exerce une force verticale sur la cellule de charge, permettant une lecture ultra-précise des contraintes mécaniques en temps réel.
  </div>
  <div style="flex: 1; min-width: 300px; text-align: center;">
    <img src="https://github.com/user-attachments/assets/fdfe80fa-c50b-41ba-9837-7ebb727fefbb" alt="Schéma Capteur" style="width: 100%; border-radius: 8px; border: 1px solid #ddd;">
    <p style="font-size: 0.8em; color: #666;">Vue réelle du dispositif de mesure</p>
  </div>
</div>

<div style="text-align: justify; margin-top: 20px;">
Le signal analogique de la cellule de charge est traité par un ESP32. Si la tension s'écarte de la valeur de consigne, l'algorithme ajuste instantanément la vitesse des moteurs pour rétablir l'équilibre.
</div>

### Modèles 3D
<div style="display: flex; flex-wrap: wrap; justify-content: space-between; gap: 20px; margin-top: 20px;">
  <div style="flex: 1; min-width: 300px; text-align: center;">
    <iframe height="400" width="100%" src="https://modelembedder.net/embed?did=a2ca14590071317756405ddb&wvm=v&wvmid=e545353ab16c7c93b2b05265&eid=d7ed1f49986d3140a7375e72&elementType=ASSEMBLY" frameborder="0" style="border: 1px solid #eee; border-radius: 8px;"></iframe>
    <p style="margin-top: 10px; font-weight: bold;"><u>Assemblage du capteur</u><br><span style="font-weight: normal; font-size: 0.85em;">Détail du passage du fil entre les trois roulements.</span></p>
  </div>
  <div style="flex: 1; min-width: 300px; text-align: center;">
    <iframe height="400" width="100%" src="https://modelembedder.net/embed?did=a2ca14590071317756405ddb&wvm=v&wvmid=856be950d975c9576b279a8c&eid=e2fb31241970e6b4d31bf182&elementType=ASSEMBLY" frameborder="0" style="border: 1px solid #eee; border-radius: 8px;"></iframe>
    <p style="margin-top: 10px; font-weight: bold;"><u>Intégration système</u><br><span style="font-weight: normal; font-size: 0.85em;">Vue d'ensemble incluant le châssis et le capteur.</span></p>
  </div>
</div>

{: .note }
> <div style="text-align: justify;"><u>Le rôle de l'ESP32 :</u> La cellule de charge détecte une micro-déformation physique. Cette donnée est convertie en signal électrique, permettant à l'ESP32 de piloter une boucle de rétroaction. Cela garantit que la <u>vitesse de rotation</u> s'adapte en permanence à la tension détectée sur le roulement central.</div>

---
