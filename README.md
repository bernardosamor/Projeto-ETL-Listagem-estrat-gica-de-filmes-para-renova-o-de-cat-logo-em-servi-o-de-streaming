# Projeto-ETL-Otimização-Catalogo-Streaming


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

---

### 📊Dashboard Criados

* **Página Capa**

<img width="1314" height="738" alt="hOME" src="https://github.com/user-attachments/assets/add27a23-32d4-4cb7-b63f-acd537163ba7" />

---  

* **Página Home**: Página dedicada a caracterização da base por meio dos critérios:
  * **Décadas:** Entender se existe algum período que se destoa dos demais.
  * **Gêneros:** Pesquisar se existe viés de gênero dentre os 250 filmes da base.
  * **Duração:** Entender a base quanto ao perfil dos usuários em relação a preferência por filmes curtos ou maiores.

<img width="1304" height="719" alt="P1" src="https://github.com/user-attachments/assets/45771175-584c-4a4a-a0f8-0db46a1a8845" />

--- 

* **Filmes Escolhidos**
  * **Escolhas otimizadas vs BlockBusters** 
  * **Listagem dos filmes selecionados** 
  * **Análise de ROI Qualitativo por Gênero** 

<img width="1304" height="728" alt="P2" src="https://github.com/user-attachments/assets/74fd9004-44fb-4aba-9023-153b3f1c5fc2" />

---

### 📈 Principais Insights
* **Blockbuster vs Escolhas estratégicas:** Ao desenvolver a métrica de Score Custo Benefício, foi possível selecionar filmes com qualidades superiores a grandes produções com fração do custo de licença.
* **Análise de ROI Qualitativo:** O estudo evidenciou uma descorrelação entre custo e satisfação. Gêneros como Crime e Biography atingem picos de avaliação (média 8.40) custando até 85% menos que gêneros saturados como Drama, provando que maior investimento nem sempre reflete maior qualidade percebida pelo usuário.
* **Eficiência de Escala:** A estratégia de otimização demonstrou que, com o orçamento necessário para licenciar um único título de alto custo (Blockbuster), é possível adquirir o Top 10 completo de filmes com maior Score Custo-Benefício. Isso garante uma nota média de 8,27 para o catálogo, maximizando a retenção de usuários com um investimento 97% menor.

---

### 📝 Documentação e Metodologia
Para entender todo o raciocínio analítico, a metodologia aplicada e as conclusões sugeridas, acesse o artigo completo no Medium:
👉 [Leia o Projeto ETL na íntegra](https://medium.com/@bernardosamor18/projeto-etl-auxiliar-tomada-de-decis%C3%A3o-em-renova%C3%A7%C3%A3o-de-cat%C3%A1logo-de-filmes-em-servi%C3%A7o-de-streaming-ae0cb1ff122b?postPublishedType=repub))

---
*Analista: Bernardo Samôr*
