# Even op Schier

Persoonlijk weekendboekje voor 6 tot en met 8 november 2026 in Hotel van der Werff.

Open `index.html` direct in een browser. Geen installatie of build nodig. De dagtabs zijn met muis en toetsenbord te bedienen; de persoonlijke paklijst wordt waar mogelijk lokaal in de browser bewaard. Bij afdrukken verschijnen alle drie de dagen.

Foto's, lettertypen en Lucide-iconen worden online geladen. Een internetverbinding is daarvoor nodig. Hotelbeelden zijn afkomstig van de website van Hotel van der Werff, met fotografie van Foppe Schut; bronvermelding staat op de pagina. Vraag toestemming voor eventueel breder openbaar hergebruik van de foto's.

## Inhoud

De boottijden zijn overgenomen uit de aangeleverde planning, niet onafhankelijk bevestigd voor deze afvaarten. Andere tijden en de fietsronde zijn suggesties. Controleer dienstregeling, openingstijden, fietspaden, het mannenkoor en de afspraken over eigen wijn kort voor vertrek. De fietsroute is een kaartvoorstel, geen gecontroleerde GPX-route.

## Container

De Dockerfile serveert de pagina via Nginx zonder rootrechten op poort 8080:

```sh
docker build -t schiermonnikoog-2026 .
docker run --rm -p 8080:8080 schiermonnikoog-2026
```

De GitHub-workflow bouwt bij pull requests en publiceert bij pushes naar `main` naar `ghcr.io/<organisatie>/<repository>:latest`. De containernaam wordt automatisch gelijk aan de repositorynaam, in kleine letters. Publicatie onder AFASGroep vereist een repository binnen die organisatie en ingeschakelde GitHub Actions. Er zijn geen applicatiegeheimen nodig.

## Deelbare website

De workflow `.github/workflows/pages.yml` publiceert alleen `index.html` via GitHub Pages bij wijzigingen op `main` of een handmatige start. Activeer hiervoor in de repository Settings > Pages de bron GitHub Actions. De workflow toont na een succesvolle publicatie de daadwerkelijke website-URL.

Gebruik een private repository binnen AFASGroep. GitHub Pages voor private repositories vereist een geschikt organisatieabonnement en toestemming vanuit de organisatie. Een private broncoderepository betekent niet dat de gepubliceerde website ook prive is: controleer de toegangsinstellingen voordat je de link deelt. Vraag toestemming voor openbaar gebruik van de hotelfoto's.

Publicatiestatus: lokaal voorbereid, nog niet online gepubliceerd. GitHub CLI ontbreekt op deze computer en moet via het bedrijfsportal worden geinstalleerd. Daarna kunnen de repository, pull request en Pages-instellingen worden geregeld; er zijn geen losse wachtwoorden of applicatiegeheimen nodig.