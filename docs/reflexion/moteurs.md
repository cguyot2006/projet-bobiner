---
layout: default
title: Moteurs
parent: Études et choix techniques
nav_order: 2
---
# Réflexion Moteurs et Charge

<div style="text-align: justify;">
Afin de sélectionner une motorisation adaptée, capable de vaincre l'inertie de la bobine et de supporter la tension mécanique du filament sans décrochage, nous avons mené une étude de dimensionnement dynamique. L'objectif est de déterminer le couple total minimal requis (C<sub>total</sub>).
</div>

---

## 1. Calcul du moment d'inertie (J)

<div style="text-align: justify;">
Le moment d'inertie caractérise la résistance d'un corps solide à la modification de sa vitesse de rotation. Pour modéliser notre système, nous exploitons la formule du moment d'inertie d'un cylindre plein :
</div>

<div style="text-align: center; font-size: 1.25em; margin: 15px 0; font-weight: bold; color: #2c3e50;">
  J = ½ · m · R²
</div>

<div style="text-align: justify;">
<b>Données d'entrée :</b>
<br>
• Rayon minimal (tambour vide) : R<sub>min</sub> = 0.045 m
<br>
• Rayon maximal (bobine pleine) : R<sub>max</sub> = 0.09 m
</div>

<br>

<table style="width: 100%; border-collapse: collapse; border: none;">
  <tr style="border: none;">
    <td style="width: 50%; padding: 15px; vertical-align: top; border: none; text-align: justify; background-color: #fcfcfc;">
      <b> Configuration : Bobine Vide</b><br>
      • Masse à vide : M<sub>vide</sub> = 0.190 kg<br>
      • Rayon d'application : R<sub>min</sub> = 0.045 m
      <br><br>
      <div style="text-align: center; font-size: 1.1em;">
        J<sub>vide</sub> = ½ · 0.190 · (0.045)²<br>
        <b>J<sub>vide</sub> ≈ 1.924 × 10⁻⁴ kg·m²</b>
      </div>
    </td>
    <td style="width: 50%; padding: 15px; vertical-align: top; border: none; border-left: 2px solid #eee; text-align: justify; background-color: #fcfcfc;">
      <b> Configuration : Bobine Pleine</b><br>
      • Masse en charge : M<sub>pleine</sub> = 2.190 kg<br>
      • Rayon d'application : R<sub>max</sub> = 0.09 m
      <br><br>
      <div style="text-align: center; font-size: 1.1em;">
        J<sub>pleine</sub> = ½ · 2.190 · (0.09)²<br>
        <b>J<sub>pleine</sub> ≈ 8.870 × 10⁻³ kg·m²</b>
      </div>
    </td>
  </tr>
</table>

---

## 2. Couple de maintien statique (C<sub>statique</sub>)

<div style="text-align: justify;">
Le couple statique est l'effort requis pour maintenir le système immobile ou en rotation uniforme face à la force de traction du fil (ici fixée à une valeur nominale de F = 1 N). La formule fondamentale s'énonce :
</div>

<div style="text-align: center; font-size: 1.25em; margin: 15px 0; font-weight: bold; color: #2c3e50;">
  C<sub>statique</sub> = F · R
</div>

<br>

<table style="width: 100%; border-collapse: collapse; border: none;">
  <tr style="border: none;">
    <td style="width: 50%; padding: 15px; vertical-align: top; border: none; text-align: justify; background-color: #fcfcfc;">
      <b> À vide :</b><br>
      <div style="text-align: center; font-size: 1.1em;">
        C<sub>statique_vide</sub> = 1 N · 0.045 m<br>
        <b>C<sub>statique_vide</sub> = 0.045 Nm</b>
      </div>
    </td>
    <td style="width: 50%; padding: 15px; vertical-align: top; border: none; border-left: 2px solid #eee; text-align: justify; background-color: #fcfcfc;">
      <b> En charge (Plein) :</b><br>
      <div style="text-align: center; font-size: 1.1em;">
        C<sub>statique_plein</sub> = 1 N · 0.09 m<br>
        <b>C<sub>statique_plein</sub> = 0.09 Nm</b>
      </div>
    </td>
  </tr>
</table>

<br>

<div style="text-align: justify;">
<b>Prise en compte des pertes mécaniques (C<sub>frottement</sub>) :</b>
<br>
Afin d'absorber les forces de frottement du filament et les pertes cinématiques du train d'engrenages, une marge de sécurité stricte est appliquée sur le cas le plus défavorable. En majorant l'effort, on définit le couple de frottement :
</div>

<div style="text-align: center; font-size: 1.2em; margin: 15px 0; font-weight: bold;">
  C<sub>frottement</sub> = C<sub>statique_plein</sub> · 1.2 = 0.108 Nm
</div>

<div style="text-align: justify; font-style: italic; color: #666;">
*(Note : Si l'on souhaite intégrer une marge globale conservative à hauteur de 0.18 Nm, cette valeur sera directement intégrée au bilan total).*
</div>

---

## 3. Couple de démarrage dynamique (C<sub>acc</sub>)

<div style="text-align: justify;">
Le pic de couple survient lors de la phase transitoire d'accélération angulaire (α). La relation fondamentale de la dynamique en rotation s'écrit :
</div>

<div style="text-align: center; font-size: 1.25em; margin: 15px 0; font-weight: bold; color: #2c3e50;">
  C<sub>acc</sub> = J · α
</div>

<div style="text-align: justify;">
<b>Calcul des grandeurs cinématiques (pour un démarrage cible en Δt = 1 s) :</b>
<br>
• Vitesse angulaire : ω = V / R = 1 m/s / 0.045 m ≈ 22.22 rad/s
<br>
• Régime de rotation : N = (ω · 60) / 2π ≈ 212.2 tr/min
<br>
• Accélération angulaire : α = Δω / Δt = 22.22 / 1 = 22.22 rad/s²
</div>

<br>

<table style="width: 100%; border-collapse: collapse; border: none;">
  <tr style="border: none;">
    <td style="width: 50%; padding: 15px; vertical-align: top; border: none; text-align: justify; background-color: #fcfcfc;">
      <b> Configuration : Vide</b><br>
      <div style="text-align: center; font-size: 1.1em;">
        C<sub>acc_v</sub> = J<sub>vide</sub> · α<br>
        C<sub>acc_v</sub> ≈ 0.000192 · 22.22<br>
        <b>C<sub>acc_v</sub> ≈ 0.0043 Nm</b>
      </div>
    </td>
    <td style="width: 50%; padding: 15px; vertical-align: top; border: none; border-left: 2px solid #eee; text-align: justify; background-color: #fcfcfc;">
      <b> Configuration : Plein</b><br>
      <div style="text-align: center; font-size: 1.1em;">
        C<sub>acc_p</sub> = J<sub>pleine</sub> · α<br>
        C<sub>acc_p</sub> ≈ 0.00887 · 22.22<br>
        <b>C<sub>acc_p</sub> ≈ 0.197 Nm</b>
      </div>
    </td>
  </tr>
</table>

---

## 4. Bilan du couple total requis

<div style="text-align: justify;">
Le cas dimensionnant correspond à la configuration où la bobine est entièrement pleine (inertie et rayon maximaux). Le couple total nécessaire se formule par la sommation des contributions statiques, dynamiques et correctives :
</div>

<div style="text-align: center; font-size: 1.25em; margin: 15px 0; font-weight: bold; color: #2c3e50;">
  C<sub>total</sub> = C<sub>statique</sub> + C<sub>acc</sub> + C<sub>frottement</sub>
</div>

<div style="text-align: center; font-size: 1.2em; margin: 10px 0;">
  C<sub>total</sub> = 0.09 Nm + 0.197 Nm + 0.18 Nm = <b>0.467 Nm</b>
</div>

<br>

<div style="text-align: justify;">
<b>Analyse critique des résultats :</b>
<br>
L'institution nous a mis à disposition des moteurs pas-à-pas de standard <u>NEMA 17</u>, développant un couple de maintien nominal de 0.42 Nm. Bien que notre calcul théorique le plus conservateur indique un besoin de 0.467 Nm (soit un léger déficit de 0.047 Nm en phase critique de démarrage), ces moteurs s'avèrent suffisants pour les phases d'essais initiaux et la validation fonctionnelle du prototype.
</div>

---

### Spécifications Techniques du Moteur

<div style="display: flex; flex-wrap: wrap; justify-content: space-between; gap: 20px; margin-top: 20px;">

  <div style="flex: 1; min-width: 300px; text-align: center;">
    <img src="https://github.com/user-attachments/assets/23a5d8ab-29b2-4d35-b871-14288244512e" alt="Dimension Nema 17" style="width: 100%; border-radius: 8px; border: 1px solid #ddd;">
    <p style="margin-top: 8px; font-style: italic; font-size: 0.9em;">"Spécifications et encombrement dimensionnel du NEMA 17"</p>
  </div>

  <div style="flex: 1; min-width: 300px; text-align: center;">
    <img src="https://github.com/user-attachments/assets/8cf0bcdd-7ce8-4d3b-8423-d6c5ce7c0048" alt="Nema 17" style="width: 100%; border-radius: 8px; border: 1px solid #ddd;">
    <p style="margin-top: 8px; font-style: italic; font-size: 0.9em;">"Visuel du moteur pas-à-pas NEMA 17 intégré"</p>
  </div>

</div>

---
