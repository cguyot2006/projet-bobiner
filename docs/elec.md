---
layout: default
nav_order: 5
title: Électronique
---

# Électronique et Logique de Commande

<div style="text-align: justify;">
Notre système d'enroulement automatique repose sur l'intégration entre une chaîne d'acquisition de précision, une électronique de puissance robuste et une logique logicielle temps réel. 
</div>

---

## 1. Centralisation des tâches : L'ESP32 et l'environnement industriel

<div style="text-align: justify;">
Le cœur du système s'appuie sur le microcontrôleur <b>ESP32</b> (architecture Dual-Core cadencée à 240 MHz). Ce choix est dicté par la nécessité de traiter simultanément deux tâches hautement critiques : la génération d'impulsions micro-secondes ultra-précises pour le pilotage des moteurs pas-à-pas d'une part, et l'échantillonnage continu du capteur d'effort d'autre part. 
<br><br>
Contrairement aux cartes microcontrôleurs standards de type Arduino, l'ESP32 intègre nativement des périphériques de communication avancés. Sa connectivité sans fil (Wi-Fi) ou filaire (via l'ajout d'un module Ethernet) permet de l'intégrer directement au sein d'un réseau industriel pour communiquer de manière transparente avec un **Automate Programmable Industriel (API / PLC)**. Cette architecture ouvre la voie à une supervision en temps réel (remontée de la tension du fil, vitesse des axes) et à la réception de consignes opérationnelles à l'aide de protocoles standards de l'industrie tels que <b>Modbus TCP</b>, <b>MQTT</b> ou <b>OPC UA</b>.
</div>

---

## 2. Chaîne de conditionnement analogique : Cellule de charge et HX711

<div style="display: flex; align-items: center; gap: 20px; flex-wrap: wrap;">
  <div style="flex: 1.2; min-width: 300px; text-align: justify;">
    La mesure de la tension mécanique du fil repose sur une cellule de charge à jauge de contrainte. Physiquement, le corps en aluminium du capteur subit une micro-déformation sous l'effet de la force transversale exercée par le filament. Cette contrainte mécanique fait varier la résistance électrique de jauges montées en <u>pont de Wheatstone</u>, générant un signal analogique de l'ordre du millivolt (mV).
    <br><br>
    Ce signal infime étant inexploitable par les convertisseurs analogique-numérique (CAN) internes de l'ESP32, nous insérons un circuit conditionneur dédié : le <b>HX711</b>. Ce composant amplifie le signal différentiel et opère une numérisation haute résolution sur 24 bits. La communication entre le HX711 et l'ESP32 s'effectue via une liaison série synchrone bifilaire (broches logiques <code>DOUT</code> pour les données et <code>SCK</code> pour l'horloge), une configuration garantissant une transmission numérique immunisée contre le bruit électromagnétique ambiant.
  </div>
  <div style="flex: 0.8; min-width: 280px; text-align: center;">
    <img src="https://github.com/user-attachments/assets/a34dc7fc-08a5-4283-8de6-ace76f8e40cf" alt="Schéma d'interfaçage HX711 et ESP32" style="width: 100%; border-radius: 8px; border: 1px solid #ddd;">
    <p style="margin-top: 8px; font-style: italic; font-size: 0.85em;">"Synoptique du circuit de conditionnement du signal de pesée"</p>
  </div>
</div>

---

## 3. Électronique de puissance : Moteurs NEMA 17 et CNC Shield

<div style="text-align: justify;">
L'enroulement synchrone nécessite un contrôle rigoureux du couple, de la vitesse et de la position angulaire, ce qui justifie le choix de moteurs pas-à-pas de type <b>NEMA 17</b>. 
<br><br>
Les broches logiques de l'ESP32 délivrant un courant maximal de quelques milliampères sous une tension de 3,3 V, l'interfaçage avec une alimentation de puissance industrielle (12V/24V) requiert l'usage de drivers de puissance montés sur un <b>CNC Shield</b>. Le rôle de ces ponts en H intégrés est de traduire les signaux de commande de l'ESP32 (<code>STEP</code> pour l'impulsion de pas, <code>DIR</code> pour le sens de rotation, et <code>ENABLE</code> pour la mise sous tension globale) en commutations de fortes intensités dans les bobinages des moteurs. De plus, les drivers gèrent le <i>micro-stepping</i> (fractionnement électronique des pas natifs du moteur), ce qui linéarise le mouvement de rotation, atténue les résonances mécaniques et optimise la régularité du dépôt de filament sur la bobine.
</div>

---

## 4. Algorithme de régulation et protocole de calibration

<div style="display: flex; align-items: center; gap: 20px; flex-wrap: wrap;">
  <div style="flex: 1.2; min-width: 300px; text-align: justify;">
    Le programme embarqué exécute une boucle de régulation dynamique non-bloquante basée sur la bibliothèque <b>AccelStepper</b>. À chaque itération de la boucle principale (<code>loop</code>), l'ESP32 interroge le HX711 pour acquérir la force instantanée. Si la tension s'écarte de la plage de consigne cible (fixée entre 10 g et 30 g), l'algorithme ajuste la variable de vitesse globale. 
    <br><br>
    L'innovation technique réside dans la <b>gestion asymétrique des axes</b> : le moteur 1 réagit immédiatement à la consigne, tandis que le moteur 2 démarre avec une temporisation logicielle de 5 secondes et maintient un décalage fixe de -25 pas/s (ou -15 pas/s selon les configurations de test) par rapport au premier, optimisant ainsi la tension différentielle lors du bobinage.
    <br><br>
    Afin d'assurer la conversion des grandeurs électriques brutes en grammes réels, le programme intègre une routine de calibration rigoureuse en deux étapes :
    <br>
    • <b>La Tare :</b> Enregistrement de la valeur brute à vide pour définir le point zéro machine initial et soustraire mathématiquement la charge propre du mécanisme de guidage.
    <br>
    • <b>Le facteur d'échelle :</b> Application d'une masse étalon connue sur le capteur. Le microcontrôleur calcule le ratio mathématique <code>(Valeur Brute / Masse Réelle)</code>. Ce facteur d'échelle constant est injecté de manière permanente dans l'équation de conversion pour traduire les variations de tension en grammes lors du processus de régulation.
  </div>
  <div style="flex: 0.8; min-width: 280px; text-align: center;">
    <img src="https://github.com/user-attachments/assets/8b1c7957-3ec6-429f-8628-102339071d58" alt="Composants et Shield Électronique" style="width: 100%; border-radius: 8px; border: 1px solid #ddd;">
    <p style="margin-top: 8px; font-style: italic; font-size: 0.85em;">"Aperçu du shield de commande et connecteurs moteurs"</p>
  </div>
</div>

---

## 5. Difficultés rencontrées lors du déploiement logiciel

<div style="text-align: justify;">
La phase de développement sur l'IDE Arduino a mis en évidence plusieurs contraintes techniques majeures :
<br><br>
1. <u>Temps de compilation excessifs :</u> L'utilisation de bibliothèques lourdes assurant la gestion du calcul en virgule flottante (pour la calibration) combinée à l'architecture Dual-Core de l'ESP32 a considérablement allongé le temps de compilation du code, ralentissant nos cycles de test sur le prototype.
<br>
2. <u>Instabilité de la communication série (Erreurs de ports) :</u> Nous avons fait face à de nombreuses pertes de détection du port COM par l'IDE Arduino lors des téléversements. Ce problème provenait d'un conflit entre la consommation de courant des moteurs au démarrage et l'alimentation USB de l'ordinateur, provoquant des micro-coupures sur le circuit d'interface USB-Série de l'ESP32. L'isolation de la puissance moteur via une alimentation externe dédiée a résolu cette anomalie.
</div>

---
