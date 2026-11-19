# Geocodificador em Lote

## Executar
Requer Node.js 18+.

```bash
npm install
```
Copie `.env.example` para `.env`, configure um User-Agent identificável com contato real em `APP_USER_AGENT` e execute:

```bash
npm start
```

Abra `http://localhost:3000`.

## Provedores
- Nominatim: padrão; backend serializa requisições a pelo menos 1,1 s. O serviço público tem política de uso restritiva e não é adequado a cargas grandes.
- Photon: alternativa pública sem SLA.
- Mapbox: configure `GEOCODER_PROVIDER=mapbox` e `MAPBOX_ACCESS_TOKEN`.
- Google: configure `GEOCODER_PROVIDER=google` e `GOOGLE_MAPS_API_KEY`.

As chaves ficam no servidor. Em hospedagem pública, adicione autenticação, cotas e proteção contra abuso antes de disponibilizar o endpoint.

## Entrada e saída
TXT/CSV/XLSX ou texto colado. Formato com coordenadas: `Nome | latitude, longitude`. Exporta TXT, XLSX, KML e KMZ. Clique em um ponto e depois no mapa para reposicioná-lo.

**Importante:** o KML/KMZ desenha uma linha reta entre pontos válidos na ordem da lista. Isso não é roteamento viário. Use OSRM/editor de rotas do BusMap para gerar o percurso pelas ruas e confira os pontos manualmente.
