# Anleitung: Deine Kräuter-App aufs Handy bringen

**Ohne Programmieren. Zeitaufwand: ca. 30–60 Minuten.**

Du hast 5 Dateien bekommen:

| Datei | Was sie tut |
|---|---|
| `index.html` | die App selbst (mit allen 14 Monographien) |
| `manifest.json` | macht sie zur installierbaren App (Name, Icon, Vollbild) |
| `sw.js` | macht sie **offline-fähig** |
| `icon-192.png` | App-Icon |
| `icon-512.png` | App-Icon (groß) |

**Wichtig:** Alle 5 Dateien müssen zusammen in **einem** Ordner liegen, ohne Unterordner.

---

## Warum nicht einfach die Datei aufs Handy kopieren?

Damit die App offline funktioniert und ein eigenes Icon bekommt, muss sie einmal über eine **https-Adresse** geladen werden. Das klingt kompliziert, ist aber kostenlos und dauert 10 Minuten. Danach brauchst du nie wieder Internet.

---

## Weg A: GitHub Pages (empfohlen — dauerhaft & kostenlos)

### Schritt 1 — Konto anlegen
1. Auf **github.com** gehen → **Sign up**
2. E-Mail, Passwort, Benutzername wählen → Konto bestätigen
3. Kostenloser Plan reicht vollkommen

### Schritt 2 — Projekt (Repository) anlegen
1. Oben rechts auf **+** → **New repository**
2. **Repository name:** `herbarium` (oder ein anderer Name)
3. **Public** auswählen ⚠️ (bei "Private" funktioniert GitHub Pages im Gratis-Plan nicht)
4. Unten auf **Create repository**

### Schritt 3 — Die 5 Dateien hochladen
1. Im neuen Repository auf **uploading an existing file** klicken
   (oder: **Add file** → **Upload files**)
2. Alle **5 Dateien** per Drag & Drop in das Feld ziehen
3. Unten auf **Commit changes**

### Schritt 4 — Website aktivieren
1. Oben im Repository auf **Settings**
2. Links in der Seitenleiste auf **Pages**
3. Unter *Source*: **Deploy from a branch**
4. Unter *Branch*: **main** auswählen, Ordner **/ (root)**, dann **Save**
5. **1–2 Minuten warten**, Seite neu laden — oben erscheint deine Adresse:
   `https://DEINBENUTZERNAME.github.io/herbarium/`

### Schritt 5 — Auf dem Handy installieren
1. Diese Adresse in **Chrome auf deinem Android-Handy** öffnen
2. Chrome-Menü (⋮ oben rechts) → **App installieren**
   (oder: *Zum Startbildschirm hinzufügen*)
3. Fertig — das Herbarium-Icon liegt auf deinem Startbildschirm

### Schritt 6 — Offline testen
1. App einmal öffnen (damit sie sich speichert)
2. **Flugmodus einschalten**
3. App öffnen → alles funktioniert weiterhin ✓

---

## Weg B: Netlify Drop (schneller zum Ausprobieren)

Wenn du es erst mal nur testen willst:

1. Auf **app.netlify.com/drop** gehen
2. Den **Ordner mit den 5 Dateien** in das Feld ziehen
3. Du bekommst sofort eine Adresse — fertig

*Nachteil:* Ohne Konto verfällt die Adresse nach einiger Zeit. Für dauerhaft → Weg A.

---

## Die App benutzen

**Unten die 5 Reiter:**

- **Start** — Übersicht + was diesen Monat erntereif ist
- **Nutzen** — Symptom eingeben („Halsschmerzen") → passende Kräuter, nach Evidenz sortiert
- **Ernte** — Monat wählen → was ist fällig
- **Register** — Verwechslungen, Toxine, Interaktionen, Korbblütler, Kontraindikationen
- **Katalog** — alle Monographien, Suche, Import/Sicherung

**In jeder Monographie:** Feld · Monographie · Praxis · Garten · **Notizen** (deine eigenen Notizen und Fotos — bleiben dauerhaft auf dem Gerät).

---

## Neue Kräuter hinzufügen (ohne die App neu zu bauen)

Das ist der Punkt, der dir wichtig war:

1. In der App auf **Katalog** → **⬆ Import (JSON)**
2. Eine `monographie-XYZ.json` auswählen
3. Fertig — sie ist sofort in der Sammlung und bleibt dauerhaft gespeichert

Die App versteht **beide** Formate: die ausführlichen `monographie-*.json`-Dateien und ihr eigenes Exportformat. Du musst also nichts umbauen — einfach die JSON-Datei importieren, die du (oder wir gemeinsam) erstellt hast.

**Sichern:** Katalog → **⬇ Sichern** speichert deine importierten Kräuter *und* alle Notizen/Fotos in eine Datei. Bewahre die auf, falls du das Handy wechselst.

---

## Häufige Stolpersteine

**„App installieren" erscheint nicht im Chrome-Menü**
→ Die Seite muss über `https://` geladen sein (nicht als lokale Datei) und alle 5 Dateien müssen im selben Ordner liegen. Prüfe, ob `manifest.json` und `sw.js` wirklich hochgeladen wurden.

**Offline geht nicht**
→ Die App einmal *online* öffnen und ein paar Sekunden warten (der Service Worker speichert sich dann). Danach klappt es.

**Nach einem Update sehe ich die alte Version**
→ App schließen, Chrome-Menü → Seite neu laden. Der Service Worker holt die neue Version beim nächsten Start.

**Fotos verschwinden**
→ Nicht die „Website-Daten" von Chrome löschen — dort liegen deine Notizen. Regelmäßig **⬇ Sichern** nutzen.

---

## Und später eine „echte" App im Play Store?

Falls du das irgendwann willst: Eine PWA lässt sich mit einem Werkzeug namens **Bubblewrap** in eine echte Android-APK verpacken. Die Arbeit von jetzt ist dann **nicht verloren** — die App bleibt dieselbe, sie bekommt nur eine andere Hülle. Aber für den privaten Gebrauch brauchst du das nicht.
