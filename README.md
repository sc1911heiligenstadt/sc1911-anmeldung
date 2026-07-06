# sc1911-anmeldung (v1.0)

Digitales Anmeldesystem für Trainerversammlungen beim 1. SC 1911 Heiligenstadt. Zwei statische HTML-Seiten, kein Build-Prozess, Firebase Realtime Database als Backend.

## Dateien

### `anmeldung.html` – Öffentliches Anmeldeformular
- Wird per QR-Code aufgerufen (Link enthält `?event=<id>`)
- Teilnehmer geben Vor- und Nachname ein und melden sich für die aktuelle Versammlung an
- Abgleich mit der importierten Teilnehmerliste: Name muss (normalisiert) vorhanden sein
- Geräte-Sperre per `localStorage`: einmal angemeldet, keine erneute Anmeldung auf demselben Gerät
- Erkennt automatisch, wenn die Versammlung vom Verwalter beendet wurde, und blockiert dann weitere Anmeldungen
- Live-Aktualisierung von Veranstaltungsname/-datum über Firebase

### `verwaltung.html` – Verwaltungsoberfläche
- **QR-Code**: erzeugt automatisch den Anmeldelink als QR-Code zum Drucken/Aushängen
- **Teilnehmerliste**: Live-Tabelle mit Anwesend/Abwesend-Status, durchsuchbar und sortierbar
- **Manuell hinzufügen**: einzelne Personen direkt eintragen (z. B. ohne Smartphone)
- **Teilnehmer verwalten** (passwortgeschützt — das Passwort wird serverseitig geprüft und steht nicht im Quellcode):
  - Teilnehmer einzeln hinzufügen, bearbeiten oder löschen
  - CSV/TXT-Import einer Stammliste (robust gegen Windows-1252/UTF-8, „Vorname;Nachname“ oder voller Name)
  - CSV-Export der aktuellen Teilnehmerliste
- **Versammlungen verwalten**:
  - Neue Versammlung starten (übernimmt die letzte Teilnehmerliste, alle zunächst „abwesend“)
  - Versammlung beenden (sperrt weitere Anmeldungen, öffnet automatisch den Bericht)
  - Übersicht aller vergangenen Versammlungen mit Statistik (Anwesend/Abwesend/Quote)
  - Druckbarer Bericht je Versammlung
  - Vergleich von bis zu 4 Versammlungen (Anwesenheitsquote pro Person über mehrere Termine)
  - Versammlungen löschen

## Technik
- Kein Server, kein Build – beide Dateien direkt im Browser öffnen/hosten
- Backend: Firebase Realtime Database (Projekt `trainerversammlung`)
- Datenstruktur: `veranstaltungen/<eventId>/{meta, anmeldungen}`, aktive Versammlung in `config/activeEvent`
