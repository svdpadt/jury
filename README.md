# Juryvoorzitter KNKV

Een mobiele webapp voor de juryvoorzitter bij een korfbalwedstrijd. De app werkt rechtstreeks in Safari op iPhone en iPad en kan via GitHub Pages worden gepubliceerd.

## Bestanden

Plaats deze bestanden samen in de hoofdmap van de repository:

- `index.html`
- `service-worker.js`
- `manifest.webmanifest`
- `icon-192.png`
- `icon-512.png`

## Publiceren met GitHub Pages

1. Upload de bestanden naar een GitHub-repository.
2. Open **Settings > Pages**.
3. Kies bij **Build and deployment** voor **Deploy from a branch**.
4. Selecteer de branch `main` en de map `/ (root)`.
5. Open de door GitHub Pages getoonde HTTPS-link.

## Gebruiken op iPhone of iPad

1. Open de GitHub Pages-link in Safari.
2. Tik op **Deel**.
3. Kies **Zet op beginscherm**.
4. Start de app voortaan via het KNKV-pictogram.

## Schermindeling

- **iPhone staand:** klok over de volle breedte, teams naast elkaar.
- **iPhone liggend:** compacte wedstrijdtafel met drie kolommen.
- **iPad staand:** klok bovenaan, teams daaronder.
- **iPad liggend:** drie kolommen voor optimaal gebruik van de breedte.
- De schermranden van iPhones en iPads met een notch of afgeronde hoeken worden via safe-area-instellingen gerespecteerd.

## Belangrijkste functies

- Score, wedstrijdklok, rust en verlenging
- Time-outs, wissels en kaarten
- Beginopstelling en reserves
- Wedstrijdlog en CSV-export
- Automatisch lokaal bewaren in de browser
- Offline gebruik nadat de app eenmaal volledig is geladen

## Bijwerken

Na een wijziging aan de app moet de cacheversie in `service-worker.js` worden verhoogd. Daardoor ontvangen iPhone en iPad de nieuwste bestanden in plaats van een oudere offline versie.

Huidige versie: **2.6**.
