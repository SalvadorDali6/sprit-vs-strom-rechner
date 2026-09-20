# ⚡ Sprit vs. Strom Rechner

Ein leichtgewichtiges Web-Tool zum direkten Kostenvergleich von **Elektrofahrzeugen (EV)**, **Diesel** und **Benzin** auf 100 km – inklusive Ermittlung des exakten **Break-Even-Strompreises**.

Live testen: [salvadordali6.github.io/sprit-vs-strom-rechner](https://salvadordali6.github.io/sprit-vs-strom-rechner/)

---

## 📐 Berechnungsgrundlagen

### 1. Fahrtkosten pro 100 km
Die Kosten je 100 Kilometer ergeben sich direkt aus dem jeweiligen Verbrauch und dem Bezugspreis:

$$\text{Kosten}_{\text{Diesel}} = \text{Verbrauch}_{\text{Diesel}} \, [\text{l/100km}] \times \text{Preis}_{\text{Diesel}} \, [€/\text{l}]$$

$$\text{Kosten}_{\text{Benzin}} = \text{Verbrauch}_{\text{Benzin}} \, [\text{l/100km}] \times \text{Preis}_{\text{Benzin}} \, [€/\text{l}]$$

$$\text{Kosten}_{\text{EV}} = \text{Verbrauch}_{\text{EV}} \, [\text{kWh/100km}] \times \text{Strompreis} \, [€/\text{kWh}]$$

---

### 2. Break-Even-Strompreis (€/kWh)
Gibt an, bis zu welchem Ladepreis das Elektroauto günstiger fährt als das jeweilige Vergleichsfahrzeug:

$$\text{Break-Even vs. Diesel} = \frac{\text{Kosten}_{\text{Diesel}}}{\text{Verbrauch}_{\text{EV}}}$$

$$\text{Break-Even vs. Benzin} = \frac{\text{Kosten}_{\text{Benzin}}}{\text{Verbrauch}_{\text{EV}}}$$

Liegt der tatsächliche Strompreis unter diesem Wert, fährt das E-Auto günstiger; liegt er darüber, fährt der Verbrenner günstiger.

---

## 📊 Hintergrund: Energiegehalt und Antriebseffizienz

Dass die Kosten trotz höherer chemischer Energiedichte von Kraftstoffen oft zugunsten von Strom ausfallen, basiert auf den unterschiedlichen Antriebswirkungsgraden:

| Energieträger / Antrieb | Heizwert / Energiegehalt | Durchschnittlicher Alltags-Wirkungsgrad |
| :--- | :--- | :--- |
| **Benzin (Super 95)** | ~8,8 kWh / Liter | ca. 20 % – 25 % |
| **Diesel** | ~9,8 kWh / Liter | ca. 30 % – 35 % |
| **Strom (EV)** | 1,0 kWh / kWh | ca. 80 % – 90 % *(inkl. Ladeverlusten)* |

Da der Bordcomputer den tatsächlichen Energiebedarf bereits fahrfertig anzeigt, basiert die Berechnung des Rechners direkt auf dem realen Endverbrauch auf 100 km.

### ⚠️ Notiz zu Ladeverlusten
Um die reale Kostenbelastung nicht schönzurechnen, kalkuliert das Tool beim E-Auto automatisch mit einem **pauschalen Ladeverlust von 10 %**. 

Bordcomputer im E-Auto zeigen oft nur den Verbrauch *aus der Batterie* an. Der Stromzähler an der Wallbox erfasst jedoch auch die Wandlungsverluste (AC zu DC) und die Energie, die das Batteriemanagement für das Temperieren des Akkus beim Ladevorgang benötigt. Stellst du im Rechner also einen Bordcomputer-Wert von `17.0 kWh/100km` ein, berechnet das Tool die Kosten fairerweise auf Basis von `18.7 kWh/100km`, da dies der Menge entspricht, die du tatsächlich bezahlst.
