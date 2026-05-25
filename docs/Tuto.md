---
layout: default
nav_order: 7
title: Tutoriels Creation CAO
---

# Tutoriels et Montée en Compétences CAO

Pour mener à bien la conception de ce projet complexe, nous avons dû approfondir nos connaissances techniques en modélisation 3D, notamment pour les mécanismes de précision et les assemblages.

## Tuto 1 : Filetage et liaisons vissées

L'un des principaux défis a été la création de filetages fonctionnels adaptés à l'impression 3D. Pour maîtriser cette technique, nous nous sommes appuyés sur des ressources spécialisées :

[![Modéliser un filetage avec Onshape](https://i.ytimg.com/vi/M8hLVeiXK9g/maxresdefault.jpg)](https://youtu.be/M8hLVeiXK9g)
*Cliquez sur l'image pour voir le tutoriel : [Modélisation de filetages imprimables en 3D](https://youtu.be/M8hLVeiXK9g)*

### Galerie des modèles réalisés avec du filetage

Voici les pièces clés que nous avons développées suite à ces recherches:

<div style="display: flex; flex-wrap: wrap; justify-content: space-between; gap: 15px;">

  <div style="flex: 1; min-width: 250px; text-align: center;">
    <iframe height="350" width="100%" src="https://modelembedder.net/embed?did=a2ca14590071317756405ddb&wvm=v&wvmid=36db1a26917329635d174889&eid=ac5b7edd050a7108625beb73&elementType=PARTSTUDIO" frameborder="0" style="border: 1px solid #ddd; border-radius: 8px;"></iframe>
    <p style="margin-top: 8px; font-weight: bold; font-size: 0.9em;">L'Attrape-Bobine<br>(Pièce seule)</p>
  </div>

  <div style="flex: 1; min-width: 250px; text-align: center;">
    <iframe height="350" width="100%" src="https://modelembedder.net/embed?did=a2ca14590071317756405ddb&wvm=v&wvmid=0465b2f0c5f5da231969aa83&eid=96f47587672184996d944969&elementType=ASSEMBLY" frameborder="0" style="border: 1px solid #ddd; border-radius: 8px;"></iframe>
    <p style="margin-top: 8px; font-weight: bold; font-size: 0.9em;">Le Guide-Fil<br>(Assemblage mécanique)</p>
  </div>

  <div style="flex: 1; min-width: 250px; text-align: center;">
    <iframe height="350" width="100%" src="https://modelembedder.net/embed?did=a2ca14590071317756405ddb&wvm=v&wvmid=6eba7b0521a836c4bd9e2562&eid=bdba4675b2ed01e616206cca&elementType=ASSEMBLY" frameborder="0" style="border: 1px solid #ddd; border-radius: 8px;"></iframe>
    <p style="margin-top: 8px; font-weight: bold; font-size: 0.9em;">Visserie spécifique<br>(Capteur de tension)</p>
  </div>

</div>

{: .info }
> **Note technique :** L'utilisation de filetages à 45° (au lieu des 60° standards) sur ces modèles a été privilégiée pour faciliter l'impression sans supports et garantir un coulissage fluide.

--- 

## Tuto 2 : Modélisation d'engrenages sur Onshape

Pour acquérir ces compétences, nous avons suivi ce tutoriel de référence qui explique comment utiliser les scripts de génération d'engrenages (Spur Gear) et comment créer des relations de mouvement réalistes :

[![Onshape How To: Gears](https://i.ytimg.com/vi/AxCgO_eJocc/maxresdefault.jpg)](https://youtu.be/AxCgO_eJocc)
*Cliquez sur l'image pour accéder au tutoriel : [Onshape How To: Gears](https://youtu.be/AxCgO_eJocc)*

Grâce à cette ressource, nous avons appris :
* À utiliser la fonctionnalité "Spur Gear" pour générer des profils de dents parfaits.
* À calculer l'entraxe exact pour un engrènement fluide.
* À définir les Gear Relations dans les assemblages pour simuler le fonctionnement réel.

### Galerie des modèles réalisés


<div style="display: flex; flex-wrap: wrap; justify-content: space-between; gap: 20px;">

  <div style="flex: 1; min-width: 45%; text-align: center;">
    <iframe height="400" width="100%" src="https://modelembedder.net/embed?did=a2ca14590071317756405ddb&wvm=v&wvmid=d6dbb5062010f2d34cb96186&eid=b63ffc71527d5949a16b9898&elementType=ASSEMBLY" frameborder="0" style="border: 1px solid #eee; border-radius: 8px;"></iframe>
    <p style="margin-top: 10px; font-weight: bold;">Application du tutoriel<br><span style="font-weight: normal; font-size: 0.9em;">Exercice de base sur les ratios et l'assemblage.</span></p>
  </div>

  <div style="flex: 1; min-width: 45%; text-align: center;">
    <iframe height="400" width="100%" src="https://modelembedder.net/embed?did=a2ca14590071317756405ddb&wvm=v&wvmid=59245a2e6b4441e9558d25dd&eid=7b8f7417ac2f0cad51f23a83&elementType=PARTSTUDIO" frameborder="0" style="border: 1px solid #eee; border-radius: 8px;"></iframe>
    <p style="margin-top: 10px; font-weight: bold;">Chemin d'engrenage<br><span style="font-weight: normal; font-size: 0.9em;">Transmission allant du moteur vers le guide-fil.</span></p>
  </div>

  <div style="flex: 1; min-width: 45%; text-align: center;">
    <iframe height="400" width="100%" src="https://modelembedder.net/embed?did=a2ca14590071317756405ddb&wvm=v&wvmid=36db1a26917329635d174889&eid=ac5b7edd050a7108625beb73&elementType=PARTSTUDIO" frameborder="0" style="border: 1px solid #eee; border-radius: 8px;"></iframe>
    <p style="margin-top: 10px; font-weight: bold;">L'Attrape-Bobine<br><span style="font-weight: normal; font-size: 0.9em;">Fixé sur le moteur, il constitue le premier engrenage du train.</span></p>
  </div>

  <div style="flex: 1; min-width: 45%; text-align: center;">
    <iframe height="400" width="100%" src="https://modelembedder.net/embed?did=a2ca14590071317756405ddb&wvm=v&wvmid=0465b2f0c5f5da231969aa83&eid=96f47587672184996d944969&elementType=ASSEMBLY" frameborder="0" style="border: 1px solid #eee; border-radius: 8px;"></iframe>
    <p style="margin-top: 10px; font-weight: bold;">Le Guide-Fil<br><span style="font-weight: normal; font-size: 0.9em;">Transformation de la rotation en translation.</span></p>
  </div>

</div>

{: .note }
> Ajustement des Ratios : > Initialement, nous avions prévu un ratio de 25 dents à 12 dents. Cependant, en raison du diamètre des roulements à billes logés à l'intérieur de l'engrenage, nous avons dû adapter le design. Le ratio final est de 25 dents à 17 dents, ce qui conserve l'intégrité de la pièce avec une transmission de la rotation.

---





