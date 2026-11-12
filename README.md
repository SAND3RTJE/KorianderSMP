# KorianderSMP website

Website van KorianderSMP (`koriandersmp.nl`): joininfo voor Java en Bedrock, live serverstatus, een galerij, de wereldkaart en Twitch-streams van Fabian en Sander. De site is volledig statisch en draait op Cloudflare Pages. Er zijn geen scripts, GitHub Actions of secrets meer nodig.

## Bestanden

| Pad | Wat het is |
|---|---|
| `site/index.html` | De hele website (HTML, CSS en JavaScript in één bestand) |
| `site/img/` | Screenshots (webp, al verkleind) |
| `site/_headers` | Beveiligingsheaders voor Cloudflare Pages |
| `site/robots.txt` | Zoekmachine-instructie |

Stel in Cloudflare Pages als build output directory `site` in, zonder build command.

## Aanpassen

Bewerk `site/index.html` via GitHub (potloodje) en klik op Commit changes. Cloudflare zet het binnen een minuut online.

- Regels: zoek `<!-- Pas deze regels aan -->`.
- Serveradres of poort: zoek `play.koriandersmp.nl` en `25639` (staan op meerdere plekken).
- Twitch-kanalen: zoek `elitegooner37` en `sand3rtje`.
- Discord-link: zoek `discord.gg/Jcuf9hXg4H`.
- Live wereldkaart: vul `MAP_URL` in (zoek `const MAP_URL`). Leeg = de knop blijft verborgen en alleen de foto van de kaart staat er.
- Foto's: zet nieuwe `.webp`-bestanden in `site/img/` en kopieer een `<button class="shot">`-blok in de galerij.

## Statistieken van bezoekers

Zet in Cloudflare Pages bij Metrics, Web Analytics aan. Dat kan zonder code te wijzigen.

## Serverinfo

- Java: `play.koriandersmp.nl`
- Bedrock: `play.koriandersmp.nl`, poort `25639`
- Het DNS-record voor `play` moet op **DNS only** staan (geen Cloudflare-proxy).

## Opruimen na de overstap

Verwijder uit de oude repo: `maak_stats.py`, `haal_aankondigingen.py`, `.github/workflows/` (beide yml-bestanden), `site/stats.json`, `site/aankondigingen.json`, `site/aankondigingen.html` en `site/statistieken.html`. Verwijder ook de oude secrets (SFTP en Discord), zeker het SFTP-wachtwoord.
