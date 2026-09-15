# CotaCurva

**Gerador de curvas de nível** — ferramenta web (um único arquivo HTML) que gera curvas de nível a partir de dados de satélite/MDE ou de pontos levantados em campo, com exportação para **DXF, KML, PNG e PDF**.

Criado por **Prof. Me. Rodrigo Gonçalves (Oswy)** · 📺 [youtube.com/@ProfOswy](https://www.youtube.com/@ProfOswy)

---

## Recursos

- Geração por **área no mapa** (satélite/relevo) ou por **pontos de campo** (UTM + cota, via superfície TIN).
- Duas equidistâncias: **mestra** (rotulada) e **intermediária**.
- Degradê de cores das altitudes configurável e tamanho da fonte dos rótulos ajustável.
- **Perfil de elevação** (corte) entre dois pontos, com leitura interativa ao passar o cursor sobre a linha.
- Exportações:
  - **DXF** em UTM/WGS84 — abre centralizado no *Model*, polilinhas 3D na cota, curvas mestras rotuladas;
  - **KML** em coordenadas geográficas;
  - **PNG** e **PDF** da carta de curvas (com polígono, legenda, barra de escala e créditos) e também do perfil.
- Aviso automático na tela quando os servidores de mapa estão instáveis.

## Como usar

1. Abra o `index.html` no navegador.
2. **Aba "Mapa / satélite":** clique em *Selecionar área (polígono)*, marque os vértices e feche (duplo-clique); escolha a fonte de elevação e os parâmetros; clique em *Gerar curvas*.
3. **Aba "Pontos de campo":** cole os pontos no formato `E N Z` (um por linha), informe zona e hemisfério UTM e gere.
4. Exporte no formato desejado (DXF, KML, PNG ou PDF).

## Executando / hospedando

- **Local:** basta abrir o `index.html`. Para maior estabilidade das requisições de rede, sirva a pasta com um servidor local:

  ```bash
  python -m http.server
  ```

  e acesse `http://localhost:8000`.

- **GitHub Pages:** renomeie o arquivo principal para `index.html`, faça o commit e ative o Pages em *Settings → Pages* (branch `main`). O link ficará em `https://profoswy.github.io/CotaCurva/`.

## Fontes de dados e atribuição

- **Relevo (padrão):** AWS Terrain Tiles (Mapzen/Tilezen) — uso sob atribuição.
- **Elevação alternativa:** Open-Meteo (Copernicus ~90 m) e Open-Elevation (SRTM ~30 m).
- **Mapa e satélite:** Esri (World Imagery / World Street Map / Reference).
- **Bibliotecas:** Leaflet, D3 e jsPDF.

## Limitações

Os dados de elevação de satélite têm resolução aproximada de **~30–90 m** e destinam-se a **ensino, estudo regional e anteprojeto**. **Não substituem levantamento topográfico** (estação total, GNSS RTK ou aerofotogrametria) para projeto executivo. No modo de pontos de campo, a precisão é a do seu próprio levantamento.

## Licença

Todos os direitos reservados — veja [LICENSE.md](LICENSE.md). Uso pessoal e educacional é permitido; redistribuição, modificação e remoção de créditos exigem autorização do autor.

© 2026 Prof. Me. Rodrigo Gonçalves (Oswy)
