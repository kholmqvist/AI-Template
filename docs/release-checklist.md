# Release-tjekliste

## Før merge

- [ ] Sub-planens acceptkriterier er opfyldt.
- [ ] Tests kører: `{{TEST_KOMMANDO}}`
- [ ] Lint og typecheck: `{{LINT_KOMMANDO}}`
- [ ] Build virker: `{{BUILD_KOMMANDO}}`
- [ ] Dokumentation opdateret, hvor ændringen berører den.
- [ ] Migrations er gennemgået: skema-ændringer er bagudkompatible, og datamigrationer indeholder ingen testdata.
- [ ] Ingen hemmeligheder eller persondata i diff.
- [ ] Review er udført af en anden agent eller person end implementeringen.

## Preview

- [ ] Preview bygges fra feature-branchen.
- [ ] Preview bruger egen database eller datakopi, aldrig produktion direkte.
- [ ] Adgang til admin og skriveendpoints er beskyttet på preview-hosts.
- [ ] Manuel gennemgang af de vigtigste flows.

## Produktion

- [ ] Datakilden er verificeret som autoritativ.
- [ ] Migrationer anvendes før kodeudrulning, medmindre andet er aftalt.
- [ ] Rollback-plan er noteret.
- [ ] Overvågning eller manuel kontrol efter udrulning.

## Dataregler (eksempel, tilpas til projektet)

- Produktion er kilden til sandheden.
- Data må aldrig kopieres, importeres eller gendannes fra test, preview eller lokal kopi til produktion.
- Import fra kildefil til produktion sker kun efter eksplicit anmodning og direkte mod produktion.
