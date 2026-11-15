# Juryvoorzitter KNKV v2.0

Nieuwe opbouw met verplichte beginopstelling en reserves per team. Upload alle bestanden naar de root van een HTTPS-host, bijvoorbeeld GitHub Pages.

## Selectiegegevens
- Exact 8 basisspelers per team.
- Rugnummer plus achternaam.
- Als de achternaam ontbreekt: rugnummer plus man/vrouw.
- Reserves met dezelfde gegevens.
- Bij een wissel worden eerst de 8 veldspelers getoond en daarna de bankspelers.
- Een nieuwe reserve kan direct in de wisselpop-up worden toegevoegd.

## v2.1
- Reserve-selectie in de wisselpop-up gerepareerd en zichtbaar gemarkeerd.
- iPhone-weergave met compacte kernbediening.
- Tablet/iPad-weergave met grotere touchknoppen.
- Time-out groen, wissel oranje, kaart geel.

## v2.2
- RESET WEDSTRIJD toegevoegd met dubbele tik.
- Reset wist score, log, wissels, time-outs, kaarten, timers, rust/verlenging en wedstrijdstatus.
- Teamnamen, bevestigde spelersopstelling, speelduur, rustduur en verlengingsinstellingen blijven behouden.

## v2.3
- Beginopstelling standaard geslacht: V, V, M, M, V, V, M, M voor beide teams.
- Subtiele scheidingslijn tussen de bovenste vier (aanval) en onderste vier (verdediging).
- Reserves beginnen standaard met een vrouw en een man per team.

## v2.4
- START ZONDER OPSTELLING toegevoegd.
- In deze modus werkt de app zoals de oude versie: de wedstrijd kan direct starten en wissels worden met rugnummer UIT/IN geregistreerd.
- Via OPSTELLING BEHEREN kan later alsnog een volledige beginopstelling worden ingevoerd.


## Versie 2.8

- **EINDE SPEELTIJD / RUST** behoudt bij de bevestigingsklik dezelfde breedte en positie.
- Zonder opstelling toont het wisselscherm alleen **Rugnummer UIT** en **Rugnummer IN**.
- Met opstelling worden alleen reserves met hetzelfde geslacht als de geselecteerde veldspeler getoond.


## Versie 2.9

- De verstreken tijd van de tweede helft begint op de ingestelde speelduur van de eerste helft. Bij de standaardinstelling begint de tweede helft dus op **25:00** verstreken tijd.


## Versie 2.10

- Tijdens de rust beëindigt **EINDE SPEELTIJD / RUST** nu daadwerkelijk de rust.
- De hoofdknop schakelt tijdens de rust tussen **STOP RUST** en **START RUST**.
- De secondenknoppen wijzigen tijdens de rust de resterende rusttijd in plaats van de speeltijd.
- De tweede helft behoudt de doorlopende verstreken tijd uit versie 2.9.


## Versie 2.11

- Als de wedstrijdtijd na **5 seconden** nog niet is gestart, gaat de grote klok knipperen als herinnering.
- Zodra **START** wordt ingedrukt stopt het knipperen direct.
- Na het stoppen van de speeltijd begint opnieuw een wachttijd van 5 seconden.
- Tijdens de rust blijft de rustbediening uit versie 2.10 actief en wordt deze waarschuwing niet gebruikt.


## Versie 2.12

- Bij een **gele kaart** wordt de verstreken wedstrijdtijd op het moment van geven opgeslagen.
- De kaartweergave toont naast de straftijd ook **gegeven mm:ss**.
- In het wedstrijdlog en daardoor ook in de CSV-export staat de verstreken tijd bij de gele kaart.


## Versie 2.13

- Als de wedstrijdklok stilstaat en de juryvoorzitter de tijd met **+/- seconden** corrigeert, wordt een gele kaart die op dat stilstaande tijdstip is gegeven automatisch naar dezelfde gecorrigeerde verstreken tijd verplaatst.
- De correctie wordt zowel in de kaartweergave als in het wedstrijdlog en de CSV-export bijgewerkt.
- Andere, eerder gegeven gele kaarten blijven ongewijzigd.


## Versie 2.14

- Bij een gele of rode kaart wordt nu de **tijd van de grote aftellende wedstrijdklok** opgeslagen en weergegeven, niet de verstreken tijd.
- Als de klok stilstaat en met **+/- seconden** wordt gecorrigeerd, wordt deze kloktijd van een zojuist gegeven kaart mee gecorrigeerd.
- De tijdelijke kaartregel toont de resterende kaarttijd en de kloktijd waarop de kaart is gegeven.
- Zodra de kaarttimer is afgelopen, verdwijnt de tijdelijke tekst en blijft alleen het **gele of rode bolletje** staan.


## Versie 2.15

- Als de grote wedstrijdklok tijdens stilstand met **+/- seconden** wordt gecorrigeerd, wordt dezelfde effectieve correctie toegepast op alle nog lopende kaarttijden.
- De kaarttijd kan niet onder **00:00** komen. Zodra de kaarttijd nul is, verdwijnt de tijdelijke kaarttekst en blijft alleen het gele of rode bolletje staan.
- De opgeslagen kloktijd waarop de kaart is gegeven blijft eveneens gekoppeld aan de correctie van de grote klok.


## Versie 2.16

- De knop **EINDE SPEELTIJD / RUST (2×)** is verkort naar **EINDE TIJD (2×)** zodat de tekst ook op smallere iPhone-schermen netjes binnen het kader blijft.
- De werking van de dubbele bevestiging en de logica voor einde speeltijd/einde rust zijn niet gewijzigd.


## Versie 2.17

- De lopende 4-minutenklok van een gele kaart is verwijderd.
- Bij een gele kaart wordt een vast vervaltijdstip getoond: **tijd grote klok minus 4 minuten**.
- Bij minder dan 4 minuten resterend in de eerste helft loopt de berekening door naar de tweede helft. Voorbeeld: kaart bij 02:00 in de eerste helft vervalt bij 23:00 in de tweede helft bij een speelduur van 25 minuten.
- Een gele kaart in de laatste 4 minuten van de tweede helft krijgt vervaltijd **00:00**.
- Zodra de grote klok het berekende tijdstip bereikt, verschijnt een pop-up. De wedstrijdklok en overige functies blijven doorlopen.
- Na het verstrijken verdwijnt de tijdtekst en blijft het gele bolletje staan.
