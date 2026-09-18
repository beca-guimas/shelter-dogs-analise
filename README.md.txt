# 🐶 Análise Social e de Negócios: Abrigo de Cães (Shelter Dogs) - Excel

Este projeto foi desenvolvido a partir e graças à **EDUMI**, como parte do programa **EDUMI FOR YOUTH 2025**. 

O repositório contém uma análise exploratória completa realizada no Excel utilizando uma base de dados pública sobre cães em abrigos (Shelter Dogs). O projeto envolveu desde o tratamento de dados brutos e tratamento de dados ausentes até a criação de novas variáveis temporais para responder a perguntas críticas de negócio.

---

## 🧭 Desafios de Negócio e Insights Extraídos

### 📊 1. Qual é o perfil de cachorros mais abandonados?

A análise de perfil cruzou dados de gênero, castração e porte dos animais:

* **Gênero:** Os cães machos representam a maior parte dos registros de abandono na base de dados.
  * **57%** Machos
  * **43%** Fêmeas
* **Castração:** Identificou-se uma alta quantidade de dados ausentes para esta variável, impossibilitando uma conclusão definitiva. Entre os registrados:
  * **39,19%** Sim (Castrados)
  * **23,87%** Não

* **Porte (Tamanho):** Há uma dominância absoluta de cães de tamanho médio nos abrigos:

  * **66,19%** Médio
  * **17,67%** Grande
  * **16,14%** Pequeno

### 📈 2. Qual a distribuição de idade dos cachorros abandonados?

* **Análise de Faixa Etária:** Houve um destaque para a predominância de cães mais velhos, onde a **maior faixa identificada foi de 9 a 12 anos**. *(Nota: A base de dados possuía 544 dados ausentes para idade).*

* **Decisão Técnico de Comunicação:** A variável quantitativa contínua de idade (`age`) foi transformada manualmente em categorias (faixas etárias). Isso permitiu criar uma tabela de frequência sólida antes da plotagem do gráfico de barras. 

> *Insight de Negócio:* Nem sempre o método teoricamente "correto" (como um histograma contínuo) é o que melhor comunica os dados para os tomadores de decisão.

### ⏱️ 3. Qual o padrão de distribuição do tempo que estão esperando para ser adotados?

Para responder a essa questão, mapeou-se as colunas de datas (`data_found`, `adoptable_from`, `posted`) e aplicou-se a seguinte inteligência:

* **Criação de Variável (`waiting time`):** Foi calculada a diferença de dias entre a data de referência do exercício (10/12/2019) e a coluna `adoptable_from`. 
* **Tratamento de Anomalias:** Valores negativos foram identificados inicialmente (cães que ainda não estavam disponíveis para adoção na data limite) e foram totalmente desconsiderados da análise para evitar distorções.

* **Agrupamento por Faixas:** Os valores brutos de dias foram agrupados em blocos de tempo dentro do Sheets/Excel, pois o histograma automático do software falhava em passar uma mensagem clara.

* **Resultado:** O gráfico de barras revelou uma **forte concentração de cães aguardando adoção há mais de 1000 dias**, apontando para um cenário de permanência prolongada nos abrigos e baixíssima rotatividade de adoções.

---

## 🛠️ Recursos Aplicados no Excel / Sheets
* **Engenharia de Recursos:** Criação da variável calculada `waiting time` através de manipulação de datas.
* **Data Wrangling:** Identificação e tratamento de registros nulos/ausentes e filtragem de anomalias (valores negativos).
* **Análise Estatística:** Tabelas de frequência customizadas e categorização de dados contínuos.
* **Visualização de Dados:** Gráficos de barras otimizados para comunicação executiva e Dashboards.
