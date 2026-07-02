# Prüfanleitung Fehlersuche Motor & Elektronik
**Autohaus Stieber GmbH · Digitale Werkstatt-Checkliste · Stand: 02.07.2026 (Version 6)**

---

## 1. Was ist das?

Die digitale Version des Papier-Bogens „Fehlersuche Motor & Elektronik" (V02072026). Techniker und Meister füllen die Prüfanleitung direkt am PC, Handy oder iPad aus. Alle Eingaben werden automatisch zentral in der Datenbank gespeichert – jeder im Team sieht denselben Stand.

**Live-Adresse (auf allen Geräten als Lesezeichen speichern):**

> **https://stioli.github.io/stieber-pruefanleitung-fehlersuche/**

Tipp fürs iPad/Handy: Seite in Safari/Chrome öffnen → „Zum Home-Bildschirm hinzufügen" – dann startet sie wie eine App.

---

## 2. Bedienung (Kurzanleitung für die Werkstatt)

### Neue Prüfung starten
1. Oben rechts **„＋ Neue Prüfung"** antippen.
2. Kopfdaten ausfüllen: **Kunde, Fahrzeug, Kennzeichen, km-Stand, Auftragsnummer, Datum, FIN** und die **Kundenbeanstandung**. Felder mit rotem Stern (*) sind Pflicht.

### Prüfschritte abarbeiten
- Jeder Schritt wird mit **„✓ OK"** oder **„✗ nicht OK"** bewertet und mit dem **Namen** des Bearbeiters versehen.
- Schritte mit rotem **PFLICHT**-Etikett müssen bewertet sein, sonst lässt sich der Bericht nicht abschließen.
- Unter **„Details"** bei jedem Schritt: Fehlercode, Bemerkung und **Fotos** (direkt mit der Kamera aufnehmen).
- **Schritt 3:** Tabelle für ausgelesene Fehlercodes (DTC) mit Code, Steuergerät, Fehlertext, statisch/sporadisch.
- **Schritt 13 (Bauteileprüfung):** 5 Zeilen zum selbst Benennen mit **Soll- und Ist-Wert**. Mindestens eine Zeile muss vollständig ausgefüllt sein (Pflicht). Weitere Zeilen: einfach 13.1–13.5 nutzen.
- **Schritt 14 (Befund)** und **Schritt 15 (Auftrag schreiben)**: große Textfelder für Befund bzw. Suchzeiten/Reparaturzeiten/Material.

### Abschließen
1. Unten bei **„Freigabe & Abschluss"** Techniker und Meister mit Datum eintragen.
2. **„✅ Als erledigt abschließen"** – nur möglich, wenn alle Pflichtfelder erledigt sind. Fehlt etwas, zeigt ein Fenster genau an, was noch offen ist, und springt dorthin.
3. Der Fortschrittsbalken unten zeigt jederzeit den Stand der Pflichtfelder.

### Zwischenspeichern & Fortsetzen
- Es wird **automatisch gespeichert** (bei jeder Eingabe).
- Über **„📋 Prüfungen"** oben öffnet sich die Liste aller Prüfungen – dort eine antippen, um weiterzuarbeiten. Status: „In Arbeit" (gelb) oder „Erledigt" (grün).

### Mitarbeiter verwalten
- Über **„👥 Mitarbeiter"**: Namen selbst anlegen, umbenennen, löschen (Rollen: Techniker, Meister, Serviceberater, Azubi). Die Namen erscheinen sofort in allen Auswahlfeldern – auf allen Geräten.

### Sprache Deutsch / Türkisch
- Button **„TR Türkçe"** oben schaltet die komplette Oberfläche auf Türkisch um (und zurück über „DE Deutsch"). Die Auswahl wird pro Gerät gemerkt.
- **Ausdruck/PDF erfolgt immer auf Deutsch**, egal welche Sprache eingestellt ist.

### PDF / Drucken
- **„🖨️ PDF / Drucken"** öffnet die Druckansicht – als PDF speichern und zum Auftrag legen.

### Verbindungsstatus
- Grüner Banner „☁️ Mit der Datenbank verbunden" = alles wird zentral gespeichert.
- Orangener Banner = keine Verbindung; Eingaben werden lokal gespeichert und bei der nächsten Änderung automatisch übertragen.

---

## 3. Technik (für Oli / Administration)

| Baustein | Details |
|---|---|
| **Live-Hosting** | GitHub Pages, Repo `Stioli/stieber-pruefanleitung-fehlersuche`, Branch `main`, Datei `index.html` |
| **GitHub-Repo** | https://github.com/Stioli/stieber-pruefanleitung-fehlersuche |
| **Datenbank** | Supabase-Projekt `fahrzeug-ankauf-automation` (mnglpqeqmoxccqnztqez, eu-central-1) |
| **Tabellen** | `fs_pruefungen` (kompletter Bericht als JSON + Suchspalten Kennzeichen/Auftrag/Status) und `fs_mitarbeiter` (Name, Rolle) |
| **OneDrive-Ablage** | `Autohaus Stieber\KI\Claude\Projekte\Pruefanleitung-Fehlersuche\` (index.html + diese Anleitung) |
| **Zugriff** | Öffentliche URL ohne Login (Namensauswahl statt Passwort). URL nur intern weitergeben! |

**Änderungen einspielen:** Datei `index.html` anpassen → in OneDrive-Ordner ablegen → im GitHub-Repo committen und pushen → GitHub Pages aktualisiert die Live-Seite automatisch nach 1–2 Minuten. (Oder einfach Claude bitten – die Änderung wird dann überall gleichzeitig eingespielt.)

**Datenauswertung:** Alle abgeschlossenen Prüfungen liegen in Supabase (Tabelle `fs_pruefungen`, Spalte `daten` enthält den kompletten Bericht inkl. Messwerten und Fotos). Auswertungen/Exporte sind jederzeit möglich.

---

## 4. Versionshistorie

| Version | Änderung |
|---|---|
| V1 | Grundversion: 26 Prüfschritte, Pflichtfelder, Fotos, DTC-Tabelle, PDF-Export |
| V2 | OK/nicht-OK-Auswahl statt Haken; Bauteileprüfung 13.1–13.5 mit Soll/Ist |
| V3 | Sprachumschaltung Deutsch/Türkisch, Ausdruck fest Deutsch |
| V4 | Übersicht als Popup; Schritte zusammengefasst (14 Befund, 15 Auftrag schreiben); neue Zeile 21 „Fehlerspeicher nach Reparatur auslesen" |
| V5 | Supabase-Anbindung: zentrale Speicherung mit Offline-Fallback; GitHub Pages live |
| V6 | Neues Pflichtfeld „Kunde"; neue Reihenfolge der Kopfdaten |

Bei Fragen oder Änderungswünschen: einfach bei Claude melden.
