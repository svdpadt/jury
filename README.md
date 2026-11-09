# Juryvoorzitter KNKV v1.0

Volledig opnieuw opgebouwde PWA. Publiceer alle bestanden samen via HTTPS, bijvoorbeeld GitHub Pages.

## Belangrijkste functies
- wedstrijdklok, verstreken tijd, helften, rust en twee verlengingen
- score, time-outs, wissels, kaarten en herstel per team
- kaarttijd op basis van de halklok
- logboek, eindsamenvatting en automatische CSV
- START NIEUWE WEDSTRIJD: 2 seconden vasthouden
- offline PWA, donker/licht en landscape

## v1.1
- 10-minuten snelknop verwijderd; speeltijd blijft vrij invoerbaar en 25 minuten blijft als snelkeuze.
- Alle 2-secondenknoppen tonen tijdens vasthouden een gele voortgangsbalk, visuele indrukstatus en VASTHOUDEN...
- RESET TIJD heet nu EINDE SPEELTIJD / RUST en opent na 2 seconden de bestaande contextuele einde-keuze.

## v1.2
- Nieuwe cumulatieve Stilstand-timer start zodra de speeltijd wordt gestopt en stopt zodra de speeltijd weer loopt.
- Rust en verlengingsrust tellen niet mee als stilstand.
- In de eindsamenvatting wordt de feitelijke wedstrijdduur afgerond op hele minuten.
- Stilstand totaal wordt ook opgenomen in de samenvatting/CSV.

## v1.3
- Automatische CSV-download bij einde wedstrijd verwijderd.
- Het samenvattingsscherm bevat nu DOWNLOAD WEDSTRIJDGEGEVENS. Alleen na deze klik wordt het CSV-bestand gedownload.
- De handmatige CSV-knop in het hoofdscherm blijft beschikbaar.

## v1.4
- Berekende halkloktijd naast gele/rode kaartbolletjes verwijderd.
- RUST-knop uit het hoofdscherm verwijderd. Rust blijft beschikbaar via EINDE SPEELTIJD / RUST en de einde-helftworkflow.

## v1.5
- Vasthoudtijd van BEVESTIG TIJD, EINDE SPEELTIJD / RUST en START NIEUWE WEDSTRIJD verkort naar 1 seconde.
- Visuele VASTHOUDEN-indicatie en voortgangsbalk blijven behouden.

## v1.6
- Alle vasthoudacties verwijderd.
- HERSTEL, BEVESTIG TIJD, EINDE SPEELTIJD / RUST en START NIEUWE WEDSTRIJD vereisen nu twee snelle tikken/klikken binnen 450 ms.
- Na de eerste tik verschijnt KLIK NOGMAALS; zonder tweede tik vervalt de actie automatisch.

## v1.7
- Bij einde 1e helft, rust, 2e helft en verlenging verschijnt een bevestigingspop-up met OK voor de volgende fase.
- Verlengingsvragen en automatische 5-secondenkeuze zijn verwijderd.
- Onder het log staat Verlenging mogelijk, standaard uit, met instelbare verlengingsduur standaard 5 minuten.
- Na einde 2e helft start OK alleen een verlenging wanneer de selectie aanstaat; anders volgt de eindsamenvatting.

## v1.8
- Twee verlengingen met dezelfde instelbare duur.
- Na de tweede verlenging start een strafworpenserie die vanaf de eerste ronde sudden death is.
- Per ronde neemt elk team één strafworp; een afwijkende uitkomst in een complete ronde bepaalt direct de winnaar.
- Samenvatting en CSV tonen verlengingen en strafworpen alleen wanneer deze daadwerkelijk hebben plaatsgevonden.

## v1.9
- Na de eerste verlenging volgt alleen bij gelijke stand een tweede verlenging.
- In de tweede verlenging beëindigt het eerste doelpunt de klok als golden goal, na bevestiging van het winnende team.
- Bij afwijzen van de golden-goalbevestiging wordt het doelpunt hersteld en loopt de tweede verlenging verder.
- Als de tweede verlenging zonder golden goal gelijk eindigt, start de sudden-death strafworpenserie.
- Strafworpknoppen heten DOELPUNT (groen) en MIS (rood).
- Samenvatting en CSV vermelden golden goal alleen wanneer deze heeft plaatsgevonden.

## v1.9.1
- START NIEUWE WEDSTRIJD zet de wedstrijdduur altijd terug op 25 minuten.
- Golden-goalbevestiging heeft nu een contrastrijke groene winnaar-knop en rode herstelknop.
- Strafworpknoppen DOELPUNT en MIS hebben extra contrast en duidelijke groene/rode styling.
