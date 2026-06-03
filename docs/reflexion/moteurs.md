---
layout: default
title: Moteurs
parent: Études et choix techniques
nav_order: 2
---
# Moteurs et Dynamique de Charge

<div style="text-align: justify;">
Afin de sélectionner une motorisation adaptée, capable de supporter l'inertie de la bobine et la tension mécanique du filament sans décrochage, nous avons mené une étude de mathématiques L'objectif est de déterminer le couple total minimal requis ($C_{\text{total}}$).
</div>

---

## 1. Calcul du moment d'inertie ($J$)

<div style="text-align: justify;">
Le moment d'inertie caractérise la résistance d'un corps solide à la modification de sa vitesse de rotation. Pour modéliser notre système, nous exploitons la formule du moment d'inertie d'un cylindre plein :
</div>

$$J = \frac{1}{2} \cdot m \cdot R^2$$

<div style="text-align: justify;">
<b>Données d'entrée :</b>
<br>
• Rayon minimal (tambour vide) : $R_{\text{min}} = 0.045 \text{ m}$
<br>
• Rayon maximal (bobine pleine) : $R_{\text{max}} = 0.09 \text{ m}$
</div>

<br>

<table style="width: 100%; border-collapse: collapse; border: none;">
  <tr style="border: none;">
    <td style="width: 50%; padding: 10px; vertical-align: top; border: none; text-align: justify;">
      <b> Configuration : Bobine Vide</b><br>
      • Masse à vide : $M_{\text{vide}} = 0.190 \text{ kg}$<br>
      • Rayon d'application : $R_{\text{min}} = 0.045 \text{ m}$
      <br><br>
      $$J_{\text{vide}} = \frac{1}{2} \cdot 0.190 \cdot (0.045)^2$$
      $$J_{\text{vide}} \approx 1.924 \times 10^{-4} \text{ kg}\cdot\text{m}^2$$
    </td>
    <td style="width: 50%; padding: 10px; vertical-align: top; border: none; border-left: 1px solid #ddd; text-align: justify;">
      <b> Configuration : Bobine Pleine</b><br>
      • Masse en charge : $M_{\text{pleine}} = 2.190 \text{ kg}$<br>
      • Rayon d'application : $R_{\text{max}} = 0.09 \text{ m}$
      <br><br>
      $$J_{\text{pleine}} = \frac{1}{2} \cdot 2.190 \cdot (0.09)^2$$
      $$J_{\text{pleine}} \approx 8.870 \times 10^{-3} \text{ kg}\cdot\text{m}^2$$
    </td>
  </tr>
</table>

---

## 2. Couple de maintien statique ($C_{\text{statique}}$)

<div style="text-align: justify;">
Le couple statique est l'effort requis pour maintenir le système immobile ou en rotation uniforme face à la force de traction du fil (ici fixée à une valeur nominale de $F = 1 \text{ N}$). La formule fondamentale s'énonce :
</div>

$$C_{\text{statique}} = F \cdot R$$

<br>

<table style="width: 100%; border-collapse: collapse; border: none;">
  <tr style="border: none;">
    <td style="width: 50%; padding: 10px; vertical-align: top; border: none; text-align: justify;">
      <b> À vide :</b><br>
      $$C_{\text{statique\_vide}} = 1 \text{ N} \cdot 0.045 \text{ m}$$
      $$C_{\text{statique\_vide}} = 0.045 \text{ Nm}$$
    </td>
    <td style="width: 50%; padding: 10px; vertical-align: top; border: none; border-left: 1px solid #ddd; text-align: justify;">
      <b>En charge (Plein) :</b><br>
      $$C_{\text{statique\_plein}} = 1 \text{ N} \cdot 0.09 \text{ m}$$
      $$C_{\text{statique\_plein}} = 0.09 \text{ Nm}$$
    </td>
  </tr>
</table>

<br>

<div style="text-align: justify;">
<b>Prise en compte des pertes mécaniques ($C_{\text{frottement}}$) :</b>
<br>
Afin d'absorber les forces de frottement du filament et les pertes cinématiques du train d'engrenages, une marge de sécurité stricte est appliquée sur le cas le plus défavorable. En majorant l'effort, on définit le couple de frottement :
</div>

$$C_{\text{frottement}} = C_{\text{statique\_plein}} \cdot 1.2 = 0.108 \text{ Nm}$$

*(Note : Si l'on souhaite intégrer une marge globale conservative à hauteur de $0.18 \text{ Nm}$, cette valeur sera directement intégrée au bilan total).*

---

## 3. Couple de démarrage dynamique ($C_{\text{acc}}$)

<div style="text-align: justify;">
Le pic de couple survient lors de la phase transitoire d'accélération angulaire ($\alpha$). La relation fondamentale de la dynamique en rotation s'écrit :
</div>

$$C_{\text{acc}} = J \cdot \alpha$$

<div style="text-align: justify;">
<b>Calcul des grandeurs cinématiques (pour un démarrage cible en $\Delta t = 1 \text{ s}$) :</b>
<br>
• Vitesse angulaire : $\omega = \frac{V}{R} = \frac{1 \text{ m/s}}{0.045 \text{ m}} \approx 22.22 \text{ rad/s}$
<br>
• Régime de rotation : $N = \frac{\omega \cdot 60}{2\pi} \approx 212.2 \text{ tr/min}$
<br>
• Accélération angulaire : $\alpha = \frac{\Delta\omega}{\Delta t} = \frac{22.22}{1} = 22.22 \text{ rad/s}^2$
</div>

<br>

<table style="width: 100%; border-collapse: collapse; border: none;">
  <tr style="border: none;">
    <td style="width: 50%; padding: 10px; vertical-align: top; border: none; text-align: justify;">
      <b> Configuration : Vide</b><br>
      $$C_{\text{acc\_v}} = J_{\text{vide}} \cdot \alpha$$
      $$C_{\text{acc\_v}} \approx 0.000192 \cdot 22.22$$
      $$C_{\text{acc\_v}} \approx 0.0043 \text{ Nm}$$
    </td>
    <td style="width: 50%; padding: 10px; vertical-align: top; border: none; border-left: 1px solid #ddd; text-align: justify;">
      <b> Configuration : Plein</b><br>
      $$C_{\text{acc\_p}} = J_{\text{pleine}} \cdot \alpha$$
      $$C_{\text{acc\_p}} \approx 0.00887 \cdot 22.22$$
      $$C_{\text{acc\_p}} \approx 0.197 \text{ Nm}$$
    </td>
  </tr>
</table>

---

## 4. Bilan du couple total requis

<div style="text-align: justify;">
Le cas dimensionnant correspond à la configuration où la bobine est entièrement pleine (inertie et rayon maximaux). Le couple total nécessaire se formule par la sommation des contributions statiques, dynamiques et correctives :
</div>

$$C_{\text{total}} = C_{\text{statique}} + C_{\text{acc}} + C_{\text{frottement}}$$
$$C_{\text{total}} = 0.09 \text{ Nm} + 0.197 \text{ Nm} + 0.18 \text{ Nm} = 0.467 \text{ Nm}$$

<div style="text-align: justify;">
<b>Analyse critique des résultats :</b>
<br>
L'institution nous a mis à disposition des moteurs pas-à-pas de standard <u>NEMA 17</u>, développant un couple de maintien nominal de $0.42 \text{ Nm}$. Bien que notre calcul théorique le plus conservateur indique un besoin de $0.467 \text{ Nm}$ (soit un léger déficit de $0.047 \text{ Nm}$ en phase critique de démarrage), ces moteurs s'avèrent suffisants pour les phases d'essais initiaux et la validation fonctionnelle du prototype.
</div>

---

###  Spécifications Techniques du Moteur

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

