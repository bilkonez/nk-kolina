# NK Kolina Ustikolina – web stranica

Statična stranica (bez build koraka). Netlify je objavljuje direktno iz ovog repozitorija.

## Šta se ažurira
Svi podaci o tekućoj sezoni su u **`data.json`**:

- `updated` – datum zadnjeg ažuriranja (YYYY-MM-DD). Stranica uzima `data.json` samo ako je ovaj datum isti ili noviji od ugrađene kopije.
- `current.matches` – sve utakmice tekuće sezone, za sve timove:
  - `r` kolo, `d` datum `DD.MM.YYYY` (ili `null`), `h` domaćin, `a` gost (kratki nazivi kao u `current.teams`)
  - `s` rezultat `"X:Y"` ili `null` ako nije odigrano / nema rezultata
  - opcionalno: `g` strijelci Koline (npr. `"Polovina 3, Karahodža"`), `time` (`"13:00"`), `kickoff` (ISO, npr. `"2026-11-22T13:00:00+01:00"` – uključuje odbrojavanje)
- `history` / `summary` – prošle sezone (ne mijenjati osim kad se sezona završi).

Tabela, lista rezultata, raspored, kartica „Sljedeća utakmica“ i napomena ispod tabele **računaju se automatski** iz `current.matches`.

## Nova sezona
Premjesti utakmice Koline iz `current.matches` u `history["YYYY-YYYY"]` (format kao ostale sezone), dodaj red u `summary`, pa u `current` upiši novu sezonu, timove i raspored. Dodaj i dugme sezone u `index.html` (`.season-tabs`).

## Izvori podataka
- SportDC: https://sportdc.net/league/6630-jkl-fs-bpk-gorazde-26-27
- Facebook stranica kluba (rezultati i strijelci)
