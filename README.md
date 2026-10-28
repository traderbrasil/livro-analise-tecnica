# Análise Técnica dos Mercados Financeiros, 4ª edição

Notebooks em Python do livro *Análise Técnica dos Mercados Financeiros*, 4ª edição, de Flávio Lemos, CMT, CFP® (Trader Brasil Editora, 2027).

Cada capítulo do livro tem um laboratório. Os QR do livro levam ao hub, em [traderbrasil.com/livro-analise-tecnica](https://traderbrasil.com/livro-analise-tecnica/), e de lá a estes notebooks.

## Como rodar

**No Google Colab (recomendado).** Clique em "Open in Colab" na tabela abaixo. O notebook roda direto na internet, sem instalar nada. Na primeira vez, o Colab pede para você entrar com uma conta do Google. Depois, rode as células de cima para baixo (Ambiente de execução > Executar tudo).

**No seu computador.** Com Python 3.10 ou mais novo:

```bash
git clone https://github.com/traderbrasil/livro-analise-tecnica.git
cd livro-analise-tecnica
pip install -r requirements.txt
jupyter lab notebooks/
```

## Versão do livro

A versão **v4.0** é a que foi congelada na impressão do livro. Os links dos QR apontam para ela. Correções e melhorias entram depois, em versões novas, e ficam registradas na página de [errata](https://traderbrasil.com/livro-analise-tecnica/errata/) do hub.

## Os dados

- **Cotações do Yahoo Finance e de outras fontes públicas:** este repositório não armazena nem redistribui séries históricas de terceiros. Na primeira execução, cada notebook baixa os dados na sua máquina (Yahoo Finance e, em alguns capítulos, Banco Central, FRED, CFTC, Cboe e Blockchain.com) e grava uma cópia local (`dados_capNN.pkl`), que as execuções seguintes reaproveitam. A cópia local fica fora do controle de versão (`.gitignore`).
- Os provedores corrigem o histórico (proventos, desdobramentos), e o Yahoo só guarda alguns meses de barras intradiárias. Por isso seus números podem diferir um pouco dos do livro, que usa dados até 30/09/2026. Quando a janela do livro não está mais disponível, o notebook avisa e usa a mais recente.
- Se o download falhar (provedor fora do ar ou limitando pedidos), o notebook diz qual ativo não veio. Espere alguns minutos e rode a célula de novo.
- `dados_negocios/negocios_INDZ26_20261020.csv`: os 11.457 negócios do contrato cheio de Ibovespa futuro (INDZ26) em 20/10/2026, das 9h00 às 15h18, com hora, preço, quantidade e lado do agressor. É usado na Parte 8 do notebook do Capítulo 22 (footprint e delta). No Colab, o notebook baixa o arquivo daqui sozinho.
- `dados_futuros/`: barras de 5 minutos de WIN e WDO (série contínua), usadas por `futuros_b3.ipynb` (Capítulos 22 a 25). No Colab, o notebook baixa os arquivos daqui sozinho.
  - `win_5min_2026-09-24_a_2026-10-13.csv` e `wdo_5min_2026-09-24_a_2026-10-06.csv`: os exemplos dos gráficos do livro;
  - `win_5min_2026-01-02_a_2026-10-14.csv` e `wdo_5min_2026-01-02_a_2026-10-14.csv`: os testes das Partes 6 e 7;
  - `win_5min_2024-09-02_a_2026-09-02.csv` e `wdo_5min_2024-09-02_a_2026-09-02.csv`: dois anos, para repetir os testes numa amostra maior. Na série contínua, os preços anteriores a cada rolagem vêm multiplicados por um fator de ajuste.
  - Formato: ativo; data; hora; abertura; máxima; mínima; fechamento; volume financeiro; contratos (separador ";", vírgula decimal, sem cabeçalho).

## Notebooks

| Capítulo | Notebook | O que faz | Colab |
|---|---|---|---|
| Cap. 1 | [`cap01_introducao.ipynb`](notebooks/cap01_introducao.ipynb) | O seu primeiro notebook | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap01_introducao.ipynb) |
| Cap. 2 | [`cap02_dow.ipynb`](notebooks/cap02_dow.ipynb) | Dow com Python | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap02_dow.ipynb) |
| Cap. 3 | [`cap03_graficos.ipynb`](notebooks/cap03_graficos.ipynb) | O mesmo preço de vários jeitos | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap03_graficos.ipynb) |
| Cap. 4 | [`cap04_tendencia.ipynb`](notebooks/cap04_tendencia.ipynb) | Tendência, suportes e gaps | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap04_tendencia.ipynb) |
| Cap. 5 | [`cap05_padroes.ipynb`](notebooks/cap05_padroes.ipynb) | O scanner de padrões gráficos | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap05_padroes.ipynb) |
| Cap. 6 | [`cap06_fibonacci.ipynb`](notebooks/cap06_fibonacci.ipynb) | Fibonacci no preço e no tempo | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap06_fibonacci.ipynb) |
| Cap. 7 | [`cap07_elliott.ipynb`](notebooks/cap07_elliott.ipynb) | As ondas de Elliott em Python | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap07_elliott.ipynb) |
| Cap. 8 | [`cap08_indicadores.ipynb`](notebooks/cap08_indicadores.ipynb) | Indicadores escritos à mão | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap08_indicadores.ipynb) |
| Cap. 9 | [`cap09_seguidores.ipynb`](notebooks/cap09_seguidores.ipynb) | Seguidores de tendência | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap09_seguidores.ipynb) |
| Cap. 9 | [`cap09b_kama_tartarugas.ipynb`](notebooks/cap09b_kama_tartarugas.ipynb) | Kaufman e as tartarugas | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap09b_kama_tartarugas.ipynb) |
| Cap. 9 | [`cap09c_dcatr.ipynb`](notebooks/cap09c_dcatr.ipynb) | O DC ATR de David Cox | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap09c_dcatr.ipynb) |
| Cap. 10 | [`cap10_momentum.ipynb`](notebooks/cap10_momentum.ipynb) | Osciladores de momentum | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap10_momentum.ipynb) |
| Cap. 11 | [`cap11_volume.ipynb`](notebooks/cap11_volume.ipynb) | Volume, o combustível do mercado | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap11_volume.ipynb) |
| Cap. 12 | [`cap12_folego.ipynb`](notebooks/cap12_folego.ipynb) | Fôlego de mercado (Market Breadth) na B3 | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap12_folego.ipynb) |
| Cap. 13 | [`cap13_sentimento.ipynb`](notebooks/cap13_sentimento.ipynb) | Sentimento, o termômetro do medo e da ganância | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap13_sentimento.ipynb) |
| Cap. 14 | [`cap14_ciclos.ipynb`](notebooks/cap14_ciclos.ipynb) | Ciclos e sazonalidade | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap14_ciclos.ipynb) |
| Cap. 15 | [`cap15_gann.ipynb`](notebooks/cap15_gann.ipynb) | Gann sem astrologia | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap15_gann.ipynb) |
| Cap. 16 | [`cap16_forca_relativa.ipynb`](notebooks/cap16_forca_relativa.ipynb) | Força relativa | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap16_forca_relativa.ipynb) |
| Cap. 17 | [`cap17_argon.ipynb`](notebooks/cap17_argon.ipynb) | A grade de nove (versão didática) | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap17_argon.ipynb) |
| Cap. 18 | [`cap18_intermercados.ipynb`](notebooks/cap18_intermercados.ipynb) | Intermercados e liquidez | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap18_intermercados.ipynb) |
| Cap. 19 | [`cap19_cripto.ipynb`](notebooks/cap19_cripto.ipynb) | Criptoativos | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap19_cripto.ipynb) |
| Cap. 20 | [`cap20_wyckoff.ipynb`](notebooks/cap20_wyckoff.ipynb) | Wyckoff | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap20_wyckoff.ipynb) |
| Cap. 21 | [`cap21_smc.ipynb`](notebooks/cap21_smc.ipynb) | SMC e manipulação | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap21_smc.ipynb) |
| Cap. 22 | [`cap22_profile.ipynb`](notebooks/cap22_profile.ipynb) | Market Profile e Volume Profile | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap22_profile.ipynb) |
| Cap. 23 | [`cap23_price_action.ipynb`](notebooks/cap23_price_action.ipynb) | Price action, Al Brooks e Linda Raschke | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap23_price_action.ipynb) |
| Cap. 24 | [`cap24_strat.ipynb`](notebooks/cap24_strat.ipynb) | The Strat | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap24_strat.ipynb) |
| Cap. 25 | [`cap25_estrategias.ipynb`](notebooks/cap25_estrategias.ipynb) | Estratégias clássicas | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap25_estrategias.ipynb) |
| Caps. 22 a 25 | [`futuros_b3.ipynb`](notebooks/futuros_b3.ipynb) | WIN e WDO no 5 minutos | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/futuros_b3.ipynb) |
| Cap. 26 | [`cap26_python.ipynb`](notebooks/cap26_python.ipynb) | Python para o analista técnico | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap26_python.ipynb) |
| Cap. 27 | [`cap27_backtest.ipynb`](notebooks/cap27_backtest.ipynb) | O backtest em 10 passos | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap27_backtest.ipynb) |
| Cap. 27 | [`cap27_sistemas.ipynb`](notebooks/cap27_sistemas.ipynb) | Sistemas, backtesting e aprendizado de máquina | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap27_sistemas.ipynb) |
| Cap. 28 | [`cap28_stops.ipynb`](notebooks/cap28_stops.ipynb) | Stops, o seguro que mantém você no jogo | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap28_stops.ipynb) |
| Cap. 29 | [`cap29_risco.ipynb`](notebooks/cap29_risco.ipynb) | Gestão quantitativa do risco, o tamanho da mão | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap29_risco.ipynb) |
| Cap. 30 | [`cap30_psicologia.ipynb`](notebooks/cap30_psicologia.ipynb) | Psicologia do trader em números | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap30_psicologia.ipynb) |
| Cap. 31 | [`cap31_roteiro.ipynb`](notebooks/cap31_roteiro.ipynb) | Juntando tudo, o Método 6C testado | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap31_roteiro.ipynb) |
| Cap. 32 | [`cap32_conclusao.ipynb`](notebooks/cap32_conclusao.ipynb) | As regrinhas da 3ª edição postas à prova | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/cap32_conclusao.ipynb) |
| Anexo I | [`anexo1_candlesticks.ipynb`](notebooks/anexo1_candlesticks.ipynb) | Os padrões de candlesticks postos à prova | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/anexo1_candlesticks.ipynb) |
| Anexo II | [`anexo2_perpetuo.ipynb`](notebooks/anexo2_perpetuo.ipynb) | Emendando os vencimentos do contrato futuro | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/anexo2_perpetuo.ipynb) |
| Anexo III | [`anexo3_opcoes.ipynb`](notebooks/anexo3_opcoes.ipynb) | O rabo, o cachorro e a volatilidade | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/anexo3_opcoes.ipynb) |
| Anexo IV | [`anexo4_mapa.ipynb`](notebooks/anexo4_mapa.ipynb) | O mapa de estudo para o CNPI-T e o CMT | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/anexo4_mapa.ipynb) |
| Anexo V | [`anexo5_hub.ipynb`](notebooks/anexo5_hub.ipynb) | O índice do hub: notebooks, apps e episódios por capítulo | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/anexo5_hub.ipynb) |
| Apêndice | [`apendice_murphy.ipynb`](notebooks/apendice_murphy.ipynb) | Os gráficos de longo prazo ajustados pela inflação | [![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/traderbrasil/livro-analise-tecnica/blob/v4.0/notebooks/apendice_murphy.ipynb) |

## Aviso legal

O conteúdo deste repositório é educacional e informativo. Não constitui recomendação de compra ou venda de ativos financeiros, nem oferta de serviço de análise ou de gestão. Os testes mostram o passado: resultados passados não garantem resultados futuros, e toda regra testada em dados históricos corre o risco de sobreajuste (*overfitting*). Investir envolve risco, inclusive o de perder todo o capital.

## Direitos

© 2026 Flávio Lemos e Trader Brasil Editora. O código pode ser usado e modificado para estudo pessoal. A reprodução do conteúdo do livro depende de autorização da editora.

## Links

- Hub do livro: [traderbrasil.com/livro-analise-tecnica](https://traderbrasil.com/livro-analise-tecnica/)
- Podcast *Traders of the World*: [youtube.com/@traderbrasil](https://www.youtube.com/@traderbrasil)
- Trader Brasil Escola de Finanças: [traderbrasil.com](https://www.traderbrasil.com/)
