# Diário de Trade

Diário de day trade em página única: cadastre cada operação e acompanhe o desempenho por dia, semana e mês, com gráficos e métricas de risco. Os dados ficam salvos no navegador (`localStorage`), sem servidor nem cadastro.

## Como usar

Abra o arquivo `index.html` no navegador. Não há dependências, build ou instalação.

## Funcionalidades

### Cadastro de operações

- Registro de operação com data, ativo, tipo (compra ou venda) e resultado em reais.
- Campo de motivo com múltiplas marcações: sugestões prontas (falha de topo, falha de fundo, padrão de candle, pico de volume, pullback, rompimento de LTA/LTB, teste em 61.8), busca por digitação, criação de motivos personalizados e separação automática por vírgula.
- Dados persistidos automaticamente no navegador, com botão para limpar todo o histórico.
- Ao salvar, o filtro de mês passa para o mês da operação cadastrada, garantindo que ela apareça na tela.

### Indicadores gerais

- Quantidade de operações, lucro/prejuízo acumulado e mês de referência.
- Resumo mensal com o resultado consolidado de cada mês.

### Gráficos

- Resultado por semana em gráfico de linha com área preenchida e valor em cada ponto.
- Resultado por mês em gráfico de barras, com barras verdes ou vermelhas conforme o resultado.
- Proporção de operações com lucro e prejuízo em gráfico de rosca.

### Insights e métricas de risco

- Ativos mais operados e motivos mais frequentes (top 5 de cada).
- Taxa de acerto, com contagem de acertos e perdas.
- Fator de lucro, comparando lucro bruto e prejuízo bruto.
- Relação risco : ganho médio, com ganho e perda médios por operação.
- Drawdown atual e máximo, com classificação visual (saudável, alerta ou crítico) e mini gráfico da evolução.

### Listagem de operações

- Filtro por mês, iniciando no mês atual, com opção de ver todos os meses.
- Duas visualizações selecionáveis, com a preferência salva no navegador:
  - **Lista**: tabela com data, ativo, tipo, motivos, resultado e exclusão individual da operação.
  - **Grade**: calendário em que cada dia é um card, mostrando o resultado somado do dia, a quantidade de operações e o detalhe das operações ao passar o mouse. Dias positivos e negativos são destacados em verde e vermelho, o dia de hoje ganha borda em destaque e cada mês exibe o total de dias operados e o resultado do período.

### Interface

- Tema escuro, valores em formato monetário brasileiro (BRL) e datas em pt-BR.
- Layout responsivo, adaptado para telas menores.

## Escopo do filtro de mês

O filtro de mês afeta os indicadores gerais, o resumo mensal, os gráficos e a listagem de operações. Os cards de insights (ativos, motivos, taxa de acerto, fator de lucro, risco : ganho e drawdown) consideram sempre o histórico completo.

## Estrutura

Todo o projeto está em `index.html`, com HTML, CSS e JavaScript no mesmo arquivo. Os gráficos são desenhados com a API `canvas` nativa.

Chaves usadas no `localStorage`:

- `daytrade-operations`: operações cadastradas.
- `daytrade-operations-view`: visualização escolhida (lista ou grade).
