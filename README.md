# Skyforge Revival – Setup

Diese Dateien sind fertig für GitHub Pages. Zwei Dinge musst du selbst erledigen, weil sie deinen eigenen Account brauchen: **Firebase einrichten** und **auf GitHub hochladen**.

## 1. Firebase einrichten (für die Account-Registrierung)

1. Gehe zu https://console.firebase.google.com und erstelle ein neues, kostenloses Projekt.
2. Links im Menü: **Authentication** → Tab "Sign-in method" → **E-Mail/Passwort** aktivieren.
3. Links im Menü: **Firestore Database** → "Datenbank erstellen" → Production mode.
4. Zahnrad oben links → **Projekteinstellungen** → runterscrollen zu "Meine Apps" → Web-App hinzufügen (`</>`-Icon) → einen Namen vergeben → Firebase zeigt dir ein `firebaseConfig`-Objekt mit 6 Werten (apiKey, authDomain, projectId, storageBucket, messagingSenderId, appId).
5. Öffne `index.html`, suche `firebaseConfig` (ganz unten) und trage dort deine 6 Werte ein.
6. In der Firebase Console: **Firestore Database → Regeln** → den kompletten Inhalt von `firestore.rules` (liegt in diesem Ordner) einfügen und veröffentlichen.

Diese Werte sind **keine Geheimnisse** – sie dürfen im Frontend-Code stehen, die eigentliche Absicherung passiert über die Firestore-Regeln aus Schritt 6.

## 2. Auf GitHub Pages veröffentlichen

1. Auf github.com ein neues, öffentliches Repository erstellen, z. B. `skyforge-revival`.
2. Alle Dateien aus diesem Ordner hochladen (`index.html`, `firestore.rules`, `README.md`, `CNAME` – am einfachsten per Drag & Drop im Browser über "Add file → Upload files", oder per `git push`).
3. Im Repo: **Settings → Pages** → unter "Build and deployment" → Source: "Deploy from a branch" → Branch: `main`, Ordner `/root` → Speichern.
4. Nach 1–2 Minuten ist die Seite live unter `https://DEIN-GITHUB-NAME.github.io/skyforge-revival/`.

## 3. Optional: eigene Domain skyforge-revival.com

Die Datei `CNAME` ist schon vorbereitet. Damit die Domain wirklich funktioniert:

1. Domain bei einem Registrar kaufen (falls noch nicht geschehen).
2. Beim Domain-Registrar folgende DNS-Einträge setzen:
   - Für die nackte Domain (`skyforge-revival.com`): vier **A-Records** auf
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - Für `www.skyforge-revival.com` (optional): ein **CNAME-Record** auf `DEIN-GITHUB-NAME.github.io`
3. Im Repo unter **Settings → Pages** die Domain `skyforge-revival.com` eintragen und "Enforce HTTPS" aktivieren, sobald verfügbar.
4. DNS-Änderungen können bis zu 24 Stunden dauern.

## 4. Download-Bereich später aktivieren

Im Installationsbereich ist der Download-Button aktuell deaktiviert (`disabled` in `index.html`, Abschnitt `#install`). Sobald der Launcher fertig ist: Datei extern hosten (z. B. GitHub Releases – Anhänge bis 2 GB, gute Geschwindigkeit) und den Button durch einen normalen Link auf die Release-Datei ersetzen.
