# Multi-agent implementering

Denne guide beskriver, hvordan flere agenter kan implementere kode parallelt uden konflikter og med kontrolleret kvalitet.

## Roller

| Rolle | Ansvar | Må skrive kode |
| --- | --- | --- |
| Koordinator | Læser masterplan og sub-planer, fordeler opgaver, samler resultater. | Nej (kun planfiler) |
| Implementer | Ændrer kode for én afgrænset opgave. | Ja, inden for sit filejerskab |
| Tester | Skriver og kører tests for en opgave. | Kun testfiler |
| Reviewer | Gennemgår diff mod plan og acceptkriterier. | Nej |
| Fejlsøger | Undersøger fejl ved hjælp af troubleshooting-skabelonen. | Kun til diagnose og minimal fix |

En agent kan have flere roller i små opgaver, men koordinatoren skal aldrig reviewe sit eget arbejde.

## Opgavefordeling

1. Koordinatoren nedbryder en sub-plan i opgaver, der kan løses uafhængigt.
2. Hver opgave får et **filejerskab**: hvilke filer må ændres, og hvilke må ikke.
3. Opgaver med overlappende filer køres sekventielt.
4. Afhængigheder noteres i sub-planen (`Afhængigheder`).

## Kontrakt for en underagent

Hver underagent får mindst:

- Formål og link til sub-plan og acceptkriterier.
- Liste over tilladte og forbudte filer.
- Kommandoer til test, lint og build.
- Forventet output: ændrede filer, testresultat, åbne spørgsmål.
- Regel: ingen push, merge eller ændring uden for filejerskab.

## Samling og verifikation

1. Koordinatoren samler ændringer på én branch og løser konflikter.
2. Kør den fulde relevante testsuite én gang efter samling, ikke kun underagenternes egne tests.
3. Reviewer gennemgår samlet diff mod acceptkriterierne i sub-planen.
4. Afvigelser fra planen noteres i sub-planen før merge.

## Faldgruber

- **Stille konflikter:** To agenter ændrer samme fil uden at det opdages. Løsning: filejerskab i planen.
- **Tests grønne i isolation, røde samlet:** Løsning: fuld kørsel efter samling.
- **Planen driver:** Agenter glider væk fra scope. Løsning: acceptkriterier som checkliste.
- **Gentagne fejl:** Samme fejl i flere opgaver. Løsning: fix i fælles kode og dokumentér i `docs/decisions/`.

## Når multi-agent ikke bør bruges

- Små rettelser (få filer, én kontekst).
- Opgaver med stærke indbyrdes afhængigheder.
- Ukendte fejl, hvor én fejlsøger er mere effektiv (se [troubleshooting](troubleshooting-template.md)).
