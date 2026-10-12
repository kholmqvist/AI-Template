# Modelkonfiguration

Denne guide beskriver, hvilken model og hvilket reasoning-niveau der bruges til hvilken opgave. Tilpas tabellen til de modeller, teamet har adgang til.

## Valg pr. opgavetype

| Opgavetype | Anbefalet profil | Begrundelse |
| --- | --- | --- |
| Planlægning og arkitektur | Stærkeste model, højt reasoning | Fejl her koster mest senere. |
| Implementering af afgrænset kode | Hurtig, kodefokuseret model, middel reasoning | Klar opgave og plan giver god kvalitet billigt. |
| Code review | Stærk model, højt reasoning | Skal finde subtile fejl. |
| Fejlfinding (ukendt årsag) | Stærk model, højt reasoning | Kræver hypoteser og verifikation. |
| Søgning og oversigt over kode | Hurtig model, lavt reasoning | Rent opslag. |
| Dokumentation og rettelser af tekst | Hurtig model, lavt reasoning | Lav risiko. |

## Profiler

Vælg én profil i konfigurationen nedenfor. Profilen angiver model og reasoning pr. opgavetype.

### Prisvenlig

Billigste model med god kvalitet. Eskaler til en stærkere model ved komplekse opgaver.

| Opgavetype | Model | Reasoning |
| --- | --- | --- |
| Planlægning og arkitektur | `gpt-6-luna` | high |
| Implementering af afgrænset kode | `gpt-6-luna` | low |
| Code review | `gpt-6-luna` | high |
| Fejlfinding (ukendt årsag) | `gpt-6-luna` | high |
| Søgning og oversigt over kode | `gpt-6-luna` | none |
| Dokumentation og rettelser af tekst | `gpt-6-luna` | none |

Priser for `gpt-6-luna`: 10 credits pr. 1M input-tokens, 1 credit pr. 1M cached input, 50 credits pr. 1M output-tokens.

Eskalering: brug `gpt-6.1-sol` til komplekse planer, arkitektur og review af sikkerhedskritisk kode.

## Kontekst

- Giv altid agenten masterplan, relevant sub-plan og berørte filer, frem for hele repositoryet.
- Ved lange sessioner: opsummér status i en fil, og start en ny session fra den, når konteksten bliver tung.
- Ved underagenter: angiv opgaven, afgrænsningen og det forventede output i prompten.

## Regler

- Skift ikke model midt i en opgave uden at notere det i sub-planen eller i commit-beskeden.
- Brug ikke højt reasoning til triviel redigering. Det er spild af tid og kontekst.
- Dokumentér nye modeller her, når de tages i brug.

## Konfiguration i projektet

- Profil: `{{PROFIL}}` (`Prisvenlig` eller en egen profil)
- Standardmodel: `{{STANDARD_MODEL}}`
- Reasoning-niveau for planlægning: `{{PLAN_REASONING}}`
