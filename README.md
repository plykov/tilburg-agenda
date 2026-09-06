# Tilburg Agenda inbox

`events.json` is the public daily delivery. Tilburg Agenda auto-imports it on load, every 30s, and when you press Update.

- Schema: `tilburg.agenda.v1`
- Fields: `deliveryId`, `generatedAt`, `source`, `headline`, `events[]`
- Event `category`: festival | music | theater | church | nightlife | family
- Event `status`: free | on-sale | sold-out | cancelled

The 08:00 Europe/Amsterdam briefing overwrites this file. The app fetches this raw URL and same-origin `/events.json`, then keeps whichever envelope has the newer `generatedAt`.
