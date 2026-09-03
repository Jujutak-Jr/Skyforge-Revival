
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
