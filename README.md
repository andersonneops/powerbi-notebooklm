# Miniguia de Estudos - Power BI com NotebookLM

## Contexto e Objetivos

Este projeto foi desenvolvido como parte do desafio da DIO utilizando o NotebookLM como ferramenta de apoio aos estudos.

O objetivo é consolidar conhecimentos sobre Power BI, explorando recursos de Inteligência Artificial para organizar informações, gerar resumos, esclarecer dúvidas e criar materiais de revisão.

### Objetivos de estudo

- Compreender os fundamentos do Power BI.
- Aprender a modelar dados.
- Criar dashboards interativos.
- Desenvolver boas práticas para análise de dados.

---

# Curadoria de Fontes

As seguintes fontes foram utilizadas no NotebookLM:

1. https://learn.microsoft.com/pt-br/power-bi/
   
2. https://www.youtube.com/watch?v=s_YprQlnXb4

3. https://learn.microsoft.com/dax/ 

# Engenharia de Prompts

## Prompt 1

> Explique o que é o Power BI como se eu fosse iniciante.

### Resposta da IA

> O **Power BI** é uma plataforma de análise de negócios da Microsoft que transforma dados brutos e desconexos em informações visuais, interativas e fáceis de entender. Em termos simples, ele ajuda você a conectar diferentes fontes de informação (como uma planilha de Excel ou um banco de dados), organizar esses dados e criar gráficos que "contam uma história" para ajudar na tomada de decisões.
>
> Para entender como ele funciona, imagine o Power BI dividido em três partes principais:
>
> ### 1. As Peças do Ecossistema
> O Power BI não é apenas um programa, mas um conjunto de ferramentas que trabalham juntas:
>
> - **Power BI Desktop:** aplicativo gratuito para Windows onde são criados os relatórios.
> - **Power BI Service:** plataforma online para publicar e compartilhar relatórios.
> - **Power BI Mobile:** aplicativo para visualizar dashboards em dispositivos móveis.
>
> ### 2. Fluxo de Trabalho
>
> 1. Conectar aos dados.
> 2. Limpar e transformar com o Power Query.
> 3. Modelar os dados e criar cálculos utilizando DAX.
> 4. Criar gráficos e dashboards.
> 5. Publicar e compartilhar os relatórios.
>
> ### 3. Por que usar o Power BI?
>
> O Power BI permite criar relatórios interativos, integrar diversas fontes de dados e utilizar recursos de Inteligência Artificial para gerar insights e narrativas automáticas, auxiliando na tomada de decisões.

### O que aprendi

Compreendi que o Power BI é composto por diferentes ferramentas e que seu fluxo de trabalho segue etapas bem definidas, desde a importação dos dados até a publicação dos dashboards. Sendo importante para tomada de decisão na empresa. Colocar para mostrar exemplos para melhorar a compreensão do assunto.

## Prompt 2

> Explique as principais funções DAX com exemplos.

### Resposta da IA

> A linguagem DAX (Data Analysis Expressions) é uma biblioteca de funções e operadores que permite criar fórmulas e expressões em modelos de dados do Power BI. Para um iniciante, o DAX pode ser visto como uma evolução das fórmulas do Excel, permitindo realizar cálculos avançados e dinâmicos em grandes conjuntos de dados.
>
> Abaixo estão as principais funções utilizadas no Power BI, divididas por categorias e acompanhadas de exemplos:
>
> **1. Funções de Agregação**
>
> Essas funções resumem valores de uma coluna ou tabela.
>
> **SUM:** Soma todos os números de uma coluna específica.
>
> Exemplo:
>
> `Total de Vendas = SUM(Vendas[Valor])`
>
> **SUMX:** É uma função iteradora que percorre a tabela linha a linha para realizar o cálculo antes de somar o resultado final.
>
> Exemplo:
>
> `Valor Total = SUMX(Vendas, Vendas[Quantidade] * Vendas[PrecoUnitario])`
>
> **AVERAGE:** Calcula a média aritmética dos valores de uma coluna.
>
> Exemplo:
>
> `Media Salarial = AVERAGE(RH[Salario])`
>
> **COUNTROWS:** É a função recomendada para contar o número de linhas de uma tabela, sendo mais eficiente que a função COUNT por operar diretamente nos metadados.
>
> Exemplo:
>
> `Total Funcionarios = COUNTROWS(Funcionarios)`
>
> **2. Funções de Filtro e Contexto**
>
> Essas são as funções mais poderosas do DAX, pois permitem mudar como o Power BI "olha" para os dados.
>
> **CALCULATE:** É considerada a função mais importante do DAX. Ela avalia uma expressão em um contexto de filtro modificado.
>
> Exemplo:
>
> `Vendas Europa = CALCULATE([Total de Vendas], Geografia[Continente] = "Europa")`
>
> **FILTER:** Percorre uma tabela e aplica um filtro específico linha a linha. No entanto, a documentação recomenda evitar o uso de FILTER em filtros simples dentro da CALCULATE para não prejudicar o desempenho.
>
> **SELECTEDVALUE:** Retorna o valor que está selecionado no momento em um filtro (segmentação de dados). É útil para criar títulos dinâmicos ou cálculos que dependem da escolha do usuário.
>
> **3. Funções Matemáticas e Lógicas**
>
> **DIVIDE:** Realiza uma divisão segura, tratando automaticamente casos de divisão por zero ao retornar um valor nulo (`BLANK`) em vez de erro.
>
> Exemplo:
>
> `Margem de Lucro = DIVIDE([Lucro], [Vendas])`
>
> **IF:** Realiza um teste lógico e retorna um valor se for verdadeiro e outro se for falso.
>
> **Boas Práticas e Otimização**
>
> A eficiência de um relatório depende da escrita correta dessas fórmulas. Algumas diretrizes técnicas incluem:
>
> - Uso de **VAR** para armazenar resultados intermediários e evitar recálculos.
> - Priorizar **COUNTROWS** em vez de **COUNT** por questões de desempenho.
> - Evitar converter valores **BLANK** em zero desnecessariamente.
>
> Se você deseja aprender na prática, o workshop **Dashboard in a Day** reserva um módulo focado no uso de hierarquias de dados e no desenvolvimento de fórmulas customizadas em DAX.

### O que aprendi

Linguagem DAX (Data Analysis Expressions) é essencial para realizar cálculos avançados no Power BI. Também compreendi que existem diferentes categorias de funções, como agregação, filtro e lógica, cada uma com uma finalidade específica na análise de dados. 
A resposta ficou melhor, texto menos genérico, quando coloquei para explicar em tópicos e colocar exemplos reais e do dia a dia.

---


## Resumos Estruturados

### O que é o Power BI?

O Power BI é uma plataforma de Business Intelligence (BI) desenvolvida pela Microsoft que transforma dados em informações visuais e interativas. Com ele, é possível conectar diferentes fontes de dados, tratá-los, criar modelos, desenvolver dashboards e gerar insights para apoiar a tomada de decisões.

### Componentes do Power BI

- **Power BI Desktop:** ferramenta para importar, transformar dados e criar relatórios.
- **Power BI Service:** plataforma online para publicar, compartilhar e colaborar em dashboards.
- **Power BI Mobile:** aplicativo para visualizar relatórios em dispositivos móveis.

### Fluxo de Trabalho

1. Conectar às fontes de dados.
2. Transformar e limpar os dados com o Power Query.
3. Modelar os dados criando relacionamentos entre tabelas.
4. Criar medidas e cálculos utilizando DAX.
5. Desenvolver dashboards e relatórios interativos.
6. Publicar e compartilhar os relatórios no Power BI Service.

### Principais Recursos

- Conexão com diversas fontes de dados.
- Transformação de dados utilizando o Power Query.
- Modelagem de dados.
- Linguagem DAX para criação de medidas.
- Dashboards interativos.
- Compartilhamento de relatórios.
- Recursos de Inteligência Artificial para geração de insights.

---## Resumos Estruturados

### O que é o Power BI?

O Power BI é uma plataforma de Business Intelligence (BI) desenvolvida pela Microsoft que transforma dados em informações visuais e interativas. Com ele, é possível conectar diferentes fontes de dados, tratá-los, criar modelos, desenvolver dashboards e gerar insights para apoiar a tomada de decisões.

### Componentes do Power BI

- **Power BI Desktop:** ferramenta para importar, transformar dados e criar relatórios.
- **Power BI Service:** plataforma online para publicar, compartilhar e colaborar em dashboards.
- **Power BI Mobile:** aplicativo para visualizar relatórios em dispositivos móveis.

### Fluxo de Trabalho

1. Conectar às fontes de dados.
2. Transformar e limpar os dados com o Power Query.
3. Modelar os dados criando relacionamentos entre tabelas.
4. Criar medidas e cálculos utilizando DAX.
5. Desenvolver dashboards e relatórios interativos.
6. Publicar e compartilhar os relatórios no Power BI Service.

### Principais Recursos

- Conexão com diversas fontes de dados.
- Transformação de dados utilizando o Power Query.
- Modelagem de dados.
- Linguagem DAX para criação de medidas.
- Dashboards interativos.
- Compartilhamento de relatórios.
- Recursos de Inteligência Artificial para geração de insights.

---

## Glossário

| Conceito | Descrição |
|-----------|-----------|
| **Business Intelligence (BI)** | Processo de análise de dados para apoiar a tomada de decisões. |
| **Power Query** | Ferramenta para importar, limpar e transformar dados. |
| **DAX** | Linguagem de fórmulas utilizada para criar medidas e cálculos no Power BI. |
| **Dashboard** | Painel com indicadores e gráficos interativos. |
| **Relatório** | Conjunto de páginas contendo análises e visualizações. |
| **Modelo de Dados** | Organização das tabelas e seus relacionamentos. |

---

## Prompts Reutilizáveis

### Para aprender conceitos

- Explique o que é o Power BI de forma simples.
- Quais são os componentes do Power BI?
- Explique o fluxo de trabalho do Power BI.

### Para Dashboards

- Quais são as boas práticas para criar dashboards?
- Quais gráficos utilizar para análise de vendas?
- Como deixar um dashboard mais intuitivo?

### Para Revisão

- Faça um resumo sobre Power BI.
- Monte um plano de estudos de Power BI para iniciantes.

## Conclusão

O NotebookLM demonstrou ser uma excelente ferramenta para organizar estudos e resumir conteúdos. Aprender a utilização de prompts bem elaborados melhora muito a qualidade das respostas obtidas. Irei continuar usando para continuar a tiver duvidas e resumir os assuntos.
