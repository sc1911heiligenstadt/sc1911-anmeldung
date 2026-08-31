# 🗳️ Trainerversammlung-Anmeldung

Das digitale Anmeldesystem für die **Trainerversammlungen** des 1. SC 1911
Heiligenstadt: Wer kommt, meldet sich über ein offenes Formular an; am
Versammlungstag wird per QR-Code eingecheckt, und die Teilnehmerliste steht
sofort.

> ⚠️ **Nicht** die Nachwuchs-Anmeldung. Neue Jugendspieler werden über
> [Anmeldung Nachwuchs](https://sc1911heiligenstadt.github.io/vereinsverwaltung/nachwuchs.html)
> im Repo `vereinsverwaltung` angemeldet.

**➡️ [Anmeldung öffnen](https://sc1911heiligenstadt.github.io/sc1911-anmeldung/anmeldung.html)**

## Seiten

| Seite | Wofür |
|---|---|
| [Anmeldung](https://sc1911heiligenstadt.github.io/sc1911-anmeldung/anmeldung.html) | Das offene Anmeldeformular — ohne Konto ausfüllbar |
| [Verwaltung](https://sc1911heiligenstadt.github.io/sc1911-anmeldung/verwaltung.html) | Teilnehmerliste, **Scannen zum Anmelden** per QR-Code und **Manuell hinzufügen** für alle, die spontan kommen |

## Am Versammlungstag

Die Verwaltungsseite kann den QR-Code einer Anmeldung **scannen** und die Person
damit als anwesend führen. Wer ohne Anmeldung erscheint, wird über **Manuell
hinzufügen** nachgetragen — die Liste bleibt vollständig, ohne dass jemand
nachträglich Papier abtippt.

## Zugang

Das **Anmeldeformular ist offen**, damit sich jede:r ohne Konto anmelden kann.
Die **Verwaltung** dahinter ist mit einem eigenen Passwort geschützt, nicht über
das Vereinskonto.

## Lokal starten

Über den Eintrag `sc1911-anmeldung` in `E:\.claude\launch.json` — der Server läuft dann auf `http://localhost:8774/`.

## Technik

Vanilla JavaScript ohne Build-Schritt — die Dateien werden so ausgeliefert, wie sie im Repo liegen. Veröffentlicht über GitHub Pages. Die Live-Daten liegen in einer Firebase-Datenbank, damit mehrere Geräte denselben Stand sehen.

Die QR-Bibliothek wird erst geladen, wenn wirklich ein Code erzeugt wird — beim
Aufrufen der Seite kostet sie nichts.

---

Ein Werkzeug des 1. SC 1911 Heiligenstadt. Alle Werkzeuge auf einen Blick: [Tools-Übersicht](https://sc1911heiligenstadt.github.io/ToolsUebersicht/) · Erklärungen im [Toolbox Wiki](https://sc1911heiligenstadt.github.io/Vereinswiki/).
