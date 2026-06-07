---
layout: default
nav_order: 6
title: Électronique
---

# Électronique et Logique de Commande

<div style="text-align: justify;">
Notre système d'enroulement automatique repose sur l'intégration entre une chaîne d'acquisition de précision, une électronique de puissance robuste et une logique logicielle temps réel. 
</div>

---

## 1. Centralisation des tâches : L'ESP32 et l'environnement industriel

<div style="text-align: justify;">
Le cœur du système s'appuie sur le microcontrôleur <u>ESP32</u> (architecture Dual-Core cadencée à 240 MHz). Ce choix est dicté par la nécessité de traiter simultanément deux tâches hautement critiques : la génération d'impulsions micro-secondes ultra-précises pour le pilotage des moteurs pas-à-pas d'une part, et l'échantillonnage continu du capteur d'effort d'autre part. 
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
  <img src="https://github.com/user-attachments/assets/6a105825-8be0-44ce-8719-02fc91a0de0c" alt="Cellule de charge à jauge de contrainte" style="width: 100%; border-radius: 8px; border: 1px solid #ddd;">
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
    <img src="https://github.com/user-attachments/assets/8b1c7957-3ec6-429f-8628-102339071d58" alt="Modbus" style="width: 100%; border-radius: 8px; border: 1px solid #ddd;">
  </div>
</div>

---

## 5. Difficultés rencontrées lors du déploiement logiciel

<div style="text-align: justify;">
La phase de développement sur l'IDE Arduino a mis en évidence plusieurs contraintes techniques majeures :
<br><br>
1. <u>Focntionnement :</u> Sur le plan ergonomique et opérationnel, la séquence d'utilisation actuelle s'avère encore contraignante et demande à être fluidifiée. Dans la pratique, la dérive naturelle du capteur de force impose de répéter régulièrement la procédure de calibration, ce qui alourdit la mise en route du système. Pour pallier cette rigidité et offrir un contrôle plus intuitif à l'opérateur, l'interface homme-machine (IHM) matérielle doit être développée. L'intégration de boutons poussoirs physiques permettrait d'ajuster dynamiquement (augmenter ou diminuer) la consigne de vitesse des moteurs en temps réel. De plus, l'ajout d'un interrupteur général (switch ON/OFF) est envisagé pour offrir une mise en marche simplifiée et un arrêt immédiat de la régulation et des moteurs, garantissant ainsi un meilleur contrôle et une sécurisation du processus de bobinage.
<br><br><br>

2. <u>Régulation des moteurs :</u> Bien que fonctionnelle, la boucle de régulation actuelle constitue un axe d'amélioration prioritaire pour optimiser la fiabilité et la fluidité du système. Actuellement, l'algorithme réagit de manière trop directe et abrupte aux données transmises par la cellule de charge. Ce comportement engendre un phénomène d'oscillation mécanique (ou pompage) : le fil se tend de manière excessive, ce qui provoque un arrêt ou un ralentissement brusque des moteurs, puis se relâche, entraînant une accélération soudaine et un déroulement trop rapide. L'évolution logicielle vers un asservissement plus avancé, tel que l'intégration d'un correcteur PID (Proportionnel, Intégral, Dérivé), s'avère nécessaire. Cette mise à niveau permettrait d'amortir ces variations, d'anticiper l'inertie physique du fil et de lisser précisément les accélérations afin de maintenir une tension de bobinage constante, sans à-coups ni blocages..
</div>

---
