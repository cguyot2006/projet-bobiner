---
layout: default
title: Cinquième pièce
parent: Conception CAO
nav_order: 5
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
