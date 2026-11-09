# Korfbal Jury PWA

## Publiceren
Plaats alle bestanden samen op een HTTPS-webserver. Geschikte opties zijn GitHub Pages, Cloudflare Pages, Netlify of een eigen HTTPS-host.

Een service worker werkt niet via een los `file://`-bestand. Test lokaal via een webserver, bijvoorbeeld:

    python3 -m http.server 8080

Open daarna `http://localhost:8080/korfbal-jury-pwa/` op dezelfde computer.

## Installeren op iPad
1. Open de HTTPS-URL in Safari.
2. Tik op Delen.
3. Kies 'Zet op beginscherm' / 'Voeg toe aan beginscherm'.
4. Schakel 'Open als webapp' in als deze optie wordt getoond.
5. Tik op Voeg toe.

De app bewaart stand, time-outs, wissels, namen, log en thema lokaal op het apparaat. De klok wordt om veiligheidsredenen gepauzeerd hersteld na volledig afsluiten.

## Cache bij updates
Wijzig in `service-worker.js` de waarde `korfbal-jury-v1` naar bijvoorbeeld `korfbal-jury-v2` wanneer je een nieuwe versie publiceert.

## Versleutelde opslag
Deze versie gebruikt AES-256-GCM via Web Crypto. De sleutel wordt met PBKDF2-SHA-256 uit een pincode afgeleid, met een willekeurige salt van 16 bytes en 250.000 iteraties. Iedere opslag gebruikt een nieuwe IV van 12 bytes. De pincode en sleutel worden niet opgeslagen. Publiceer via HTTPS.

## Versie 3 wijzigingen
- Het wedstrijdlog bevat uitsluitend doelpunten, wissels en time-outs.
- TIME-OUT en WISSEL stoppen de wedstrijdklok automatisch. De klok wordt alleen handmatig hervat.
- Elk team begint met 8 wisselbolletjes. Vanaf de 9e, 10e en iedere volgende wissel verschijnt automatisch een extra rood bolletje.

## Versie 4 wijzigingen
- Gele kaart op rugnummer met geel bolletje en afteltimer van 4 minuten.
- Rode kaart op rugnummer met rood bolletje en afteltimer van 8 minuten.
- Kaarttimers lopen alleen wanneer de wedstrijdklok loopt en pauzeren tegelijk met de wedstrijdklok.
- Kaarten worden opgenomen in het wedstrijdlog en de export.
- Meerdere kaarttimers kunnen gelijktijdig actief zijn.

## Versie 5 wijzigingen
- Wissels en kaarten worden per team via eigen knoppen en pop-ups geregistreerd.
- In elke pop-up staat eerst de wisselregistratie en daarna de kaartregistratie; de gekozen knop opent direct het juiste onderdeel.
- Een toegekend doelpunt (+1) stopt de wedstrijdklok. Een scorecorrectie (-1) beïnvloedt de klok niet.
- De spatiebalk start en stopt de wedstrijdklok, behalve tijdens invoer of wanneer een pop-up/vergrendelscherm openstaat.

## Versie 5.1 correctie
- JavaScript-syntaxisfout in de teamselectie verwijderd voor Microsoft Edge en andere browsers.

## Versie 5.2 correctie
- De spatiebalk bedient rechtstreeks uitsluitend START/STOP van de wedstrijdklok.
- De spatiebalk activeert geen score-, wissel-, kaart-, time-out- of andere knop, ook niet wanneer een knop eerder focus had.
- In tekst- en numerieke invoervelden en bij geopende registratie- of vergrendelpop-ups wordt spatie genegeerd.

## Versie 6 wijzigingen
- Directe tijdcorrectie met -10, -1, +1 en +10 seconden.
- Knop RESET TIJD naast de tijdsbediening.
- RUST opent een pop-up voor minuten en seconden, stopt de wedstrijdklok en start een aparte rusttimer.
- Tijdens rust kan RESET TIJD, of de beveiligde resetknop, de rust onmiddellijk beëindigen en de klok voor de tweede helft klaarzetten.
- Bij beëindiging van de rust wordt automatisch 2e helft geselecteerd en de ingestelde speelduur hersteld.

## Versie 6.1 correctie
- Tijdcorrectie met -10, -1, +1 en +10 seconden wijzigt uitsluitend de weergegeven tijd.
- Als de klok loopt, blijft hij lopen. Als de klok stilstaat, blijft hij stilstaan.
- De tijdcorrectie roept geen START, STOP, doelpunt of andere wedstrijdactie aan.

## Versie 6.2 wijziging
- De aparte RESET TIJD-knop is verwijderd.
- De voormalige HERSTEL-knop heet nu RESET TIJD en moet tijdens de wedstrijd 2 seconden ingedrukt worden gehouden.
- RESET TIJD stopt de wedstrijdklok en zet de wedstrijdtijd terug naar de ingestelde speelduur.
- Tijdens RUST beëindigt RESET TIJD de rust direct en zet de klok klaar voor de tweede helft.

## Versie 6.3 wijziging
- LICHT/DONKER, VERGRENDEL en PIN WIJZIGEN zijn naar de onderzijde van de app verplaatst.
- Onder de app is een subtiel KNKV-watermerk toegevoegd. Het logo wordt van een externe bron geladen en vereist voor de afbeelding internettoegang; de appfuncties zelf blijven offline beschikbaar.

## Versie 6.4 wijziging
- Het wedstrijdlog bevat uitsluitend vier wedstrijdmomenten: Start wedstrijd, Einde 1e helft, Start 2e helft en Einde wedstrijd.
- Doelpunten, wissels, time-outs en kaarten worden niet meer in het log of de logexport opgenomen.

## Versie 6.5 correctie
- Doelpunten, wissels, time-outs en gele/rode kaarten staan weer in het wedstrijdlog en de export.
- Daarnaast blijven de vier tijdsmeldingen aanwezig: Start wedstrijd, Einde 1e helft, Start 2e helft en Einde wedstrijd.
- Gewone START/STOP-acties, tijdcorrecties en resetacties worden niet gelogd.

## Versie 6.6 wijziging
- Na afloop van de tweede helft verschijnt automatisch de vraag of er verlenging komt.
- JA start direct een aparte rusttimer van 3:00. Na 00:00 wordt automatisch Verlenging 1 klaargezet op 5:00, stilstaand.
- De jury start de verlenging bewust met START of spatie.
- NEE registreert Einde wedstrijd. Na een verlenging van 5:00 worden Einde verlenging en Einde wedstrijd geregistreerd.

## Versie 6.7 wijziging
- De rust vóór de eerste verlenging is instelbaar in minuten en seconden, standaard 3:00.
- Na de eerste verlenging verschijnt de vraag of een tweede verlenging nodig is.
- Bij JA volgt 1:00 minuut rust en daarna een tweede verlenging van 5:00.
- Beide verlengingsvragen verlopen na 5 seconden automatisch als NEE; de wedstrijd wordt dan beëindigd.

## Versie 6.8 wijziging
- Elk team heeft een eigen HERSTEL 1 SEC.-knop.
- De knop moet minimaal 1 seconde ingedrukt worden gehouden en toont voortgang.
- Herstel maakt de laatst geregistreerde wissel, time-out of kaart van dat team ongedaan.
- Het gebruikte wissel- of time-outaantal wordt gecorrigeerd. Een herstelde kaart en de bijbehorende kaarttimer worden verwijderd.
- De herstelde registratie wordt ook uit het wedstrijdlog verwijderd. Doelpunten worden via deze knop niet hersteld.

## Versie 6.9 wijziging
- Tijdcorrecties wijzigen de verstreken tijd automatisch tegengesteld mee: +10 resterend betekent -10 verstreken en andersom. De klokstatus verandert niet.
- De teamknop heet nu HERSTEL; de tekst 1 SEC. is verwijderd. De beveiliging blijft 1 seconde vasthouden.
- Een tweede teller Stilstand loopt op wanneer de wedstrijdklok tijdens een actieve wedstrijdperiode stilstaat. Deze teller wordt niet beïnvloed door tijdcorrecties.

## Versie 6.10 wijziging
- De beveiligde knop heet alleen RESET TIJD; de tekst over 2 seconden is verwijderd.
- Na 2 seconden vasthouden verschijnt een keuzepop-up: Einde 1e helft, Einde rust, Einde wedstrijd of Annuleren.
- Einde 1e helft registreert het einde en opent de bestaande rustinstelling.
- Einde rust beëindigt een actieve rust en zet de tweede helft klaar.
- Einde wedstrijd opent dezelfde verlengingsvraag als bij het natuurlijke einde van de tweede helft, inclusief de 5-seconden automatische NEE-regel.

## Versie 6.10.1 code-audit
- Alle JavaScript-blokken, HTML-ID's, selectors, manifest en service worker zijn statisch gecontroleerd.
- Voor iedere start van de hoofdtimer wordt een eventueel bestaand interval eerst opgeruimd.
- De service worker cachet uitsluitend succesvolle bestanden van dezelfde origin. Externe afbeeldingen worden niet meer in de PWA-cache geschreven.
- De offline HTML-fallback wordt uitsluitend gebruikt voor navigatie en niet voor afbeeldingen of andere bestanden.

## Versie 6.11 wijziging
- De teller Verstreken is cumulatief over de wedstrijd. Bij de tweede helft begint deze op de ingestelde duur van de eerste helft. Bij 25:00 per helft start de tweede helft dus op 25:00 en loopt door richting 50:00.
- Bij Verlenging 1 en Verlenging 2 wordt de verstreken tijd niet teruggezet naar 00:00, maar loopt deze door vanaf de reeds verstreken reguliere speeltijd en eerdere verlenging.
- Tijdcorrecties blijven de cumulatieve verstreken tijd tegengesteld aanpassen, maar nooit tot vóór het beginpunt van het huidige wedstrijddeel. De Stilstand-teller blijft onafhankelijk.

## Versie 6.12 wijziging
- Bij definitief einde wedstrijd worden wedstrijdklok, verstreken tijd, stilstand, rusttimer en alle actieve kaarttimers op 00:00 gezet.
- Er verschijnt een tweekoloms wedstrijdsamenvatting met links het thuisteam en rechts het uitteam: eindstand, wissels, kaarten en time-outs.
- Automatisch wordt een volledig CSV-bestand gedownload met datum, samenvatting en alle logdetails. De bestandsnaam is jjmmdd_thuisteam_uitteam.csv.
- Een browser/PWA mag uit veiligheid niet zelf een vaste map kiezen. Het bestand gaat naar de ingestelde downloadmap van Edge/Safari; stel die downloadmap in op Documenten om daar automatisch op te slaan.

## Versie 6.13 wijziging
- Totale stilstand van de wedstrijd wordt opgenomen in de wedstrijdsamenvatting en automatische CSV-export.
- Speeltijd blijft standaard 25 minuten en is vrij instelbaar; er zijn snelkeuzes voor 10 en 25 minuten.
- Een gekozen speelduur wordt gebruikt bij reset en bij het klaarzetten van de tweede helft.

## Versie 6.14 correctie
- De Stilstand-teller gebruikt nu verstreken echte tijd en telt betrouwbaar door zodra de wedstrijd is gestart en de wedstrijdklok stilstaat.
- Naast de instelbare speelduur staat BEVESTIG TIJD. De standaard blijft 25 minuten; 10 minuten of een andere waarde kan worden ingevoerd en bevestigd.
- Speeltijd wijzigen is alleen toegestaan als de wedstrijdklok stilstaat.
- RESET TIJD stopt na 2 seconden vasthouden de wedstrijdklok en opent zichtbaar de bestaande resetkeuze.

## Versie 6.15 wijziging
- BEVESTIG TIJD moet nu 2 seconden worden ingedrukt voordat een gewijzigde speelduur wordt toegepast.
- De knoppen 10 min en 25 min kiezen alleen een waarde; ook daarna is 2 seconden BEVESTIG TIJD nodig.
- De tijdcorrectieknoppen, RUST, RESET TIJD, 10 min, 25 min en BEVESTIG TIJD zijn uniform grijs uitgevoerd.

## Versie 6.16 correctie
- Stilstandteller gebruikt een aparte clockHasRun-status die direct bij de eerste echte start van de wedstrijdklok wordt gezet.
- Daardoor telt Stilstand betrouwbaar vanaf het moment dat STOP wordt ingedrukt of de klok met spatie wordt gestopt.
- De teller stopt direct zodra START of spatie de wedstrijdklok weer laat lopen.

## Versie 6.17 wijziging
- Het feitelijke lokale tijdstip van de eerste wedstrijdstart wordt opgeslagen.
- Bij definitief einde wordt het feitelijke lokale eindtijdstip opgeslagen.
- De totale kalenderduur tussen start en einde wordt berekend in minuten met twee decimalen; rust, stilstand en verlenging vallen dus binnen deze totale duur.
- Starttijd, eindtijd en totale duur staan in de eindsamenvatting en automatische CSV-export.

## Versie 6.18 wijziging
- KAART opent per team de bestaande kaart-pop-up met rugnummer en nieuw veld Tijd klok hal (mm:ss).
- Geel berekent halklok minus 4:00; rood berekent halklok minus 8:00. De berekende tijd staat naast het gekleurde bolletje en in de actieve kaartregel.
- Krijgt dezelfde speler tijdens een actieve gele-kaartperiode opnieuw geel, dan wordt de bestaande berekende halkloktijd nogmaals met 4:00 verlaagd en in het log bijgewerkt.
- Kaarttimers blijven tijdens rust gepauzeerd doordat de rusttak van tick vóór de kaarttimerupdates terugkeert; na START van de tweede helft lopen actieve kaarttimers verder.
