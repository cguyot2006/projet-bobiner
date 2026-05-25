---
layout: default
nav_order: 5
title: Conception CAO
has_children: true
---

# Conception CAO

<div style="text-align: justify;">
Une fois notre vision du projet clarifiée, nous avons débuté la phase de modélisation 3D sur Onshape.

## Aperçu des Étapes

Le processus de fabrication est divisé en plusieurs étapes clés :

1. [Attrape Bobine](conception_1)
2. [Stand Bobines](conception_2)
3. [Engrenage](conception_3)
4. [Capteur de Tension]()
</div>

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

## La cinquième pièce : Le Guide Fil

<div style="text-align: justify;">
La conception de cette pièce a été l'un des défis les plus complexes de notre projet, car elle repose sur le principe d'une <u>vis sans fin à double hélice</u> (ou vis à va-et-vient). Ce système est essentiel pour distribuer le filament de manière uniforme sur toute la largeur de la bobine cible.
</div>

<div style="text-align: justify;">
Pour modéliser ce mécanisme sur Onshape, nous avons utilisé une méthode avancée :
<br><br>
1. <u>Double Hélice Inversée :</u> Nous avons tracé deux trajectoires hélicoïdales opposées sur un cylindre, se rejoignant précisément à chaque extrémité.
<br>
2. <u>Balayage :</u> Une forme géométrique spécifique a été créée à l'extrémité de ces trajectoires, puis "balayée" tout le long du chemin pour sculpter les rainures de guidage.
<br>
3. <u>Opération Booléenne :</u> Pour créer la pièce mobile (le curseur), nous avons modélisé un bloc au-dessus de la vis et utilisé l'outil <u>booléen</u> pour soustraire la forme de la vis, créant ainsi une empreinte parfaite capable de suivre le rail de guidage.
</div>

### Modèles 3D 

<div style="display: flex; flex-wrap: wrap; justify-content: space-between; gap: 20px;">

  <div style="flex: 1; min-width: 300px; text-align: center;">
    <iframe height="450" width="100%" src="https://modelembedder.net/embed?did=a2ca14590071317756405ddb&wvm=v&wvmid=0465b2f0c5f5da231969aa83&eid=96f47587672184996d944969&elementType=ASSEMBLY" frameborder="0" style="border: 1px solid #eee; border-radius: 8px;"></iframe>
    <p style="margin-top: 10px; font-weight: bold; color: #2c3e50;"><u>Détail du Guide-Fil</u><br><span style="font-weight: normal; font-size: 0.85em;">Focus sur la vis sans fin et son curseur de translation.</span></p>
  </div>

  <div style="flex: 1; min-width: 300px; text-align: center;">
    <iframe height="450" width="100%" src="https://modelembedder.net/embed?did=a2ca14590071317756405ddb&wvm=v&wvmid=f55d95e54ddd2697724d21c4&eid=e2fb31241970e6b4d31bf182&elementType=ASSEMBLY" frameborder="0" style="border: 1px solid #eee; border-radius: 8px;"></iframe>
    <p style="margin-top: 10px; font-weight: bold; color: #2c3e50;"><u>Intégration Mécanique</u><br><span style="font-weight: normal; font-size: 0.85em;">Assemblage final combinant le châssis, les engrenages et le guide-fil.</span></p>
  </div>

</div>


{: .note }
> <div style="text-align: justify;">L'avantage majeur de cette vis à double hélice est qu'elle permet de transformer une rotation continue dans un seul sens en un mouvement de va-et-vient automatique. Cela simplifie énormément le code informatique car il n'est pas nécessaire d'inverser le sens du moteur pour changer la direction du guide-fil.</div>

---
