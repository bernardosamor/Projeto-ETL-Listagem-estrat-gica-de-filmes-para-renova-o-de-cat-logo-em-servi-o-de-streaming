# Projeto-ETL-Listagem-estrat-gica-de-filmes-para-renova-o-de-cat-logo-em-servi-o-de-streaming

⚠️ Work in Progress (WIP): Este repositório está sendo atualizado com a documentação completa dos projetos.


> **Resumo:** Projeto desenvolvido com intuito de listar filmes com maior valor argregado via a criação de métricas que equilibrassem o custo de aquisição de licença com qualidade (avaliação IDMB) do filme para renovação de catálogo de filmes em serviço de streaming.

---

### 💡 O Problema de Negócio
Foi realizada uma pesquisa de satisfação com os clientes de uma empresa de streaming e o catálogo de filmes foi o tópico mais recorrente do lado negativo. A partir de uma database de filmes do IMDB, a empresa tomou a decisão de buscar novos nomes para compor seu catálogo.

---

🎯 Objetivo do Negócio
O desafio principal foi criar uma estratégia de eficiência de capital. Em vez de focar apenas em grandes blockbusters caros, o modelo identifica "pérolas escondidas": títulos com excelentes avaliações, mas que possuem um custo de aquisição significativamente menor, maximizando o ROI do catálogo.

---

🛠️ Tecnologias Utilizadas
MySQL: Para o unir 2 tabelas com informações adicionais a base bruta..
Power BI: Tratamento final dos dados, com a criação de métricas de dimensão de desempenho para compor dashboards para visualização dos filmes listados como escolhas otimizadas.

---

🧠 Hipóteses que guiaram o projeto.
* **É provavel que precise se sacrificar ligeiramente a qualidade pelo menor custo, mais ainda se mantendo uma margem pequena de desvio de avaliação.**
  * ** Resultado: ✅ Confirmado:** A avaliação média dos filmes selecionados é 8,21 (a avaliação média da bse é 8,31), apontando um desvio de apenas 1,3%. 
* **Filmes caros não necessariamente são sinmônimo de qualidade**
  * ** Resultado: ✅ Confirmado:** Ao compararmos o custo de um blockbuster de avaliação 8,10 ($310.000) com o custo somado de todos os filmes que foram selecionados via métricas de desempenho ($210.000), vemos que as escolhas estratégicas apresentam uma economia de 32,2%.
* **Mesmo que a avaliação média dos filmes listados seja ligeirament inferior a da média da base, os filmes ainda possuem valor**
  * ** Resultado: ✅ Confirmado:** O custo de um blockbuster de avaliação inferior a média dos filmes elegidos pelas métricas é muito superior.  

---

### 🗺️ RoadMap do Projeto
Este é um projeto que exemplifica a cadeia de ETL, portanto ele é criado ao integrar a cadeia de produção com 2 ferramentas principais, SQL e Power BI:
* **Base Bruta:** CSV extraídos via site Kaggle.
* **Tratamento inicial no SQL:** Utilizado para unir 2 tabelas via INNER Joins, o CSV original tinha dados incompletos para os insights que eu optei por apresentar. 
* **Power BI:** Criação de tabelas auxiliares (tabela calendário e tabelas de métricas para estimar custo de licença)
  * **Tabelas de desenvolvimento de Métricas:** Considerando que custo de aquisição de licença não são informações públicas, estimei o custo da licença considerando: Duração do filme, Idade, Exclusividade (se o filme está disponível apenas no meu serviço) e Gênero do filme.
  * **Página Home:** Introdução do Projeto, optei por trazer informações do projeto buscando tendências, como: Médias de avaliação por década, proporção absoluta de filmes por gênero e proporção percentual da base por duração de filmes. 
  * **Página Filmes escolhidos:** Apresentação da lista de filmes escolhidos, comparações com filmes blockbusters para quantificar a economia e dimensionar o peso das escolhas estratégicas.


### 📈 Principais Insights
* **Blockbuster vs Escolhas estratégicas:** Ao desenvolver a métrica de Score Custo Benefício, foi possível selecionar filmes com qualidades superiores a grandes produções com fração do custo de licença.
Processamento de Dados: Limpeza de ruídos e normalização de notas e gêneros.

---
TERMINAR A PARTIR DAQUI 


Dashboard de Decisão: Uma visão executiva que permite ao gestor de conteúdo filtrar títulos por gênero, ano e pontuação de custo-benefício.

Insight de Arbitragem: Demonstração visual de como substituir títulos de baixo desempenho por opções de alta qualidade e menor custo.

🚀 Como visualizar
O dashboard em PDF/imagem está na pasta /visuals.

O script de tratamento de dados está em data_processing.py.

✍️ Análise Completa (Medium)
Para entender toda a lógica de negócio por trás desse projeto, incluindo a metodologia do Score, leia o artigo completo que escrevi:
👉 [Link para o seu artigo do Medium aqui]
