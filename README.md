#  QS-Dashboard Nockenwelle | Datenanalyse & Ursachenforschung (Q1 2026)

Ein interaktives Power BI-Dashboard zur Überwachung von Fertigungsqualitäten, Ausschussquoten und zur tiefgehenden prozessseitigen Ursachenanalyse in der Nockenwellenproduktion.

## Projektziel & Business-Kontext

In der industriellen Serienfertigung von Nockenwellen ist die Einhaltung enger Toleranzen bei Härte- und Rissprüfungen entscheidend für die Bauteilintegrität. Dieses Projekt demonstriert, wie unstrukturierte Qualitätsdaten automatisiert aufbereitet werden können, um:
1. Qualitäts-KPIs (Prüfmengen, Ausschussquoten) abteilungsübergreifend transparent zu machen.
2. Prozessabweichungen auf Maschinenebene (Maschine 22 vs. Maschine 34) frühzeitig zu identifizieren.
3. physikalische Ursachenketten*durch die Verknüpfung von Qualitäts- und Prozessparametern (z. B. Konzentration des Abschreckmediums) datengetrieben nachzuweisen.


## Dashboard-Übersicht (Screenshots)

1. Startseite / Globales KPI-Board
Zentraler Einstiegspunkt mit intuitiver Kachelnavigation und den wichtigsten Kernmetriken (Gesamtprüfmenge, Gesamtausschuss sowie maschinenspezifische Aufteilung).
![Startseite](<img width="1920" height="1032" alt="START" src="https://github.com/user-attachments/assets/aee69a0f-e17e-49e3-b21b-24d4bd9b57c9" />)


### 2. Prozess-Ebene: Härteprüfung (Stichprobe)
Detaillierte Analyse der Härtefehler (Max-Wert überschritten vs. Min-Wert unterschritten), aufgeteilt nach Monaten, Schichten und Prüfern samt methodischer Hinweisboxen.
![Härteprüfung](<img width="1920" height="1032" alt="Härteprüfung" src="https://github.com/user-attachments/assets/2ebc3109-2771-4c86-883a-e3a87a3ae838" />)

3. Analytische Ebene: Maschinenvergleich & Ursachenanalyse
Das Herzstück des Dashboards – eine Korrelationsanalyse zwischen den Ausschussquoten und der chemischen Konzentration des Abschreckmediums.
![Ursachenanalyse](<img width="1920" height="1032" alt="M22   M34 Vergleich" src="https://github.com/user-attachments/assets/92834a38-efca-4a98-bcb8-6a3bf0690916" />)


## Analytischer Case-Study: Root Cause Analysis (M34)

Das Dashboard liefert über den reinen Status-Quo hinaus eine strukturierte Ursachenanalyse für ein reales Fertigungsproblem im ersten Quartal:

JANUAR — Kritischer Ausgangspunkt : Konzentration Ø 4,4% (deutlich unter Soll-Min 5%). Die Abschreckwirkung war zu stark,  das Abschreckmedium verhielt sich nahezu wie reines Wasser. Ergebnis: höchster Ausschuss im Quartal — Härte 9,09%, Riss 5,04%. Die zu schnelle Abkühlung führte zu Härteüberschreitungen und thermischen Spannungen, die Mikrorisse begünstigten.

FEBRUAR — Erste Verbesserung, aber noch unzureichend Konzentration steigt auf Ø 5,2% — knapp im Soll, aber noch nahe der unteren Grenze.  Der Ausschuss sinkt spürbar (Härte 8,50%, Riss 3,30%), bleibt aber weiterhin über dem  Zielwert. Das zeigt: schon eine kleine Konzentrationssteigerung wirkt sich direkt auf  die Bauteilqualität aus — der Zusammenhang ist eindeutig.

MÄRZ — Stabilisierung im Sollbereich : Konzentration erreicht Ø 5,9%, näher an der Mitte des Sollbereichs (5–8%).  Der Ausschuss sinkt weiter auf Härte 6,36% und Riss 2,76% — der bisher beste Wert  im Quartal. Dieser Trend bestätigt: mit stabiler Konzentration im Sollbereich sinkt  die Ausschussquote kontinuierlich.

Kernaussage: Zwischen Januar und März steigt die Ø Polymerkonzentration von 4,4% auf 5,9%  (+34%) — im gleichen Zeitraum sinkt der Härte-Ausschuss von 9,09% auf 6,36%  (-30%) und der Riss-Ausschuss von 5,04% auf 2,76% (-45%). Die Daten zeigen eine  klare inverse Korrelation: Je näher die Konzentration am Sollbereich liegt,  desto niedriger die Ausschussquote.

Empfehlung: Konzentration konsequent auf Zielwert 6,5% ± 0,5% halten (Mitte des Sollbereichs),  nicht nur knapp über der unteren Grenze. Tägliche Kontrolle und sofortige  Nachdosierung bei Unterschreitung von 5,5% — bevor die Grenze von 5,0% erreicht wird.

##  Technische Umsetzung & Datenmodellierung

* Architektur: Power BI Desktop / Datenmodellierung über Sternschema.
* Sprachen & Tools: 
* DAX (Data Analysis Expressions): Erstellung von zeitintelligenten Measures (Time Intelligence) für monatliche Vergleiche, dynamische Ausschussquotenberechnung und aggregierte KPI-Karten.
* Power Query (M-Code): ETL-Prozess zur Bereinigung von Schichtbüchern, automatisierter Datentyp-Konvertierung und Zusammenführung von Prüfprotokollen.
* Visualisierung Best Practices: Striktes, einheitliches Farbkonzept (Violett für Mengen, Rot/Orange für Ausschuss), klare visuelle Trennung von Stichproben- und Vollprüfungen sowie nahtlose User Experience durch konsistente Navigations-Buttons.

##  Repository-Struktur

```
├── screenshots/               # Enthält die Dashboard-Bilder für dieses README
├── QS_Dashboard_Welle.pbit    # Die datenfreie Power BI-Vorlage zur Code-Einsicht
├── .gitignore                 # Blockiert den Upload lokaler Excel-Quellen und Datencaches
└── README.md                  # Projekt-Dokumentation
