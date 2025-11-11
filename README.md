# pH-Sorter.github.io
pH Sorter Documentation

German Version
# 🧪 pH-Sorter – Mettler Toledo SevenDirect CSV Processor

Dieses Web-Tool automatisiert die Nachbearbeitung von pH-Messungen aus dem **Mettler Toledo SevenDirect pH-Meter**.  
Das Gerät exportiert jede Messung als **einzelne CSV-Datei**, was die Auswertung und Archivierung schnell unübersichtlich macht.  
Der **pH-Sorter** kombiniert diese Einzeldateien automatisch in eine saubere Excel-Tabelle und benennt die Dateien konsistent um.

---

## Funktionsweise

1. Jede Messung des SevenDirect wird als CSV gespeichert, z. B.:

   Sample ID,"3"
   Measurement result,"2.34 pH"
   Result status,"OK*"

2. Das Tool liest beliebig viele dieser CSV-Dateien im Browser ein.
3. Es prüft:
   - Dateien mit `Sample ID = "---"` → werden **ignoriert / gelöscht**
   - Dateien mit `Result status = "Fehler"` → werden **ignoriert / gelöscht**
4. Für alle übrigen Messungen wird:
   - die Datei in `SampleID.csv` umbenannt
   - der pH-Wert extrahiert
   - eine Excel-Tabelle `pH_summary.xlsx` erzeugt mit den Spalten: Sample ID, pH
5. Anschließend lädt der Browser automatisch ein ZIP-Archiv herunter mit:
   - allen umbenannten CSVs
   - der Excel-Zusammenfassung `pH_summary.xlsx`

---

## Verwendung

1. Seite öffnen: https://tintin353.github.io/dataextractor.github.io/
2. CSV-Dateien auswählen.
3. „Auswerten“ klicken.
4. Ergebnis: `ph_sorter_output.zip` wird heruntergeladen.

---

## Beispielausgabe

ph_sorter_output.zip  
├── 3.csv  
├── 4.csv  
├── 5.csv  
└── pH_summary.xlsx

| Sample ID | pH |
|------------|----|
| 3 | 2.34 |
| 4 | 7.02 |
| 5 | 5.68 |

---

## Datenschutz & Kompatibilität

- Lokale Verarbeitung, keine Internetübertragung.
- Läuft auf Windows, macOS, Linux mit Chrome, Edge, Firefox, Safari.

---

## Hintergrund

Das Mettler Toledo SevenDirect pH-Meter exportiert jede Messung als separate CSV-Datei.  
Dieses Tool vereinfacht die Zusammenfassung und Organisation der Daten im Labor.

---

**Laurin Tempel**  
Institut für Bodenkunde und Bodenerhaltung, JLU Gießen  
2025

 
English Version
# 🧪 pH-Sorter – Mettler Toledo SevenDirect CSV Processor

This web tool automates the post-processing of pH measurements from the **Mettler Toledo SevenDirect pH Meter**.  
The device exports each measurement as an **individual CSV file**, which can make data handling and analysis cumbersome.  
The **pH-Sorter** automatically combines these files into a clean Excel summary and renames them consistently.

---

## How it Works

1. Each measurement from the SevenDirect is saved as a CSV file, e.g.:

   Sample ID,"3"  
   Measurement result,"2.34 pH"  
   Result status,"OK*"

2. The tool reads multiple CSV files in the browser.
3. It checks:
   - Files with `Sample ID = "---"` → **ignored / deleted**
   - Files with `Result status = "Fehler"` → **ignored / deleted**
4. For valid measurements, it:
   - renames files as `SampleID.csv`
   - extracts the pH value
   - creates an Excel file `pH_summary.xlsx` containing Sample ID and pH
5. The browser downloads a ZIP archive containing:
   - all renamed CSVs
   - the summary file `pH_summary.xlsx`

---

## Usage

1. Open: https://tintin353.github.io/dataextractor.github.io/
2. Select CSV files.
3. Click **"Auswerten" (Evaluate)**.
4. The browser downloads `ph_sorter_output.zip`.

---

## Example Output

ph_sorter_output.zip  
├── 3.csv  
├── 4.csv  
├── 5.csv  
└── pH_summary.xlsx

| Sample ID | pH |
|------------|----|
| 3 | 2.34 |
| 4 | 7.02 |
| 5 | 5.68 |

---

## Privacy & Compatibility

- All processing is done locally in the browser.
- No data is uploaded or transmitted.
- Works on Windows, macOS, and Linux using Chrome, Edge, Firefox, or Safari.

---

## Background

The **Mettler Toledo SevenDirect pH Meter** exports each measurement as a separate CSV file.  
This tool was created to simplify data organization and analysis in laboratory workflows.

---

**Laurin Tempel**  
Institute for Soil Science and Soil Conservation, JLU Gießen  
2025


