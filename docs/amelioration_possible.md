---
layout: default
nav_order: 7
title: Améliorations 
---

# Perspectives d'Évolution et Améliorations Futures

<div style="text-align: justify;">
Bien que le Robobiner remplisse efficacement sa fonction principale de bobinage automatisé, l'évaluation de notre prototype a mis en lumière plusieurs axes d'optimisation. Ces pistes d'amélioration permettraient d'augmenter significativement ses performances, sa fiabilité opérationnelle et l'ergonomie générale du système dans un contexte industriel ou de laboratoire.
</div>

---

## 1. Interface utilisateur (IHM)

<div style="text-align: justify;">
L'intégration d'un écran LCD ou d'un afficheur OLED industriel permettrait de visualiser en temps réel les variables d'état du système (vitesse de défilement, tension instantanée du fil en grammes, métrologie des pas effectués). L'adjonction de boutons de navigation physiques ou d'un encodeur incrémental faciliterait le paramétrage des consignes à la volée (seuils de tolérance, diamètres de bobine), affranchissant l'opérateur de toute modification logicielle directe dans le code source.
</div>

---

## 2. Optimisation du contrôle automatique de la tension

<div style="display: flex; align-items: center; gap: 20px; flex-wrap: wrap;">
  <div style="flex: 1; min-width: 300px; text-align: justify;">
    Actuellement, le système mesure la tension du fil pour valider la conformité du processus. Une évolution majeure consisterait à implémenter un véritable algorithme d'asservissement en boucle fermée (type régulateur PID : Proportionnel, Intégral, Dérivé). 
    <br><br>
    Cet automatisme ajusterait en temps réel et de manière prédictive la vitesse des moteurs pas-à-pas en fonction des micro-variations de tension lues par le HX711. Cela garantirait un enroulement parfaitement homogène, éliminerait les à-coups mécaniques et réduirait à zéro le risque de rupture du filament.
  </div>
  <div style="flex: 1; min-width: 250px; text-align: center;">
    <img src="https://github.com/user-attachments/assets/1a480ea4-b274-4f91-83f2-be2a1064521c" alt="logiciel d'automatiste" style="width: 100%; border-radius: 8px; border: 1px solid #ddd;">
    <p style="margin-top: 8px; font-style: italic; font-size: 0.85em;">"Modélisation d'une boucle d'asservissement sur logiciel d'automatisme"</p>
  </div>
</div>

---

## 3. Cinématique du guide-fil

<div style="text-align: justify;">
Le mécanisme de distribution latérale du fil pourrait gagner en régularité par l'utilisation d'un système de translation de précision supérieure. Remplacer le guidage d'origine par une vis à billes ou par des rails de guidage linéaire renforcés offrirait une répétabilité micrométrique. Cette modification est indispensable pour traiter des filaments de très faibles diamètres ou des fibres techniques haut de gamme exigeant un rangement spire à spire parfait.
</div>

---

## 4. Métrologie et détection de fin de course

<div style="display: flex; align-items: center; gap: 20px; flex-wrap: wrap;">
  <div style="flex: 1; min-width: 300px; text-align: justify;">
    L'ajout de capteurs de fin de course (optiques ou mécaniques) permettrait d'automatiser l'arrêt de la machine lors de deux événements critiques : l'épuisement du consommable sur la bobine source ou le remplissage complet de la bobine réceptrice. 
    <br><br>
    L'implantation d'un <b>encodeur rotatif</b> supplémentaire sur l'arbre de dévidage permettrait de corréler la vitesse angulaire et la longueur réelle de fil enroulé, sécurisant ainsi la machine contre tout emballement ou patinage.
  </div>
  <div style="flex: 1; min-width: 200px; text-align: center;">
    <img src="https://github.com/user-attachments/assets/759f318f-a1ae-4e85-ad9d-1cdfb1c5411d" alt="encodeur rotatif" style="max-width: 200px; width: 100%; border-radius: 8px; border: 1px solid #ddd;">
    <p style="margin-top: 8px; font-style: italic; font-size: 0.85em;">"Intégration d'un encodeur rotatif pour le suivi métrologique"</p>
  </div>
</div>

---

## 5. Connectivité et supervision IoT

<div style="text-align: justify;">
Profitant de la présence native des modules sans fil sur l'ESP32, une mise à niveau logicielle permettrait d'intégrer une interface web embarquée ou une compatibilité Bluetooth/Wi-Fi. Les données de fonctionnement pourraient être téléversées vers un serveur local pour analyser l'évolution temporelle de la tension du fil (historisation des données), facilitant le contrôle qualité de la production.
</div>

---

## 6. Améliorations structurelles et guidage du capteur de tension

<div style="display: flex; align-items: center; gap: 20px; flex-wrap: wrap;">
  <div style="flex: 1; min-width: 300px; text-align: justify;">
    <b>Optimisation mécanique du capteur d'effort :</b>
    <br>
    Un axe d'amélioration critique identifié lors de nos tests dynamiques concerne le cheminement du fil au niveau de la jauge de contrainte. À haute vitesse, le filament a tendance à glisser et à sauter hors des roulements à billes lisses. 
    <br><br>
    Pour corriger ce défaut de guidage, il est impératif de modifier le design de la cloche de protection en y intégrant des parois latérales de confinement (joues de guidage). Prisonnier de sa gorge, le fil ne pourrait plus s'échapper, garantissant une lecture de force constante et fiable même lors de brusques variations de vitesse.
  </div>
  <div style="flex: 1; min-width: 250px; text-align: center;">
    <img src="https://github.com/user-attachments/assets/13587519-d0ea-45f6-ab4e-17ee4256690f" alt="Amélioration guidage roulement" style="width: 100%; border-radius: 8px; border: 1px solid #ddd;">
    <p style="margin-top: 8px; font-style: italic; font-size: 0.85em;">"Modification CAO requise pour le confinement du roulement du capteur"</p>
  </div>
</div>

<br>

<div style="text-align: justify;">
<b>Rigidité du châssis :</b>
<br>
La structure globale pourrait être allégée tout en augmentant sa rigidité torsionnelle. Une reconception du bâti vertical, combinant des profilés d'aluminium rainurés et des liaisons imprimées en PETG ou en plastique chargé en fibre de carbone, réduirait les résonances vibratoires constatées lors des pointes de vitesse des moteurs NEMA 17.
</div>

---

## 7. Sécurité opérationnelle

<div style="text-align: justify;">
Dans l'optique d'une certification ou d'une utilisation industrielle conforme aux normes de sécurité des machines, l'intégration d'un bouton d'arrêt d'urgence de type "coup de poing" (câblé directement sur la ligne d'alimentation du CNC Shield / broche <code>RESET-ENABLE</code>) est indispensable. De plus, l'installation de carters transparents en polycarbonate autour du train d'engrenages préviendrait tout risque de pincement ou d'accident lors des phases d'enroulement à haut régime.
</div>

---
