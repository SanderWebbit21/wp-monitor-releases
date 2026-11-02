# Licentie WP-Monitor

Copyright © 2026 Webbit21. Alle rechten voorbehouden, behalve wat hieronder staat.

## 1. Gebruik

WP-Monitor ("de software") is gratis te gebruiken voor **privé en niet-commercieel gebruik**.

Dat mag:
- de software downloaden, installeren en gebruiken op je eigen computers en NAS;
- de link naar deze pagina met anderen delen.

Dat mag niet zonder schriftelijke toestemming van Webbit21:
- de software verkopen, verhuren of commercieel inzetten, ook niet als onderdeel van een dienst;
- de bestanden aanpassen, decompileren of onder een andere naam verspreiden;
- de bestanden zelf ergens anders aanbieden om te downloaden. Deel de link naar deze pagina.

## 2. Geen garantie, geen aansprakelijkheid

De software wordt geleverd **"zoals hij is"**, zonder enige garantie, uitdrukkelijk of stilzwijgend, ook niet op juistheid, geschiktheid of ononderbroken werking.

De software leest de warmtepomp alleen uit en wijzigt standaard geen instellingen. De getoonde cijfers kunnen afwijken van de werkelijkheid; voor bijvoorbeeld energie- en kostencijfers zijn het schattingen. Gebruik is **op eigen risico**. Webbit21 is niet aansprakelijk voor directe of indirecte schade die ontstaat door het gebruik van de software, of door beslissingen die op basis van de getoonde gegevens worden genomen.

## 3. Merken

WP-Monitor is een onafhankelijk project. Er is geen band met Alpha Innotec, ait-deutschland GmbH of de makers van de Luxtronik-regelaar, en de software is niet door hen goedgekeurd. Alle merknamen zijn eigendom van hun respectieve eigenaars.

## 4. Onderdelen van derden

De software bevat open-source onderdelen. Die vallen onder hun eigen licenties, en voor die onderdelen gaan die licenties boven deze licentie. De broncode en volledige licentieteksten staan op de projectpagina's hieronder.

| Onderdeel | Licentie | Bron |
|---|---|---|
| Python 3.12 | PSF License | https://www.python.org |
| Flask, Werkzeug, Jinja2, MarkupSafe, ItsDangerous, Click | BSD-3-Clause | https://palletsprojects.com |
| Blinker | MIT | https://github.com/pallets-eco/blinker |
| luxtronik (python-luxtronik) | MIT | https://github.com/Bouni/python-luxtronik |
| certifi | MPL-2.0 | https://github.com/certifi/python-certifi |
| pywebview *(Mac)* | BSD-3-Clause | https://github.com/r0x0r/pywebview |
| pystray *(Windows)* | LGPL-3.0 | https://github.com/moses-palmer/pystray |
| Pillow *(Mac/Windows)*, inclusief meegeleverde beeldbibliotheken | MIT-CMU (HPND) | https://python-pillow.org |
| PyObjC *(Mac)* | MIT | https://github.com/ronaldoussoren/pyobjc |
| six | MIT | https://github.com/benjaminp/six |
| PyInstaller-bootloader *(Mac/Windows)* | GPL-2.0 met bootloader-uitzondering | https://pyinstaller.org |
| Docker-basisimage `python:3.12-slim` *(Docker)* | Debian-pakketten onder hun eigen licenties | https://hub.docker.com/_/python |

**LGPL (pystray):** je hebt het recht pystray te vervangen door een eigen of gewijzigde versie. De broncode staat via de link hierboven. Wil je hierbij hulp, of de objectbestanden om de app opnieuw te bundelen? Vraag ernaar via de Issues van deze repository.

## 5. Weergegevens

Weer en weersverwachting: **[Open-Meteo.com](https://open-meteo.com/)**, gebruikt onder de licentie [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). De gegevens worden live opgevraagd en niet aangepast, behalve dat ze worden weergegeven en gemiddeld.
