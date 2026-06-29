# `.github` — org-brede defaults voor Jabu-Systems

Deze **publieke** repository levert *default community health files* voor alle
repositories van de organisatie `Jabu-Systems`. GitHub gebruikt deze bestanden
automatisch voor elke repo (privé of publiek) die **geen eigen versie** van dat
bestand heeft. Zo onderhouden we issue-formulieren, het PR-template, de
bijdragerichtlijnen, de gedragscode en het beveiligingsbeleid op één plek.

> Deze repo moet **publiek** zijn, anders passen de defaults zich niet org-breed
> toe — ook niet op private member-repos. De repo bevat geen broncode, alleen
> sjablonen en beleid.

## Inhoud

```
.github/
  ISSUE_TEMPLATE/
    bug.yml                 # Issue-form, gekoppeld aan Issue Type "Bug"
    feature.yml             # Issue-form, gekoppeld aan Issue Type "Feature"
    task.yml                # Issue-form, gekoppeld aan Issue Type "Task"
    config.yml              # blank issues uit + contact-links
  PULL_REQUEST_TEMPLATE.md  # Standaard PR-template
CONTRIBUTING.md             # Bijdragerichtlijnen (branches, commits, PR's, labels)
CODE_OF_CONDUCT.md          # Gedragscode (Contributor Covenant 2.1)
SECURITY.md                 # Beveiligingsbeleid + private vulnerability reporting
profile/
  README.md                 # Org-profiel, zichtbaar op github.com/Jabu-Systems
README.md                   # Dit bestand
```

## Hoe overerving werkt

GitHub zoekt een ontbrekend community-health-bestand op in deze volgorde:
de map `.github/`, de root van de repo, en daarna `docs/`. Vindt een member-repo
het bestand zelf niet, dan toont GitHub de versie uit deze `.github`-repo.

Dit geldt onder meer voor: `CODE_OF_CONDUCT`, `CONTRIBUTING`, `SECURITY`,
`SUPPORT`, `GOVERNANCE`, `FUNDING`, issue- en pull-request-templates,
`config.yml` en discussion-category-forms.

### Belangrijke aandachtspunten

- **Per type, alles-of-niets voor issue-templates.** Zodra een member-repo
  *zelf* iets in `.github/ISSUE_TEMPLATE/` heeft staan, neemt GitHub **geen
  enkel** default-issue-template meer over voor die repo. Het is per repo dus
  alles uit deze repo, óf volledig de eigen set.
- **Overschrijven kan per repo.** Plaats een eigen bestand in de member-repo om
  de default te overrulen (bijv. een repo-specifieke `CONTRIBUTING.md`).
- **Defaults zijn geen kopieën.** Member-repos krijgen geen bestand in hun eigen
  history; GitHub toont de default live. Wijzig hier, en het werkt overal door.

## Issue-formulieren, Issue Types en private repos

- De `.yml`-bestanden in `ISSUE_TEMPLATE/` zijn **YAML issue forms** met
  gestructureerde velden (dropdowns, verplichte velden, checkboxes).
- Issue forms werken op **private repositories**, en **verplichte velden** worden
  daar ook ondersteund. Een markdown-fallback is daarom niet nodig.
- Elk formulier koppelt via de `type:`-sleutel aan een org-breed **Issue Type**
  (`Bug`, `Feature`, `Task`). Issue Types zijn algemeen beschikbaar.
- `config.yml` zet `blank_issues_enabled: false`, zodat melders altijd een
  formulier kiezen, en biedt contact-links voor vragen en beveiligingsmeldingen.

### Labels

De formulieren leggen **applicatie/component** (`app:*`) en **thema/domein**
(`theme:*`) vast via dropdowns. Soort, status en prioriteit komen **niet** uit
labels maar uit Issue Types en Project-velden. Statische auto-labels worden alleen
gezet waar ze altijd kloppen (bijv. `needs-investigation` op een nieuwe bug);
de overige labels worden bij triage toegekend.

### Projecten

Wil je nieuwe issues automatisch aan een GitHub Project koppelen, ontkommentarieer
dan de `projects:`-sleutel in de formulieren en vul het juiste nummer in
(formaat: `Jabu-Systems/<projectnummer>`).

## Onderhoud

- Houd de labeltaxonomie in `CONTRIBUTING.md` en in de dropdowns van de
  issue-formulieren synchroon.
- Vul de placeholder-mailadressen in `SECURITY.md` en `CODE_OF_CONDUCT.md` in.
- Wijzigingen hier werken direct door naar alle member-repos zonder eigen
  variant.
