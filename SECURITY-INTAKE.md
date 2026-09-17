<!-- template-control
template: PROJECT-SECURITY-INTAKE
version: 1.0
date: 2026-09-17
language: nl-NL
source: https://github.com/SpringTree/isms/blob/main/templates/PROJECT-SECURITY-INTAKE.md
-->
<!--
  Sjabloon: security intake- en beheersdocument (ISMS-PROCEDURE-informatiebeveiliging-in-projectmanagement).

  Gebruik: kopieer dit bestand bij projectstart naar de repository van het
  project (bijv. als SECURITY-INTAKE.md in de root), vul het in en laat het
  reviewen. Het ingevulde exemplaar leeft en versioneert mee met het project.

  Dit sjabloon is geen beheerst document: het staat niet in docs/, kent geen
  goedkeuringsstroom en `bun run check` valideert het niet. Het draagt wél een
  versie, zodat een ingevuld exemplaar in een projectrepository kan laten zien
  op welke uitgave het gebaseerd is. Wijzig je het sjabloon inhoudelijk, hoog
  dan version op en pas de regel Sjabloonversie hieronder aan — er is geen
  controle die dat afdwingt.

  language is een BCP 47-taalcode. Het veld staat hier omdat dit bestand naar
  klantrepositories wordt gekopieerd, waar een Engelse variant kan ontstaan;
  de taal van een ingevuld exemplaar is dan niet meer vanzelfsprekend.
-->

# Security intake — <projectnaam>

| Veld                                                              | Waarde      |
| ----------------------------------------------------------------- | ----------- |
| Project                                                           |             |
| Opdrachtgever                                                     |             |
| Startdatum                                                        |             |
| Ingevuld door (developer die het project start)                   |             |
| Gereviewd door (Security Officer, of directielid bij afwezigheid) |             |
| Reviewdatum                                                       |             |
| Sjabloonversie                                                    | 1.0 (nl-NL) |

## 1. Risico-analyse-checklist

Beantwoord elke vraag met ja/nee/n.v.t. **mét onderbouwing** — de onderbouwing
is het eigenlijke denkwerk.

| #   | Vraag                                                                                                                                                                                              | Ja/nee/n.v.t. | Onderbouwing en afspraken |
| --- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------- | ------------------------- |
| 1   | Verwerkt het project persoonsgegevens? Zo ja: is de verwerkersrelatie geregeld (DPA/verwerkersovereenkomst, zie ISMS-REGISTER-wettelijk-en-contractueel-register)?                                 |               |                           |
| 2   | Vloeit er productiedata naar test- of ontwikkelomgevingen? Zo ja: gemaskeerd, of contractueel belegd bij de opdrachtgever?                                                                         |               |                           |
| 3   | Introduceert het project nieuwe (cloud)diensten of leveranciers? Zo ja: beoordeling conform het Leveranciersbeveiligingsbeleid (ISMS-BELEID-leveranciersbeveiligingsbeleid) gedaan?                |               |                           |
| 4   | Wie krijgen toegang tot welke omgevingen (SpringTree- én klantzijde), en wie kent die toegang toe?                                                                                                 |               |                           |
| 5   | Wie beheert de productieomgeving en de database — SpringTree of de opdrachtgever? Zo SpringTree: back-ups conform het Back-upbeleid (ISMS-BELEID-back-upbeleid) ingericht, inclusief notificaties? |               |                           |
| 6   | Worden er secrets/credentials gebruikt? Waar leven die (1Password), en zijn gedeelde accounts nodig (→ uitzonderingenregister ISMS-REGISTER-uitzonderingenregister)?                               |               |                           |
| 7   | Wordt er AI ingezet met klantcode of klantdata? Zo ja: binnen de SpringTree-licenties en conform het Aanvaardbaar-gebruikbeleid (ISMS-BELEID-aanvaardbaar-gebruikbeleid §3.8)?                     |               |                           |
| 8   | Stelt de opdrachtgever contractuele beveiligingseisen (SLA, geheimhouding, meldtermijnen)? Zo ja: opgenomen in ISMS-REGISTER-wettelijk-en-contractueel-register?                                   |               |                           |
| 9   | Zijn er koppelingen met externe systemen of API's die extra risico geven (bulk-data, betalingen, gevoelige bronnen)?                                                                               |               |                           |

## 2. Security requirements

De eisen die voor dít project gelden — uit de checklist hierboven, uit het
contract met de opdrachtgever, of uit het SpringTree-beleid.

| #   | Requirement | Bron (klant/wet/SpringTree-beleid) | Aantoonbaarheid |
| --- | ----------- | ---------------------------------- | --------------- |
| 1   |             |                                    |                 |
| 2   |             |                                    |                 |

## 3. Methodiek van aantoonbaarheid

Kies één van beide en licht toe:

- [ ] **A — Bewijs per requirement**: elke requirement in hoofdstuk 2 verwijst naar zijn bewijs (commit, PR, configuratie, testresultaat) in deze repository. Geschikt voor elk project, ook bij sporadisch werk.
- [ ] **B — Periodieke bespreking**: de requirements worden ten minste maandelijks besproken zolang er actief ontwikkeld wordt, in de overlegvorm van dit project (sprint, retro of refinement); de bespreking wordt kort vastgelegd (notitie of Slack-bericht).

Toelichting op de keuze:

## 4. Herbeoordeling

Bij een significante wijziging van het project (nieuwe scope, nieuwe
leverancier, andere dataverwerking) wordt dit document opnieuw doorlopen en
gereviewd.

| Datum | Aanleiding | Gereviewd door |
| ----- | ---------- | -------------- |
|       |            |                |
