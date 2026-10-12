# Sub-plan: {{SUBPLAN_NAVN}}

Forælder: [masterplan]({{MASTERPLAN_FIL}}), arbejdspakke {{WP_ID}}

## Formål

{{FORMÅL}}

Én afgrænset funktion eller ændring. Hvis planen bliver større end ~1 uge eller ~10 filer, så del den op.

## Afhængigheder

- Forudsætter: {{FORUDSÆTNINGER}}
- Blokerer: {{BLOKERER}}

## Berørte områder

- Filer/moduler: {{FILER}}
- Dataændringer: {{DATAÆNDRINGER}} (migrations: {{MIGRATIONS}})

## Implementeringstrin

1. **{{TRIN_1}}**
   - Ejer: {{AGENT_ELLER_PERSON}}
   - Filer: {{FILER}}
2. **{{TRIN_2}}**

## Filejerskab (multi-agent)

| Agent/opgave | Må ændre | Må ikke ændre |
| --- | --- | --- |
| {{AGENT}} | {{FILER}} | {{IKKE_FILER}} |

## Acceptkriterier

- [ ] {{KRITERIUM}}

## Tests

- Nye tests: {{NYE_TESTS}}
- Eksisterende tests der skal være grønne: {{TESTS}}

## Noter og beslutninger

- Beslutninger lægges i `docs/decisions/` hvis de er varige.
- Ændringer af planen noteres med dato nederst.
