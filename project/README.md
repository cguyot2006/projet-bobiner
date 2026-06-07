# Les ressources du projet

Comme pour tout projet d'ingénierie, le développement du Robobiner s'est appuyé sur l'étude de solutions existantes. Ces ressources nous ont permis d'identifier les bonnes pratiques en matière de conception mécanique, de choix des composants et de programmation.

## Conception générale de la machine

Les systèmes industriels de rebobinage existants nous ont servi de référence pour définir l'architecture globale de notre machine, notamment l'organisation des bobines, le cheminement du fil et l'intégration des différents composants.

- Fer-Plast – Rebobineur industriel :
https://www.fer-plast.com/fr/produits/emballage/imprimantes-et-etiquetage/enrouleurs-et-d%C3%A9rouleurs-pour-bobines-detiquettes/rebobiner-rtr-detail
- Exemple de système de rebobinage automatisé :
https://youtu.be/B1Um_I1KRLo
- Conception d'un enrouleur automatique :
https://youtu.be/Z5IBeuUkbwU

## Conception du guide fil 

Le guide-fil est un élément essentiel pour garantir une répartition homogène du fil sur la bobine. Les vidéos suivantes nous ont permis d'étudier différents mécanismes de translation et d'en comprendre les avantages et les limites.

- Système de guide-fil automatisé :
https://youtu.be/LP9k6_QAmTU
- Exemple de mécanisme de guidage :
https://youtu.be/gvHMyLjorVU

## Choix des composants

Le choix des moteurs, capteurs et composants électroniques a été réalisé à partir de catalogues spécialisés et de fournisseurs reconnus dans le domaine de la robotique et de l'automatisation.

- Transmotec : moteurs pas à pas et solutions de motorisation
https://fr.transmotec.com/product-category/stepping-motors/
- Robot-Maker : composants électroniques et mécaniques
https://www.robot-maker.com/
- Systeal : capteurs, électronique industrielle et automatisation
https://www.systeal.com/fr/

## Programmation et électronique 

La programmation du Robobiner repose sur un ESP32 pilotant deux moteurs pas à pas NEMA ainsi qu'un capteur de tension. Les ressources suivantes ont été particulièrement utiles pour comprendre le fonctionnement des bibliothèques de contrôle moteur et l'acquisition de données capteurs.

### ESP32 et moteurs pas à pas
- ESP32 + bibliothèque AccelStepper
https://www.youtube.com/results?search_query=ESP32+AccelStepper+tutorial
- Contrôle d'un moteur NEMA 17 avec ESP32 et driver A4988/DRV8825
https://www.youtube.com/results?search_query=ESP32+NEMA17+A4988
- Synchronisation de plusieurs moteurs pas à pas avec ESP32
https://www.youtube.com/results?search_query=ESP32+multiple+stepper+motors

### Capteur de tension (Load Cell)
- Utilisation d'une cellule de charge avec module HX711 et ESP32
https://www.youtube.com/results?search_query=ESP32+HX711+load+cell+tutorial
- Calibration d'un capteur de force avec ESP32
https://www.youtube.com/results?search_query=ESP32+load+cell+calibration

### Documentation officielle
- Arduino IDE : https://www.arduino.cc/
- ESP32 Documentation : https://docs.espressif.com/
