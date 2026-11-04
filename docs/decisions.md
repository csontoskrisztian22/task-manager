# Architectural Decisions

Ebben a fájlban dokumentálom a fontosabb technikai döntéseket.
Formátum: döntés → miért → milyen alternatívák voltak.

## D1 – Monorepo npm workspaces-szel

**Döntés:** Egy repóban a backend és frontend, `npm workspaces`-szel.

**Miért:** Egy portfólióprojektnél a reviewer egy helyen látja a teljes stacket.
A workspaces megosztott `node_modules`-t és egységes scripteket ad.

**Alternatívák:** külön repók (több repo, nehezebb átlátni), pnpm/yarn workspaces
(ez is jó, de az npm a legelterjedtebb, és ránézésre azonnal érthető).

## D2 – Express a NestJS helyett

**Döntés:** Express.

**Miért:** Kisebb boilerplate, a portfólióban a rétegzés (route → service → repo)
kézzel látszik, ami jobban bizonyítja, hogy értem a mintát, mint egy generált Nest modul.