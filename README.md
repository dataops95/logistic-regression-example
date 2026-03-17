<img src="img/logistic-regression.png" alt="Interactive Logistic Regression" width="80%">

---
## Deutsche Version

### 1. Grundlegende Konzepte
Bevor die Regler auf dem Bildschirm angepasst werden, müssen die mathematischen Grundlagen verstanden werden:
* **Binäre Klassifikation:** Wir versuchen, Objekte in zwei Klassen zu unterteilen (z. B. "krank" oder "gesund"). Hier handelt es sich um **Klasse 0** (rote Punkte/negative Klasse) und **Klasse 1** (grüne Punkte/positive Klasse).
* **Wahrscheinlichkeit (Probability):** Das Modell trifft keine bloße Ja/Nein-Aussage, sondern schätzt die Chance mathematisch auf einer Skala von 0 bis 1 (0 % bis 100 %).
* **Lineare Kombination:** Die Basis bildet eine lineare Gleichung: $z = \beta_0 + \beta_1 \cdot X$. Da eine Gerade jedoch gegen Unendlich läuft, benötigen wir eine Begrenzung auf den Bereich zwischen 0 und 1.
* **Sigmoid-Funktion:** Diese Funktion biegt die lineare Gerade in eine "S-Form". Die Formel lautet $p = \frac{1}{1 + e^{-z}}$. Sie komprimiert beliebige Zahlenwerte elegant in das Wahrscheinlichkeitsintervall $[0, 1]$.

### 2. Visualisierung
Um dies zu veranschaulichen, nehmen wir an, wir prognostizieren, ob ein Kunde einen Data-Science-Kurs kauft.
* **X-Achse (Feature Value):** Ein Merkmal, wie zum Beispiel die Anzahl der besuchten kostenlosen Webinare.
* **Y-Achse (Probability):** Die Kaufwahrscheinlichkeit (0 bis 1).
* **Datenpunkte:** Dies sind reale historische Daten. Rote Punkte bei $y=0$ bedeuten "kein Kauf", grüne Punkte bei $y=1$ stehen für Kunden, die den Kurs gekauft haben. Je höher der X-Wert, desto dichter gruppieren sich die grünen Punkte.
* **Die blaue S-Kurve:** Dies ist das trainierte logistische Regressionsmodell. Sie zeigt, wie die Kaufwahrscheinlichkeit mit jedem weiteren Webinar kontinuierlich ansteigt.

### 3. Funktion der Regler
Unter der URL https://www.interactive-ml.com/logistic-regression.html werden die Parameter der Gleichung manuell eingestellt:
* **Intercept (Achsenabschnitt / $\beta_0$):** Verschiebt die Kurve nach links oder rechts. Dies entspricht einer "Basis-Kaufbereitschaft", unabhängig von den Webinaren.
* **Slope (Steigung / $\beta_1$):** Reguliert die Steilheit der S-Kurve. Eine hohe Steigung bedeutet, dass das Merkmal (Webinare) die Entscheidung radikal beeinflusst. Eine flache Kurve deutet auf einen geringen Einfluss hin.
* **Threshold (Schwellenwert):** Die gestrichelte horizontale Linie. Das Modell liefert eine Wahrscheinlichkeit (z. B. 0,65), aber das Business benötigt eine klare Entscheidung. Standardmäßig liegt dieser Wert bei **0,5**. Liegt die Kurve über dem Schwellenwert, wird "Kauf" (Klasse 1) prognostiziert, ansonsten "Kein Kauf" (Klasse 0).

### 4. Performance-Metriken
Bei der Generierung neuer Datensätze ("New Data") oder der Anpassung der Regler ändern sich die Kennzahlen:
* **Accuracy (Genauigkeit):** Der Gesamtanteil der korrekten Vorhersagen.
* **Precision (Präzision):** Welcher Anteil der als Käufer prognostizierten Personen hat tatsächlich gekauft?
* **Recall (Trefferquote/Sensitivität):** Welchen Anteil der tatsächlichen Käufer konnte das Modell korrekt identifizieren?
* **Log-Loss:** Eine Kennzahl für die Bestrafung von Fehlprognosen bei hoher Sicherheit. Je niedriger dieser Wert, desto besser. Wenn das Modell sich zu 99 % sicher ist, dass ein Kauf erfolgt, dieser aber ausbleibt, steigt der Log-Loss drastisch an.

---

## English Version

### 1. Fundamental Concepts
Before adjusting the parameters on the screen, it is essential to understand the underlying principles:
* **Binary Classification:** The objective is to categorize objects into two distinct groups (e.g., "healthy" vs. "ill"). These are represented as **Class 0** (red points/negative class) and **Class 1** (green points/positive class).
* **Probability:** The model does not merely provide a "yes" or "no" answer; it mathematically estimates the likelihood on a scale from 0 to 1 (0% to 100%).
* **Linear Combination:** At its core lies a linear equation: $z = \beta_0 + \beta_1 \cdot X$. However, since a line extends to infinity and we require values between 0 and 1, a transformation is necessary.
* **Sigmoid Function:** This mathematical function transforms the linear input into an "S-shaped" curve. The formula is $p = \frac{1}{1 + e^{-z}}$. It elegantly compresses any real number into the probability range of $[0, 1]$.

### 2. Visualization Analysis
To illustrate this, consider a practical example: predicting whether a client will purchase a Data Science course.
* **X-Axis (Feature Value):** Represents a specific variable, such as the number of free webinars attended.
* **Y-Axis (Probability):** The probability of purchase (ranging from 0 to 1).
* **Data Points:** These represent historical observations. Red points at $y=0$ signify non-purchasers, while green points at $y=1$ represent those who completed a purchase. Notice that as $X$ increases, the density of green points also increases.
* **The Blue S-Curve:** This represents the trained Logistic Regression model, showing how the probability of purchase increases relative to the number of webinars attended.

### 3. Parameter Controls (Sliders)
https://www.interactive-ml.com/logistic-regression.html page demonstrates manual adjustments of the following parameters:
* **Intercept ($\beta_0$):** Shifts the curve horizontally. It represents the "baseline inclination" to purchase, independent of the feature $X$.
* **Slope ($\beta_1$):** Controls the steepness of the S-curve. A high slope indicates that the feature significantly influences the decision, while a shallow slope suggests a weak correlation.
* **Threshold:** Represented by the dashed horizontal line. While the model outputs a probability (e.g., 0.65), business decisions often require a binary outcome. By default, it is set to **0.5**. If the curve is above this threshold, the model predicts "Purchase" (Class 1); otherwise, it predicts "No Purchase" (Class 0).

### 4. Performance Metrics
As you generate "New Data" or adjust sliders, the following metrics update:
* **Accuracy:** The overall percentage of correct predictions.
* **Precision:** The ratio of true positives to all positive predictions (how many of those we predicted would buy actually did).
* **Recall:** The ratio of true positives to all actual positives (how many of the actual buyers the model successfully identified).
* **Log-Loss:** A penalty for incorrect confidence. A lower value indicates better performance. If the model predicts a 99% probability of purchase but the client does not buy, the Log-Loss increases significantly.

---