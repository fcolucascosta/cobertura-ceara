# Cobertura Ceará

Mapa interativo de cobertura móvel do Ceará, com foco inicial entre Sobral e Fortaleza. Compara Claro, Vivo, TIM e Brisanet em 3G, 4G e 5G, permitindo combinar tecnologias e consultar pontos no mapa.

Site estático, sem backend. Dados, bibliotecas e aplicação estão incluídos no `index.html`. Abra o arquivo em um navegador moderno ou publique a branch `main` no GitHub Pages, usando a pasta raiz.

## Fontes e critérios

- Cobertura prevista em ambiente aberto: [Anatel / Mosaico](https://sistemas.anatel.gov.br/se/public/cmap.php), consultada em 08/10/2026. Publicações: 3G em 21/08/2026, 4G em 03/10/2026 e 5G em 07/09/2026. Brisanet 3G não foi publicado nesse catálogo.
- Limites e municípios: [IBGE](https://servicodados.ibge.gov.br/api/docs/malhas?versao=3).
- Vias principais: © [OpenStreetMap contributors](https://www.openstreetmap.org/copyright), dados sob ODbL.
- Leaflet: BSD 2-Clause; aviso de licença incluído no HTML.
- Interface inspirada em [Material 3 Expressive](https://m3.material.io/).

As manchas são previsões, não medições no local. Não representam velocidade nem garantem cobertura dentro de imóveis. Os tons distinguem sobreposições de tecnologias da mesma operadora; a consulta mostra os limiares de sinal separadamente. Não há acréscimo automático de roaming.

## Atualizar

Substitua `index.html` pela versão nova e envie um commit para `main`. O GitHub Pages publica a atualização.
