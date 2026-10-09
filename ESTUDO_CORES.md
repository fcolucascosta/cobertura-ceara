# Cores, sobreposições e leitura do mapa

## Problema

Misturar quatro cores de operadoras com três tecnologias produz muitas combinações visuais. Uma cor resultante não permite saber quais das doze camadas estão presentes. Opacidade acumulada também mistura quantidade de fontes com intensidade de sinal, conceitos diferentes.

## Representação adotada

| Visão | O que a cor representa | Como confirmar o detalhe |
| --- | --- | --- |
| Comparação automática, com três ou quatro operadoras | Quantidade de operadoras com ao menos uma rede selecionada no limiar mais alto | Matriz de operadoras × redes ao tocar no mapa |
| Comparação automática, com uma ou duas operadoras | Quantidade de camadas publicadas presentes; tons ajustados à seleção | Matriz identifica as combinações exatas |
| Uma operadora | Uma rede presente em tom claro, duas ou três sobrepostas em tons mais fortes | Tom máximo indica todas as redes publicadas selecionadas |
| Coincidência | Interseção de todas as camadas publicadas selecionadas | Fontes ausentes são explicitamente identificadas |

Quantidade de operadoras usa uma escala sequencial azul baseada no esquema Blues do ColorBrewer: `#c6dbef`, `#6baed6`, `#3182bd`, `#08519c`. No tema escuro a progressão fica mais luminosa: `#294d6b`, `#407e9f`, `#68abc5`, `#a9dfef`. Números e texto acompanham a legenda; a interpretação não depende apenas de distinguir tons.

Com uma ou duas operadoras, a escala usa a quantidade de redes presentes em vez de cores categóricas por tecnologia. A tonalidade varia entre os extremos claro e forte conforme o número de camadas publicadas selecionadas: duas camadas usam dois tons, três usam três, e duas operadoras com três redes publicadas cada usam seis tons. Uma camada usa um tom intermediário uniforme. Camadas não publicadas não ampliam a escala. Assim, a seleção inteira tem contraste suficiente, preservando a união: cobertura exclusiva de qualquer rede permanece visível.

Com três ou quatro operadoras, a visão automática volta à contagem de operadoras para evitar excesso de gradações. A legenda muda junto com o significado da cor. No tema escuro, a progressão fica mais luminosa, mantendo a mesma ordem de cobertura. As variações não medem intensidade de sinal nem favorecem 5G sobre 4G. A recomendação de rotas continua usando os pesos definidos anteriormente: 4G 60%, 5G 30% e 3G 10%.

As listras, na visão de contagem de operadoras, e o tom máximo, na visão de sobreposição de redes, nunca significam presença de uma camada não publicada. Brisanet 3G não está no catálogo. Ao selecionar as doze combinações, só onze são conhecidas; a legenda e a matriz deixam essa limitação explícita.

## Legibilidade e desempenho

- A base passou a usar cinzas neutros. Vias e nomes ficam acima da cobertura para manter contexto geográfico.
- O controle de transparência foi removido: a intensidade visual é uniforme e não altera os dados, contagens ou percentuais.
- Roboto Flex foi embutida, incluindo suporte a acentos e sua licença OFL. Não há requisições ao Google durante o uso.
- Textos de controles, resultados e instruções foram aumentados; nomes no mapa usam 13–14 px, com prioridade e prevenção de colisões.
- Bairros, vilas e povoados de IBGE e OpenStreetMap aparecem em escalas progressivas, com limite de rótulos simultâneos.
- A cobertura usa blocos de 384 px ancorados no mapa. Arrastar reaproveita blocos existentes, e somente os novos blocos precisam ser desenhados. Máscaras geométricas e combinações têm cache no worker.
- O tema segue inicialmente o sistema; o seletor claro/escuro permite substituí-lo e memoriza a escolha.

## Referências

- [ColorBrewer — esquemas sequenciais e qualitativos](https://colorbrewer2.org/learnmore/schemes.html).
- [Ordnance Survey — hierarquia visual, bases neutras e camadas temáticas](https://www.ordnancesurvey.co.uk/blog/effective-basemaps).
- [Google Fonts — Roboto Flex](https://fonts.google.com/specimen/Roboto+Flex).
- [IBGE — Localidades do Brasil](https://www.ibge.gov.br/geociencias/organizacao-do-territorio/estrutura-territorial/27385-localidades.html).
