# Cobertura Ceará

Mapa interativo de cobertura móvel de todo o Ceará. Compara Claro, Vivo, TIM e Brisanet em 3G, 4G e 5G, permitindo combinar tecnologias, consultar pontos e analisar rotas.

Site estático, sem backend. Dados, bibliotecas e aplicação estão incluídos no `index.html`. Abra o arquivo em um navegador moderno ou publique a branch `main` no GitHub Pages, usando a pasta raiz.

## Uso no celular

- Mapa em tela inteira, com painel inferior recolhido, intermediário ou expandido. Arraste a alça ou toque nela para mudar a posição.
- Busca de município com sugestões locais e botão de localização, acionado apenas quando solicitado.
- Toque no mapa para consultar cartões de Claro, Vivo, TIM e Brisanet. O ponto permanece visível acima do painel.
- Combine 3G, 4G e 5G na aba Camadas; limiares e transparência ficam em Mais opções.
- Legenda recolhível e atalho para visualizar todo o Ceará.
- Tema claro ou noturno automático, seguindo o sistema, inclusive quando ele muda com a página aberta.

## Rotas e recomendação

Escolha origem, destino e, opcionalmente, um município intermediário. As sedes dos 184 municípios vêm de Localidades do Brasil 2022, do IBGE. A rota local é aproximada pelas vias principais do OpenStreetMap; respeita sentidos de circulação cadastrados, mas não é uma ferramenta de navegação nem cobre todas as restrições de conversão e acessos urbanos. Há uma opção de traçado online via OSRM; a indisponibilidade desse serviço retorna à malha local.

A análise corta o traçado nos polígonos originais e mede seu comprimento, sem amostragem regular de pontos. Usa exclusivamente os limiares de sinal mais alto: −82 dBm em 3G e −90 dBm em 4G/5G. Trechos fora do Ceará não entram no denominador. A união de redes evita contar o mesmo trecho duas vezes.

O ranking usa 60% de peso para 4G, 30% para 5G e 10% para 3G. Dados não publicados são excluídos e os pesos restantes normalizados, com informação parcial identificada. Esse índice expressa uma preferência de cobertura, não velocidade medida nem garantia de serviço. Percentuais são arredondados a 1%.

## Fontes e critérios

- Cobertura prevista em ambiente aberto: [Anatel / Mosaico](https://sistemas.anatel.gov.br/se/public/cmap.php), consultada em 08/10/2026. Publicações: 3G em 21/08/2026, 4G em 03/10/2026 e 5G em 07/09/2026. Brisanet 3G não foi publicado nesse catálogo.
- Limites e municípios: [IBGE](https://servicodados.ibge.gov.br/api/docs/malhas?versao=3).
- Vias principais: © [OpenStreetMap contributors](https://www.openstreetmap.org/copyright), dados sob ODbL.
- Leaflet: BSD 2-Clause; aviso de licença incluído no HTML.
- Interface inspirada em [Material 3 Expressive](https://m3.material.io/).

As manchas são previsões, não medições no local. Não representam velocidade nem garantem cobertura dentro de imóveis. Os tons distinguem sobreposições de tecnologias da mesma operadora; a consulta mostra os limiares de sinal separadamente. Não há acréscimo automático de roaming.

## Atualizar

Substitua `index.html` pela versão nova e envie um commit para `main`. O GitHub Pages publica a atualização.
