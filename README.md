# WP-Monitor

Live dashboard voor een **Alpha Innotec-warmtepomp met Luxtronik 2.1-regelaar**.
De app leest de warmtepomp rechtstreeks uit via je thuisnetwerk. Dat gaat sneller dan de cloud-apps.
Hij **leest standaard alleen**. Alleen de Docker-versie kan, nadat je een pincode hebt ingesteld, een paar instellingen van de warmtepomp wijzigen.

Je ziet een live installatieschema (bodembron, warmtepomp, vloer, boiler), temperaturen, vermogen, compressor-frequentie, wat er op dit moment actief is, en het weer.

## Welke versie past bij jou?

| | Mac / Windows | Docker (NAS) |
|---|---|---|
| Live dashboard en schema | ✓ | ✓ |
| Draait | als je de app open hebt | 24/7 |
| Bekijken | eigen venster (Mac) of browser (Windows), op die computer | browser, vanaf elk apparaat in huis |
| Geschiedenis, grafieken, energie per dag/maand, inzichten | – | ✓ |
| Instellingen wijzigen (met pincode) | – | ✓ kamertemperatuur, stooklijn, warm water, bedrijfsstand |

Wil je alleen af en toe meekijken, neem dan de Mac- of Windows-app. Wil je ook de geschiedenis bijhouden en heb je een NAS, neem dan Docker.

## Downloaden

Deze links wijzen altijd naar de nieuwste versie:

| Computer | Download |
|---|---|
| Mac met Apple-chip (M1, M2, M3, M4…) | [WP-Monitor-mac-arm64.zip](https://github.com/SanderWebbit21/wp-monitor-releases/releases/latest/download/WP-Monitor-mac-arm64.zip) |
| Mac met Intel-processor (tot ~2020) | [WP-Monitor-mac-intel.zip](https://github.com/SanderWebbit21/wp-monitor-releases/releases/latest/download/WP-Monitor-mac-intel.zip) |
| Windows 10 / 11 | [WP-Monitor-windows.exe](https://github.com/SanderWebbit21/wp-monitor-releases/releases/latest/download/WP-Monitor-windows.exe) |
| NAS met Docker (Intel/AMD) | [WP-Monitor-docker-amd64.tar](https://github.com/SanderWebbit21/wp-monitor-releases/releases/latest/download/WP-Monitor-docker-amd64.tar) |
| NAS met Docker (ARM64) | [WP-Monitor-docker-arm64.tar](https://github.com/SanderWebbit21/wp-monitor-releases/releases/latest/download/WP-Monitor-docker-arm64.tar) |

Weet je niet welke Mac je hebt? Kies  → *Over deze Mac*. Staat daar "Chip Apple M…", dan heb je een Apple-chip.

Wat er per versie veranderd is, staat bij [Releases](https://github.com/SanderWebbit21/wp-monitor-releases/releases).

---

## Installeren op de Mac

**1. Uitpakken**
- Dubbelklik de zip om hem uit te pakken.
- Sleep **WP-Monitor.app** naar *Programma's*.

**2. Eerste keer openen** (eenmalig, omdat de app niet bij Apple is geregistreerd)
1. Open *Programma's* en dubbelklik op WP-Monitor.
2. Je krijgt de melding *"WP-Monitor niet geopend – Apple kon niet verifiëren…"*. Klik op **Gereed**, níet op "Verplaats naar prullenmand".
3. Open **Systeeminstellingen → Privacy en beveiliging**.
4. Scrol helemaal naar beneden tot *Beveiliging*. Daar staat *"WP-Monitor werd geblokkeerd…"*. Klik op **Toch openen** en voer het wachtwoord van je Mac in.
5. Open WP-Monitor opnieuw en klik in de nieuwe melding op **Open**.

Daarna start de app voortaan gewoon met een dubbelklik.

> Zie je bij stap 4 geen melding? Open de app eerst nog een keer (stap 1) en ga dan meteen naar Privacy en beveiliging. De melding staat er maar een tijdje.
> Vraagt de Mac of WP-Monitor apparaten in je lokale netwerk mag zoeken? Klik op **Sta toe**. Anders kan de app de warmtepomp niet vinden.

**3. Dagelijks gebruik**
Het dashboard opent in een eigen venster. Je start de app vanuit *Programma's* of het Dock. Sluit je het venster, dan stopt de app.

---

## Installeren op Windows

**1. Neerzetten**
- Er hoeft niets geïnstalleerd te worden: het is één programmabestand.
- Zet `WP-Monitor-windows.exe` op een vaste plek, bijvoorbeeld in *Documenten* of op het bureaublad. Laat hem niet in *Downloads* staan, dan gooi je hem niet per ongeluk weg.

> Blokkeert de browser de download ("wordt niet vaak gedownload")? Klik in Edge op de drie puntjes → **Behouden** → **Meer weergeven** → **Toch behouden**.

**2. Eerste keer openen** (eenmalig, omdat de app niet bij Microsoft is geregistreerd)
1. Dubbelklik op `WP-Monitor-windows.exe`.
2. Je krijgt het blauwe venster *"Windows heeft uw pc beveiligd"*. Klik op **Meer informatie**, het kleine linkje onder de tekst.
3. Klik op **Toch uitvoeren**.

Daarna start de app voortaan gewoon met een dubbelklik.

> De eerste keer opstarten duurt een paar seconden, omdat de app zichzelf dan uitpakt. Even wachten en niet nog een keer dubbelklikken.
> Vraagt Windows Firewall om toegang? Kies alleen **Privénetwerken** en klik op **Toegang toestaan**.

**3. Dagelijks gebruik**
Rechtsonder in de taakbalk, naast de klok, staat een huisje-icoon. Klik er met de rechtermuisknop op voor **Open dashboard** of **Stoppen**.
Zie je het icoon niet? Klik op het pijltje **^** naast de klok, dan staat het in het uitklapmenu.

**Automatisch starten met Windows** (optioneel): druk op Windows-toets + R, typ `shell:startup` en druk op Enter. Zet in die map een snelkoppeling naar `WP-Monitor-windows.exe`.

---

## Instellen (Mac en Windows)

De eerste keer opent de browser vanzelf met de setup-pagina.
1. Klik op **Zoek op mijn netwerk**. De app zoekt de warmtepomp op je thuisnetwerk.
2. Bij de gevonden warmtepomp klik je op **Gebruiken**. Vul eventueel een naam in voor de titel.
3. Klik op **Opslaan en naar dashboard**.

De computer en de warmtepomp moeten op hetzelfde netwerk zitten. De warmtepomp moet met een netwerkkabel aangesloten zijn; de app gebruikt poort 8889.

---

## Docker (NAS)

Voor wie de monitor 24/7 op een NAS wil laten draaien. Deze versie bewaart ook de **geschiedenis**: grafieken, energie per dag en maand, en inzichten.

1. **Image laden.** Synology: *Container Manager → Image → Toevoegen → Uit bestand toevoegen*. Of op de commandline:
   `docker load -i WP-Monitor-docker-amd64.tar`
2. **Starten:**
   ```bash
   docker run -d --name wp-monitor --restart unless-stopped --network host \
     -v /pad/naar/data:/data wp-monitor:latest
   ```
   Daarna open je `http://<ip-van-de-nas>:5055`.
3. Met **host-netwerk** kan *Zoek op mijn netwerk* de warmtepomp vinden. Zonder host-netwerk gebruik je `-p 5055:5055` en vul je het IP van de warmtepomp handmatig in.

- Instellingen en meetdata staan in `/data`. De container draait niet als root.
- Op de setup-pagina kun je een pincode instellen. Zodra die er is, vraagt de setup-pagina eerst om die pincode.
- **Instellingen wijzigen** zet je op de setup-pagina aan. Daarvoor moet er een pincode zijn. Daarna kun je vanuit het dashboard de kamertemperatuur, de stooklijn (eind- en voetpunt), de warmwatertemperatuur en de bedrijfsstand voor verwarmen en warm water aanpassen. Zonder pincode leest de app alleen. Wijzigen is op eigen risico: noteer vooraf je huidige instellingen.
- Omgevingsvariabelen: `PORT` (5055), `TZ` (Europe/Amsterdam), `WP_IP` (zet het IP vast; de setup-pagina gaat dan op slot), `WP_PLACE`/`WP_LAT`/`WP_LON` (plaats voor het weer).

---

## Goed om te weten

- De app praat alleen met de warmtepomp op je eigen netwerk, plus een weerdienst (Open-Meteo) voor de verwachting. Er gaat geen data naar een cloud.
- Twee keer per dag kijkt de app op deze pagina of er een nieuwere versie is. Zo ja, dan zie je bovenin het dashboard een melding met een downloadknop. Daarbij wordt niets over jou of je warmtepomp verstuurd. In Docker zet je dit uit met `WP_UPDATE_CHECK=0`.
- De app is gemaakt voor en getest met een Alpha Innotec-warmtepomp met bodembron en Luxtronik 2.1. Andere Luxtronik-warmtepompen werken waarschijnlijk ook, maar niet elk onderdeel van het schema zal dan kloppen.
- Weergegevens: [Open-Meteo.com](https://open-meteo.com/) (CC BY 4.0).

## Licentie

De app is gratis voor privé, niet-commercieel gebruik. Hij wordt geleverd zonder garantie en het gebruik is op eigen risico. Er is geen band met Alpha Innotec of de makers van Luxtronik.
Meer staat in [LICENSE.md](LICENSE.md), samen met de gebruikte open-source onderdelen.

© 2026 Webbit21
