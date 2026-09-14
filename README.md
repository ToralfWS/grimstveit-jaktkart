# Grimstveit jaktkart

Et enkelt, statisk og mobilvennlig jaktkart for Grimstveit jaktområde i Nissedal.

Kartet bruker Leaflet, Kartverkets topografiske WMTS-kart og en lokal GeoJSON-fil i
`data/grimstveit-eiendommer.geojson`. Eiendomsgrensene lastes derfor ikke fra
Kartverkets eiendoms-API når siden åpnes, og løsningen trenger ingen backend.

## Eiendommer

Kartet inneholder disse 11 matrikkelenhetene:

`10/1`, `10/2`, `10/7`, `11/2`, `12/4`, `12/5`, `12/6`, `12/8`, `19/10`, `13/4` og `8/1`.

**11/84 mangler.** Eiendoms-API-et returnerte ikke denne matrikkelenheten, og den er
bevisst utsatt til en senere versjon.

## Lokal kjøring

Siden må åpnes via en lokal HTTP-server fordi nettlesere normalt blokkerer `fetch`
av GeoJSON fra `file://`:

```sh
python3 -m http.server 8000
```

Åpne deretter <http://localhost:8000>.
