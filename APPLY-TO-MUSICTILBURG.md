# Apply to musictilburg.grok.me — HipSy chapel miss

Desk date: Saturday 12 September 2026 (Europe/Amsterdam).  
App: **Musictilburg** (Tilburg Agenda) at musictilburg.grok.me.  
Daily job: 08:00 Amsterdam → GitHub `plykov/tilburg-agenda` `events.json`.

**Status:** applied to the live inbox (delivery `005209ec-74ad-4dc1-a21e-6517efad4a27`, generated 12 Sep 16:05). Tap **Update** on musictilburg to merge. Next 08:00 run already has the source list below.

This is the briefing the morning sweep missed, why, the sources to keep checking, and the records to merge. Yoga / tantra / healing HipSy listings stay out.

---

## 1. The miss

[Best of Chopin — Alexandre Lutz García](https://hipsy.nl/event/204483-best-of-chopin-tilburg)

| | |
|---|---|
| When | Sunday 13 Sep 2026, 15:30–16:45 (doors 15:00) |
| Where | Concertzaal Het Cenakel, Cenakel 77-60, 5022 KK Tilburg |
| Who | Neoklassieke Concerten Nederland · pianist Alexandre Lutz García |
| Tickets | **Sold out** — €28.50 standard and €24.50 kleinere beurs |
| Programme | Nocturnes, Ballade no. 1, Scherzo no. 2 · chapel Steinway |

**Why 013 / Schouwburg / Songkick never had it.** Het Cenakel is a former monastery chapel (Steinway D, Van Vulpen organ). Touring neo-classical nights are sold on **HipSy**, not on pop-venue feeds. The 08:00 job only checked 013, Schouwburg, Paradox, organ calendars, Partyflock, etc.

Same promoter, same pattern: [Onder Einaudi’s Vleugels](https://www.deleest.nl/programma/onder-einaudi-s-vleugels-fsbk) — Sun 27 Sep 15:30, Theater De Leest (Rabozaal), Waalwijk, €31.50. Hired hall, not De Leest’s own series.

Same miss class, different chapel: Gyo Kretz — Candlelight Tour, Sat 7 Nov 20:00, Rooi Harten Klooster (WAU Effect, Bredaseweg), organiser Resonated Harmonies, HipSy only.

---

## 2. Sources the daily automation must open every run

Add this block under the existing venue list. Include Concert / Live muziek / Optreden / klassiek / piano / koor / orgel / candlelight. **Skip** yoga, tantra, breathwork, psoas, sound-healer trainings, SUP, workshops, healing — unless the listing is a public concert.

```
INTIMATE HALLS & INDEPENDENT TICKETS
- HipSy: ?query=Tilburg | Cenakel | Waalwijk | Breda | klooster
  Organisers: hipsy.nl/neoklassieknederland and Resonated Harmonies
- Concertzaal Het Cenakel — https://www.cenakel.nl/
  Series: Betoverende Pianisten, S.M.E.T. kamermuziek (Sun 12:30),
  De Link (1st/3rd Tue), orgel, Bachcantates, Tilburgs Vocaal Ensemble,
  Jong Talent, Korendag / Maand van de Koren, plus any promoter hiring the chapel
- muziekladder.nl/locaties/cenakel.nl  (dates the homepage buries)
- delink.nl/concertagenda/
- Rooi Harten Klooster / WAU Effect (Bredaseweg) — HipSy "Rooi Harten"
- We Are Public, Ticketkantoor, Stager, Eventbrite Tilburg concerts
- Theater De Leest Waalwijk — https://www.deleest.nl/
Also hunt: Café Weemoed, 013 Next Stage, Studio Tilburg, Cul,
Knoflookfeest / Theresiaplein, Open Monumentendag, Bosvreugd Cultuurbos
```

Church / classical / youth section must include **chapel recitals** (Cenakel + Rooi Harten), not only Heuvelse Kerk / Pauluskerk / city organist.

Mint a **new UUID** `deliveryId` on every run. Write `events.json` on `plykov/tilburg-agenda` main.

---

## 3. Records to merge (stable ids)

Category `church` for chapel recitals so the Church filter catches them.

```json
{
  "id": "chopin-cenakel-2026-09-13",
  "title": "Best of Chopin — Alexandre Lutz García",
  "date": "2026-09-13",
  "time": "15:30",
  "end": "16:45",
  "venue": "Concertzaal Het Cenakel",
  "city": "Tilburg",
  "category": "church",
  "status": "sold-out",
  "price": "Sold out",
  "note": "Nocturnes, Ballade no. 1, Scherzo no. 2. Chapel Steinway. Both ticket tiers sold out.",
  "url": "https://hipsy.nl/event/204483-best-of-chopin-tilburg"
}
```

| id | date | title | venue | status |
|---|---|---|---|---|
| `chopin-cenakel-2026-09-13` | 13 Sep 15:30 | Best of Chopin — Alexandre Lutz García | Het Cenakel | sold-out |
| `knoflookfeest-2026-09-13` | 13 Sep | Legiana Collective — Knoflookfeest | Theresiaplein | free |
| `korendag-cenakel-2026-09-20` | 20 Sep | Korendag — Maand van de Koren | Het Cenakel | on-sale |
| `einaudi-waalwijk-2026-09-27` | 27 Sep 15:30 | Onder Einaudi’s Vleugels | De Leest, Waalwijk | on-sale €31.50 |
| `smet-skazka-2026-10-11` | 11 Oct 12:30 | S.M.E.T. — Skazka Quartet | Het Cenakel | on-sale |
| `scriabin-sporck-2026-10-13` | 13 Oct | Tussen Scriabin en Sporck | Het Cenakel | on-sale |
| `delink-cenakel-2026-10-20` | 20 Oct | De Link — newly composed | Het Cenakel | on-sale |
| `gyo-kretz-rooi-harten-2026-11-07` | 7 Nov 20:00 | Gyo Kretz — Candlelight Tour | Rooi Harten Klooster | on-sale |

Cenakel looking-ahead on muziekladder (do not invent times): 8 Nov + 13 Dec SMET; 15 Nov + 20 Dec Betoverende Pianisten; De Link 3 Nov, 17 Nov, 1 Dec, 15 Dec.

Same-class HipSy later: Schindler’s List violin classics Tilburg 23 May 2027. Skip OM Chanting / Way of Yoga / Soulstar.

---

## 4. How Musictilburg picks this up

1. Overwrite GitHub `plykov/tilburg-agenda` `events.json` (schema `tilburg.agenda.v1`, new `deliveryId`, `generatedAt` with Amsterdam offset).
2. On the device, tap **Update**. Merge keeps existing cards; new ids get the `new` tag.
3. Filter **Tomorrow** + **Church** for Chopin; **Looking ahead** + **Church** for Cenakel series and Rooi Harten.

Do not paste yoga/healing HipSy pages into the envelope. HipSy concert permalinks count as official `url`.
