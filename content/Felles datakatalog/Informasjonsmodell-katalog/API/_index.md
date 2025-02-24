---
title: API
weight: 2
---
Her følger en kort beskrivelse informasjonsmodell-katalogens API, samt eksempel på bruk med [curl](https://curl.haxx.se/)..
## Detaljer
* Server: `https://fellesdatakatalog.digdir.no/api/informationmodels`
* Tilbyr: `application/json`

| <a>Oppføring i API-katalogen</a> | <a href="https://raw.githubusercontent.com/brreg/openAPI/master/specs/informationmodel-cat.json" target="_blank"><u>Lenke direkte til spesifikasjon (openAPI v3)</u></a> |
| --------------- | --------- |

## Eksempel på spørringer
Alle informasjonsmodeller:
```
curl -H "Accept: application/json" https://fellesdatakatalog.digdir.no/api/informationmodels
```
En spesifik informasjonsmodell basert på id:
```
curl -H "Accept: application/json" https://fellesdatakatalog.digdir.no/api/informationmodels/<id>
```
En  enkelt søk etter modeller med ordet "summert":
```
curl -H "Accept: application/json" https://fellesdatakatalog.digdir.no/api/informationmodels?q=summert
```
