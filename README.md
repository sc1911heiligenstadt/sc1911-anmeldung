# 🗳️ Trainerversammlung-Anmeldung

Das digitale Anmeldesystem für die **Trainerversammlungen** des 1. SC 1911
Heiligenstadt: Die Teilnehmerliste steht vorher fest, am Versammlungstag hängt
ein QR-Code aus, und wer kommt, checkt sich damit selbst am Handy ein. Die
Anwesenheitsliste ist dadurch sofort fertig.

> ⚠️ **Nicht** die Nachwuchs-Anmeldung. Neue Jugendspieler werden über
> [Anmeldung Nachwuchs](https://sc1911heiligenstadt.github.io/vereinsverwaltung/nachwuchs.html)
> im Repo `vereinsverwaltung` angemeldet.

**➡️ [Verwaltung öffnen](https://sc1911heiligenstadt.github.io/sc1911-anmeldung/verwaltung.html)**

## Seiten

| Seite | Wofür |
|---|---|
| [Anmeldung](https://sc1911heiligenstadt.github.io/sc1911-anmeldung/anmeldung.html) | Die Eincheck-Seite für die Teilnehmer — ohne Konto, aufgerufen über den QR-Code der Versammlung |
| [Verwaltung](https://sc1911heiligenstadt.github.io/sc1911-anmeldung/verwaltung.html) | Versammlungen anlegen, Teilnehmerliste pflegen, QR-Code aushängen, Anwesenheit verfolgen und auswerten |

Die Anmeldeseite ist ohne den Link aus der Verwaltung nicht sinnvoll zu
benutzen: Sie braucht die Kennung der Versammlung aus dem QR-Code und sagt sonst,
dass der Link fehlt.

## Am Versammlungstag

1. In der **Verwaltung** steht die aktive Versammlung. Ihr QR-Code lässt sich
   einblenden, als Bild speichern oder ausdrucken und am Eingang aushängen.
2. Die Teilnehmer scannen den Code **mit dem eigenen Handy**, tragen Vor- und
   Nachnamen ein und sind damit als anwesend eingecheckt — mit Uhrzeit.
3. Wer nicht auf der Liste steht, kommt so nicht hinein und bekommt den Hinweis,
   sich beim Trainer zu melden. Für diese Fälle gibt es in der Verwaltung
   **Manuell hinzufügen**: die Person wird direkt als anwesend nachgetragen,
   nur für diese eine Versammlung.

Damit sich niemand versehentlich doppelt einträgt, merkt sich das Handy die
eigene Anmeldung. Ein zweiter Versuch mit demselben Namen meldet, wann die
Person bereits eingecheckt hat. Ist die Versammlung beendet, nimmt die Seite
keine Anmeldung mehr an.

## Was die Verwaltung kann

- **Teilnehmerliste** — aktualisiert sich live bei jedem Einchecken. Sortierbar,
  und die Anwesenheit lässt sich für jede Person auch von Hand auf anwesend oder
  abwesend stellen. Einträge sind nachträglich zu korrigieren oder zu löschen.
- **Teilnehmer verwalten** — Namen einzeln hinzufügen oder eine ganze Liste aus
  einer CSV- oder Textdatei importieren. Der Import erkennt Umlaute auch dann
  richtig, wenn die Datei aus Excel in der alten Windows-Kodierung kommt.
- **Versammlungen** — eine neue Versammlung mit Name und Datum starten, ohne die
  alte Liste zu verlieren; frühere Versammlungen ansehen, ihren Bericht drucken
  oder sie löschen. Eine laufende Versammlung lässt sich beenden, danach ist kein
  Einchecken mehr möglich.
- **Vergleich** — mehrere Versammlungen nebeneinanderstellen und sehen, wer wann
  da war.
- **Export** — Liste als CSV für Excel oder als Druckansicht, dazu der Bericht
  einer einzelnen Versammlung.

## Zugang

Die **Anmeldeseite braucht kein Konto** — der QR-Code genügt. Einchecken kann
sich aber nur, wer schon auf der Teilnehmerliste der Versammlung steht.

Die **Verwaltung** ist mit einem eigenen Passwort geschützt, nicht über das
Vereinskonto. Das Passwort wird serverseitig geprüft und steht nicht im
Quellcode.

## Lokal starten

Über den Eintrag `sc1911-anmeldung` in `E:\.claude\launch.json` — der Server läuft dann auf `http://localhost:8774/`.

## Technik

Vanilla JavaScript ohne Build-Schritt — die Dateien werden so ausgeliefert, wie sie im Repo liegen. Veröffentlicht über GitHub Pages. Die Live-Daten liegen in einer Firebase-Datenbank, damit mehrere Geräte denselben Stand sehen.

Die QR-Bibliothek wird erst geladen, wenn wirklich ein Code erzeugt wird — beim
Aufrufen der Seite kostet sie nichts.

---

Ein Werkzeug des 1. SC 1911 Heiligenstadt. Alle Werkzeuge auf einen Blick: [Tools-Übersicht](https://sc1911heiligenstadt.github.io/ToolsUebersicht/) · Erklärungen im [Toolbox Wiki](https://sc1911heiligenstadt.github.io/Vereinswiki/).
