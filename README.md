# 🏡 Familienplaner

Interaktiver Familienplaner für Regina, Maik, Emily & Paul — eine einzige HTML-Datei, keine Installation, keine Abhängigkeiten.

## Module

| Tab | Funktion |
|---|---|
| 📅 Woche | Wochenkalender mit Terminen (wöchentlich, täglich oder einmalig mit Datum), Personen-Zuordnung, Fahrdienst (hin/zurück) — plus abhakbare Aufgaben als abgetrennter Bereich in jedem Wochentag |
| 🍽️ Essen | Essensplan (Frühstück/Mittag/Abend) für die ganze Woche — Gerichte werden automatisch als Favoriten gemerkt und wieder vorgeschlagen |

## Bedienung

Termin, Aufgabe oder Routineschritt **antippen = bearbeiten**, **lange drücken** (oder Rechtsklick) **= Löschmenü** mit Papierkorb. Aufgaben sind Termine ohne Uhrzeit: Sie erscheinen abgetrennt unter den Terminen des Tages und lassen sich abhaken.

Unter **⚙️ Einstellungen** (oben rechts): Familie (Namen, Farben, Symbole), Routinen & Erinnerungen je Kind und Tageszeit, Kindmodus-PIN und Geräte-Sync.

## 🚀 Kindmodus

Vollbild-Ansicht für Emily und Paul — komplett ohne Lesen: große Emoji-Kacheln, Flip-Animation mit 👍 beim Abhaken, Sterne-Belohnung (⭐ +1 pro Schritt, +3 Bonus mit Konfetti, wenn alles geschafft ist). Beenden nur per 4-stelliger PIN (Standard: `1234`, änderbar über ✏️ oben rechts).

## Nutzung

`index.html` im Browser öffnen — fertig. Alle Daten bleiben lokal im Browser gespeichert (localStorage).

**Hinweis:** Erinnerungen klingeln nur, solange die Seite im Browser geöffnet ist.

## ☁️ Geräte-Sync (optional, über Firebase)

Ohne Einrichtung hat jedes Gerät seinen eigenen Stand. Für Live-Sync über alle Geräte:

1. Auf [console.firebase.google.com](https://console.firebase.google.com) ein Projekt anlegen (Google Analytics kann aus bleiben)
2. Links **Build → Realtime Database** → „Create database" → Standort z. B. `europe-west1` → **Testmodus** starten
3. Zahnrad → **Projekteinstellungen** → unter „Meine Apps" eine **Web-App** (`</>`) hinzufügen → das `firebaseConfig`-Snippet kopieren
4. Im Planer oben rechts **✏️** → bei „☁️ Geräte-Sync" das Snippet einfügen → **Verbinden**
5. Dasselbe Snippet einmalig auf jedem weiteren Gerät einfügen

Danach zeigt die Kopfzeile „☁️ synchron" und alle Geräte teilen denselben Stand in Echtzeit.

**Wichtig:** Der Testmodus läuft nach 30 Tagen ab. Danach in der Firebase-Konsole unter Realtime Database → „Rules" setzen: `".read": true, ".write": true` (bequem, aber prinzipiell öffentlich — für Familiendaten dieser Art meist okay, sensible Dinge gehören nicht in den Planer).

## Online stellen (GitHub Pages)

Repo → Settings → Pages → Branch `main` auswählen → Save. Der Planer ist danach unter `https://maikunverricht.github.io/Familienplaner/` erreichbar.
