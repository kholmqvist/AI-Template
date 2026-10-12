# Fejlfinding: {{FEJL_TITEL}}

Dato: {{DATO}}
Miljø: {{MILJØ}} (lokal / test / preview / produktion)
Relateret sub-plan eller issue: {{LINK}}

## 1. Symptom

Hvad observeres præcist? Inkluder fejlbesked, HTTP-status, logudsnit og skærmbillede hvis relevant.

## 2. Reproduktion

1. {{TRIN_1}}
2. {{TRIN_2}}

- Reproducerbar: Ja / Nej / Delvist
- Mindste reproduktion (test eller kommando): {{MINIMAL_REPRO}}

## 3. Kontekst

- Seneste ændringer: {{COMMITS_ELLER_PR}}
- Berørte moduler: {{MODULER}}
- Konfiguration og miljøvariabler (uden hemmeligheder): {{KONFIG}}

## 4. Hypoteser

| # | Hypotese | Hvordan testes den | Resultat |
| --- | --- | --- | --- |
| H1 | {{HYPOTESE}} | {{TEST}} | Bekræftet / Afvist |

Arbejd én hypotese ad gangen. Ændr ikke flere ting samtidig.

## 5. Observationer

Log, data og fakta der understøtter eller afviser hypoteserne. Skil fakta fra fortolkning.

## 6. Root cause

{{ROOT_CAUSE}}

## 7. Fix

- Ændrede filer: {{FILER}}
- Minimal ændring, der løser root cause (ikke kun symptomet).
- Berører fixet andre dele? {{BIVIRKNINGER}}

## 8. Verifikation

- [ ] Reproduktionen fejler før fixet
- [ ] Reproduktionen virker efter fixet
- [ ] Regressionstest tilføjet: {{TEST}}
- [ ] Eksisterende tests grønne: {{KOMMANDO}}

## 9. Læring

- Hvad skulle have fanget fejlen tidligere (test, type, lint, dokumentation)?
- Skal det føre til en regel i `AGENTS.md` eller en beslutning i `docs/decisions/`?
