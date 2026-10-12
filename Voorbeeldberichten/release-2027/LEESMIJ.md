# Voorbeeldberichten release 2027 (v1.4.0)

Voorbeelden bij release 2027. Ze voldoen aan de JSON-schema's van release 2027 en aan de verbandscontroles in
§6.3.1 en §6.3.2 van de handleiding (onder meer bericht 5: per instructie `tradeAmount` óf `tradeQuantity`;
bericht 6: `tradeQuantity` × `tradePrice` = `tradeAmount`).

De voorbeelden zijn opgebouwd naar situaties uit de praktijk. De pensioenuitvoerders zijn bestaande uitvoerders,
met `puvCode` en naam zoals in de codelijst AFDIDP; alle bedragen en kenmerken zijn fictief. ISIN's beginnen met
het niet-toegewezen landprefix `QZ`; IBAN's zijn fictief.

Niet normatief: bij verschil gelden de JSON-schema's en de handleiding.

## Overzicht

| bericht | bestand | wat het laat zien |
|---|---|---|
| 1 Vermogen | `Voorbeeldbericht_1.json`, `_2.json` | basis; twee regelingen |
| | `Voorbeeldbericht_1-reserves.json` | cohorten per leeftijd in maanden (actief en slaper) en reserves: AFDRES 1, 3, 4 en tweemaal 99, elk met een eigen `reserveDescription` |
| 2 Cashflow | `Voorbeeldbericht_2.json` | SPR-route, uitsplitsing per cohort |
| | `Voorbeeldbericht_2-fpr.json` | FPR-route: cashflow per beleggingsportefeuille, elk met eigen `netDate`; het totaal direct onder de regeling |
| 3 Pensioenprojectie | `Voorbeeldbericht_3.json`, vier chunkvoorbeelden | SPR-route en chunking |
| | `Voorbeeldbericht_3-fpr.json` | FPR-route: maandelijkse geprojecteerde uitkeringen per beleggingsportefeuille; de betalingen direct onder de regeling zijn de regelingtotalen |
| 4 Rendementsinformatie | `Voorbeeldbericht_4.json`, `-uitgebreid.json` | portefeuille met cohorten (SPR) en alleen portefeuilles (FPR) |
| 5 Orderopdracht | `5-buy`, `5-buy-sell`, `5-buy-sell-switch` | koop op bedrag, verkoop op aantal, switch |
| 6 Orderconfirmation | `6-buy`, `6-buy-sell-switch` | |
| 10 Stuurinformatie beleggingspools | `Voorbeeldbericht_10.json` | netto koop- en verkoopbehoefte per beleggingspool, zonder cohortpool |
| 13 Waarde-informatie beleggingspool | `Voorbeeldbericht_13.json` | drie pools; totale poolwaarde = aantal units × NAV per unit |
| 14 Betaalinformatie | `Voorbeeldbericht_14.json` | meerdere betalingen per regeling, elk met een begunstigde |
| 15 Corporate Actions | `Voorbeeldbericht_15.json` | cash dividend (1), stockdividend (2), productverandering (3) en rebate (99) |
| Feedbackbericht | `Voorbeeldbericht_feedback-geaccepteerd.json`, `-afgewezen.json` | geaccepteerd (8) en afgewezen (0) met `errorCode` en uitleg |

## Wijzigingen

| datum | bestand | wijziging |
|---|---|---|
| 12-10-2026 | alle | eerste versie voor release 2027, omgezet van de voorbeelden van release 2026 en de prerelease |
| | bericht 2 `Voorbeeldbericht_2.json` | `netDate` bij elk cohort (verplicht sinds release 2027) |
| | bericht 3 `Voorbeeldbericht_3.json` | regeling `scheme01` met een cohort: in bericht 3 precies één uitsplitsing per regeling (§6.3.1) |
| | bericht 3, vier chunkvoorbeelden | `afdDefinitionName` gelijk aan de bestandsnaam van het schema |
| | bericht 5, alle drie | buy met alleen `tradeAmount`, sell met alleen `tradeQuantity` |
| | bericht 5 en 6 `buy-sell-switch` | switch van de opbouwfase naar de CVP, beide in EUR; in bericht 5 draagt `switchfrom` het aantal units en blijft `switchto` leeg |
| | bericht 6 `buy` | `tradeAmount` 10000.08 (102 × 98.04) |
| | bericht 1 `Voorbeeldbericht_1.json` | reserves zonder leeftijd en deelnemersstatus, met een passende omschrijving |
| | alle | naam van de pensioenuitvoerder gelijk aan de naam bij de `puvCode` in AFDIDP |
| | nieuw | berichten 10, 13, 14, 15, feedbackbericht, FPR-route in 2 en 3, reserves in 1 |

---

# Sample messages release 2027 (v1.4.0) — English

Samples for release 2027. They conform to the JSON schemas of release 2027 and to the consistency checks in
§6.3.1 and §6.3.2 of the manual. They are modelled on practical situations. The pension providers are existing providers with
`puvCode` and name as in the AFDIDP code list; all amounts and identifiers are fictitious (ISINs use the unassigned
country prefix `QZ`; IBANs are fictitious). Not normative: in
case of a difference, the JSON schemas and the manual prevail. The overview and change log above list every file
and change.
