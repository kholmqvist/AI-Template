# Agentregler: {{PROJEKTNAVN}}

Disse regler gælder for alle sprogmodeller og agenter, der arbejder i dette repository.

## 1. Sprog

- Svar til brugeren og dokumentation skrives på `{{SPROG}}` (fx dansk).
- Kode, identifikatorer, commit-beskeder og fejlmeddelelser i kode skrives på `{{KODESPROG}}` (fx engelsk), medmindre projektet angiver andet.
- Brug præcise faguudtryk og undgå unødig fyldtekst.

## 2. Arbejdsgang

1. Læs `README.md`, relevant masterplan og den aktuelle sub-plan, før der ændres kode.
2. Hold dig til den afgrænsede opgave. Ret ikke ufaglige problemer, der ligger uden for opgaven, men ret fejl som din ændring har forårsaget eller er tæt koblet til.
3. Følg eksisterende mønstre i kodebasen før nye.
4. Kør den mindste relevante test, lint og build efter ændringer. Kør bredere tests først ved behov.
5. Opdatér dokumentation, der direkte hænger sammen med ændringen.

## 3. Kodestil

- Kommentér kun kode, der kræver en forklaring. Kommentarer forklarer *hvorfor*, ikke *hvad*.
- Ingen kommenterede rester af gammel kode.
- Ingen hemmeligheder, tokens eller persondata i kode, logs eller tests.

## 4. Tilladte og forbudte handlinger

**Tilladt uden spørgsmål:** læse filer, søge i kode, køre tests, lint og build, oprette og redigere filer i arbejdsområdet.

**Kræver eksplicit brugeranmodning:**
- Push til, merge til eller ændring af `{{HOVEDBRANCH}}`.
- Sletning af data, filer eller branches, der ikke er oprettet i den aktuelle opgave.
- Ændring af infrastruktur, hemmeligheder, adgangsregler eller produktionskonfiguration.
- Kørsel af migrationer eller imports mod produktion.

**Forbudt:** at omgå sikkerhedsbarrierer, at committe hemmeligheder, og at skrive direkte til produktion fra test- eller lokale kilder.

## 5. Datahåndtering

{{DATA_REGLER}}

Eksempel (slettes eller tilpasses):
- Produktionsdata er kilden til sandheden.
- Data må aldrig kopieres fra test, preview eller lokal kopi til produktion.

## 6. Kommunikation

- Vær kort i rutinesvar. Forklar tilgang før større ændringer.
- Ved usikkerhed: gør en rimelig antagelse, nævn den eksplicit, og fortsæt, medmindre den er destruktiv eller irreversibel.
- Rapportér resultater med konkret evidens: testkommando og resultat.

## 7. Git

- Arbejd på feature-branches. Commit med klar besked og forklaring af hvorfor.
- Lav ikke ukontrollerede force-pushes.
