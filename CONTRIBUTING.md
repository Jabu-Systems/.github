# Bijdragen aan Jabu-Systems

Bedankt voor je bijdrage. Dit document beschrijft de werkwijze die voor **alle** repositories van de organisatie `Jabu-Systems` geldt, tenzij een repository een eigen `CONTRIBUTING.md` heeft die dit overschrijft.

## Werk dat we volgen via issues

Werk start bij een **issue**. We gebruiken org-brede **Issue Types**:

- **Bug** — een reproduceerbaar defect.
- **Feature** — nieuwe functionaliteit of een verbetering.
- **Task** — afgebakend werk, onderhoud, refactors of techniek.

Maak een issue via de templatekiezer (tab *Issues* → *New issue*). Lege issues staan uit; kies een formulier zodat de juiste metadata wordt vastgelegd.

### Labels

Labels beschrijven **waar** en **waarover** een issue gaat — niet de soort, status of prioriteit (die komen uit Issue Types en Project-velden).

- **Applicatie / component:** `app:api`, `app:api-console`, `app:auth-app`, `app:commission-app`, `app:console`, `app:core`, `app:cross-app`, `app:fieldops`, `app:infra`, `app:ops`, `app:web`
- **Thema / domein:** `theme:architecture`, `theme:ai`, `theme:auth`, `theme:billing`, `theme:checklists`, `theme:data-sources`, `theme:devices`, `theme:landing`, `theme:lib-refactor`, `theme:notificaties`, `theme:observability`, `theme:onboarding`, `theme:points`, `theme:rapportages`
- **Intake / workflow:** `pilot-feedback`, `needs-investigation`, `good first issue`, `help wanted`

## Branches

- Werk nooit direct op `main`. Maak een feature-branch.
- Naamgeving: `type/korte-omschrijving`, bijv. `fix/login-redirect`, `feat/rapportage-export`, `chore/deps-bump`.
- Houd branches kortlevend en rebase regelmatig op `main`.

## Commits

We volgen **Conventional Commits**:

```
<type>(optionele-scope): korte omschrijving

optionele body

optionele footer (bijv. "Closes #123")
```

Veelgebruikte types: `feat`, `fix`, `chore`, `refactor`, `docs`, `test`, `build`, `perf`, `ci`.

> Let op: in de hoofd-monorepo committen meerdere mensen en agents tegelijk op een gedeelde index. Gebruik daarom altijd een **pathspec** (`git commit -- <bestand>`), nooit `git add -A`.

## Pull requests

1. Open een PR tegen `main` en koppel het issue (`Closes #123`).
2. Vul het PR-template volledig in.
3. Houd de PR **klein en gefocust** op één doel.
4. Zorg dat lint, typecheck en tests lokaal slagen.
5. Geen secrets, tokens of credentials in de diff.
6. Vraag review aan; merge pas na akkoord en groene checks.

## Lokaal ontwikkelen

De meeste repositories gebruiken **pnpm** in een monorepo-opzet. Globaal:

```bash
pnpm install
pnpm dev        # of de in de repo gedocumenteerde dev-/run-opdracht
pnpm lint
pnpm typecheck
pnpm test
```

Raadpleeg de `README.md` en eventuele `CLAUDE.md`/docs van de specifieke repository voor afwijkende opdrachten, omgevingvariabelen (Infisical) en services (Supabase, Tilt, Docker).

## Code- en stijlconventies

- Volg de bestaande stijl en structuur van de repository; voeg geen nieuwe patronen toe zonder reden.
- React-componentbestanden gebruiken PascalCase; hooks/utils/config volgen kebab-case of de bestaande projectstijl.
- Voeg geen documentatiebestanden toe tenzij gevraagd.
- Verwijder geen ongecommit werk van anderen zonder afstemming.

## Gedragscode

Deelnemen betekent akkoord met onze [Gedragscode](CODE_OF_CONDUCT.md).

## Beveiliging

Meld kwetsbaarheden **niet** via een issue of PR, maar volg ons [beveiligingsbeleid](SECURITY.md).
