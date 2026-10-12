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

## Kontekst

- Giv altid agenten masterplan, relevant sub-plan og berørte filer, frem for hele repositoryet.
- Ved lange sessioner: opsummér status i en fil, og start en ny session fra den, når konteksten bliver tung.
- Ved underagenter: angiv opgaven, afgrænsningen og det forventede output i prompten.

## Regler

- Skift ikke model midt i en opgave uden at notere det i sub-planen eller i commit-beskeden.
- Brug ikke højt reasoning til triviel redigering. Det er spild af tid og kontekst.
- Dokumentér nye modeller her, når de tages i brug.

## Konfiguration i projektet

- Standardmodel: `{{STANDARD_MODEL}}`
- Reasoning-niveau for planlægning: `{{PLAN_REASONING}}`
