---
layout: default
title: Composants
parent: Études et choix techniques
nav_order: 1
---

# Réflexion - Capteur de tension

<div style="text-align: justify;">
La mesure de la tension dynamique d'un filament en cours d'enroulement est une problématique complexe. N'ayant pas trouvé de capteur de tension standard adapté à notre projet, nous avons mener des recherches pour développer notre propre système de mesure. 
</div>

---

## 1. Trappe oscillante avec capteur de contact

<div style="display: flex; align-items: center; gap: 20px; flex-wrap: wrap;">
  <div style="flex: 1; min-width: 300px; text-align: justify;">
    Notre première réflexion reposait sur une trappe rectangulaire mobile actionnée par le passage du fil. Un capteur de fin de course (contact sec) devait signaler si le fil exerçait une pression suffisante pour ouvrir les portes du mécanisme.
    <br><br>
    Cependant, cette approche présentait des limites critiques :
    <br>
    • <u>Absence de mesure quantitative :</u> Le capteur fonctionnait en tout-ou-rien (binaire), détectant la présence du fil plutôt que sa tension réelle. Pour quantifier la force, il aurait fallu adjoindre un ressort de rappel calibré et un potentiomètre rotatif pour mesurer la variation de l'angle d'ouverture.
    <br>
    • <u>Complexité d'intégration mécanique :</u> La liaison pivot entre la partie mobile (trappe) et la structure stable (socle) s'avérait difficile à modéliser et à fiabiliser en impression 3D. De plus, si la structure est mal pensée, celle ci pourrait s'avérée cassante et donc éphémère.
    <br>
    • <u>Rendement et faisabilité :</u> Suite à la revue de projet avec nos professeurs, cette solution a été écartée au profit d'un système plus robuste, plus simple et intégrant dès le départ les contraintes de fabrication.
  </div>
  <div style="flex: 1; min-width: 300px; text-align: center;">
    <img src="https://github.com/user-attachments/assets/ed818643-1075-4c53-afb4-2a33111de8a7" alt="Capteur de tension - trappe cercle bleu" style="width: 100%; border-radius: 8px; border: 1px solid #ddd;">
    <p style="margin-top: 8px; font-style: italic; font-size: 0.9em;">Capteur de tension - Concept initial de la trappe</p>
  </div>
</div>

<br>
<div style="text-align: center;">
  <img src="https://github.com/user-attachments/assets/a5e37853-15ff-4405-93f4-9436857d61c1" alt="Recherches initiales" style="width: 100%; border-radius: 8px; border: 1px solid #ddd;">
  <p style="margin-top: 8px; font-style: italic; font-size: 0.9em;">"Schémas de la trappe oscillante"</p>
</div>

---

## 2. Le potentiomètre et le bras danseur

<div style="display: flex; align-items: center; gap: 20px; flex-wrap: wrap;">
  <div style="flex: 1; min-width: 300px; text-align: justify;">
    Le principe du bras danseur (ou rouleau danseur) est un standard industriel pour la régulation de tension. Le filament passe sur un roulement monté à l'extrémité d'un bras pivotant. Ce bras est maintenu en équilibre mécanique par un ressort de rappel ajustable. 
    <br><br>
    Lorsqu'une variation de tension survient sur la ligne, le bras pivote. Ce déplacement angulaire est mesuré directement par un potentiomètre rotatif lié à l'axe de pivot. La tension mécanique est ainsi convertie en une variation de résistance électrique, puis en tension lue par le microcontrôleur.
    <br><br>
    <b>Difficultés identifiées :</b> L'étalonnage du ressort est complexe (phénomène d'oscillation et d'inertie du bras pouvant fausser la mesure). L'usure mécanique prématurée de la piste du potentiomètre et les frottements induits par le mécanisme risquaient de perturber l'asservissement en temps réel. De plus, l'équipe avait un très grand mal à visualiser ce capteur de tension dans notre projet et l'assemblage globale avec le bras danceur.
  </div>
  <div style="flex: 1; min-width: 300px; text-align: center;">
    <img src="https://github.com/user-attachments/assets/2d0715d0-7f2c-4854-a712-c8d2aeb63008" alt="schema bras danceur - capteur de tension" style="width: 100%; border-radius: 8px; border: 1px solid #ddd;">
    <p style="margin-top: 8px; font-style: italic; font-size: 0.9em;">Schéma de principe d'un capteur de tension à bras danseur</p>
  </div>
</div>

---

## 3. Solution commerciale : Capteur sur étagère

<div style="display: flex; align-items: center; gap: 20px; flex-wrap: wrap;">
  <div style="flex: 1; min-width: 300px; text-align: justify;">
    Nos recherches de composants industriels existants nous ont conduits vers le modèle <u>TE-22 Tension Sensor</u> distribué par l'entreprise Checkline Europe. Ce dispositif repose sur un système à 3 roulements, où le galet central mesure la force délective induite par la tension du fil. 
    <br><br>
    Nous avons initié une demande de devis auprès du fournisseur afin de ne pas dépasser le budget de notre projet. N'ayant reçu aucun retour de leur part, nous avons pris la décision de développer notre propre alternative basée sur ce même principe.
  </div>
  <div style="flex: 1; min-width: 300px; text-align: center;">
    <img src="https://github.com/user-attachments/assets/b88ac2b1-08af-4ec3-b085-5062db564c62" alt="TE-22 Tension Sensor - Checkline EU" style="width: 100%; border-radius: 8px; border: 1px solid #ddd;">
    <p style="margin-top: 8px; font-style: italic; font-size: 0.9em;">TE-22 Tension Sensor - Checkline EU</p>
  </div>
</div>

---

## 4. Solution retenue : Capteur sur-mesure à cellule de charge

<div style="text-align: justify;">
Inspirés par la disposition en triangle de la solution industrielle, nous avons conçu un capteur basé sur une <u>cellule de charge à jauge de contrainte</u>. Le filament est guidé à travers un cheminement de trois roulements à billes alignés. Le roulement central est solidaire de l'extrémité mobile de la cellule de charge, agissant comme le point de mesure d'effort.
</div>

<br>

<div style="display: flex; align-items: center; gap: 20px; flex-wrap: wrap;">
  <div style="flex: 1; min-width: 300px; text-align: justify;">
    <b>Chaîne d'acquisition et fonctionnement électronique :</b>
    <br>
    La mesure de la tension mécanique repose sur la déformation microscopique du corps en aluminium de la cellule sous l'effet de la force transversale exercée par le fil. Cette contrainte modifie la résistance électrique des jauges montées en <u>pont de Wheatstone</u>, générant un signal analogique infime de l'ordre du millivolt ($mV$).
    <br><br>
    Ce signal différentiel étant inexploitable directement par les entrées CAN classiques de l'<u>ESP32</u>, nous intégrons un circuit conditionneur dédié : le **HX711**. Ce composant intègre un amplificateur à faible bruit et un convertisseur analogique-numérique de haute résolution (24 bits). 
    <br><br>
    Les données numérisées sont transmises à l'ESP32 via un bus série synchrone bifilaire (lignes <u>DOUT</u> pour les données et <u>SCK</u> pour l'horloge), ce qui immunise le signal contre les interférences électromagnétiques générées par les moteurs à proximité.
  </div>
  <div style="flex: 1; min-width: 300px; text-align: center;">
    <img src="https://github.com/user-attachments/assets/59c678c4-d16d-4a88-b435-6475bd7fbef1" alt="Cellule de charge a jauges de contraintes" style="width: 100%; border-radius: 8px; border: 1px solid #ddd;">
    <p style="margin-top: 8px; font-style: italic; font-size: 0.9em;">"Intégration finale de la cellule de charge à jauges de contraintes"</p>
  </div>
</div>

---
