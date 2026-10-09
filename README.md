# Cobertura Ceará

Mapa interativo de cobertura móvel de todo o Ceará. Compara Claro, Vivo, TIM e Brisanet em 3G, 4G e 5G, permitindo combinar tecnologias, consultar pontos e analisar rotas.

Site estático, sem backend. Dados, bibliotecas e aplicação estão incluídos no `index.html`. Abra o arquivo em um navegador moderno ou publique a branch `main` no GitHub Pages, usando a pasta raiz.

## Uso no celular

- Mapa em tela inteira, com painel inferior recolhido, intermediário ou expandido. Arraste a alça ou toque nela para mudar a posição.
- Busca de municípios e localidades com sugestões locais e botão de localização, acionado apenas quando solicitado. Bairros, vilas e povoados aparecem conforme o zoom.
- Toque no mapa para consultar a matriz de operadoras × redes e os cartões de Claro, Vivo, TIM e Brisanet. O ponto permanece visível acima do painel.
- Combine 3G, 4G e 5G na aba Camadas. Todo o mapa usa exclusivamente os limiares de sinal mais alto.
- Legenda recolhível e atalho para visualizar todo o Ceará.
- Tema inicialmente automático, com seletor claro/escuro que memoriza a escolha e opção para voltar ao tema do aparelho.
- Fonte variável Roboto Flex, do Google Fonts, embutida no arquivo, com textos maiores nos controles e resultados.

## Cores e desempenho

A comparação automática adapta a escala azul à seleção. Com uma ou duas operadoras, tons claros indicam uma rede presente e tons mais fortes indicam mais camadas sobrepostas. A escala usa toda a faixa de contraste para as camadas publicadas selecionadas. Com três ou quatro operadoras, os tons contam operadoras com ao menos uma rede presente. A visão de uma operadora usa a mesma escala de sobreposição; a visão de coincidência mostra a interseção das camadas publicadas selecionadas. Listras na contagem de operadoras e o tom máximo na contagem de redes indicam a coincidência dessas camadas. Brisanet 3G não foi publicado: ausência de informação aparece como N/D, sem ser tratada como ausência de cobertura.

A matriz exibida ao tocar no mapa esclarece cada combinação de operadora e tecnologia. A transparência é fixa; a cor não representa intensidade de sinal. O [estudo de cores](ESTUDO_CORES.md) explica as decisões e referências.

A cobertura é desenhada em blocos de 384 px, com processamento em worker e cache de máscaras. Arrastar reaproveita os blocos existentes, enquanto os novos são desenhados progressivamente.

## Rotas e recomendação

Escolha origem, destino e, opcionalmente, um município intermediário. As sedes dos 184 municípios vêm de Localidades do Brasil 2022, do IBGE. A rota local é aproximada pelas vias principais do OpenStreetMap; respeita sentidos de circulação cadastrados, mas não é uma ferramenta de navegação nem cobre todas as restrições de conversão e acessos urbanos. Há uma opção de traçado online via OSRM; a indisponibilidade desse serviço retorna à malha local.

A análise corta o traçado nos polígonos originais e mede seu comprimento, sem amostragem regular de pontos. Usa exclusivamente os limiares de sinal mais alto: −82 dBm em 3G e −90 dBm em 4G/5G. Trechos fora do Ceará não entram no denominador. A união de redes evita contar o mesmo trecho duas vezes.

O ranking usa 60% de peso para 4G, 30% para 5G e 10% para 3G. Dados não publicados são excluídos e os pesos restantes normalizados, com informação parcial identificada. Esse índice expressa uma preferência de cobertura, não velocidade medida nem garantia de serviço. Percentuais são arredondados a 1%.

Nos resultados, escolha **Dois chips** para comparar as seis duplas de operadoras. O cálculo une os trechos cobertos por qualquer uma delas, contando sobreposições uma única vez. Cada dupla mostra cobertura total, união de 4G/5G, percentuais por tecnologia, maior trecho sem cobertura combinada e ganho em pontos percentuais e quilômetros sobre a melhor cobertura total individual entre as duas operadoras. O ranking das duplas mantém os pesos 4G 60%, 5G 30% e 3G 10%. Informações ausentes, como Brisanet 3G, são identificadas; se a outra operadora tem dados dessa rede, entram apenas esses trechos conhecidos. O botão para ver a dupla destaca a união na rota e seleciona ambas no mapa. Dois chips oferecem alternativas de cobertura; os dados não pressupõem troca automática nem soma de velocidades.

## Fontes e critérios

- Cobertura prevista em ambiente aberto: [Anatel / Mosaico](https://sistemas.anatel.gov.br/se/public/cmap.php), consultada em 08/10/2026. Publicações: 3G em 21/08/2026, 4G em 03/10/2026 e 5G em 07/09/2026. Brisanet 3G não foi publicado nesse catálogo.
- Limites e municípios: [IBGE](https://servicodados.ibge.gov.br/api/docs/malhas?versao=3).
- Vias principais: © [OpenStreetMap contributors](https://www.openstreetmap.org/copyright), dados sob ODbL.
- Leaflet: BSD 2-Clause; aviso de licença incluído no HTML.
- Roboto Flex: SIL Open Font License; fonte e licença incluídas no HTML.
- Interface inspirada em [Material 3 Expressive](https://m3.material.io/).

As manchas são previsões, não medições no local. Não representam velocidade nem garantem cobertura dentro de imóveis. A consulta usa os mesmos limiares de sinal mais alto do mapa e das rotas. Não há acréscimo automático de roaming.

## Atualizar

Substitua `index.html` pela versão nova e envie um commit para `main`. O GitHub Pages publica a atualização.
