# Cassava Breeding – NextGen 2022 Analyses

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/wevertoncosta/)
[![ORCID](https://img.shields.io/badge/ORCID-0000--0003--0742--5936-green?style=flat&logo=orcid&logoColor=white)](https://orcid.org/0000-0003-0742-5936)
[![Lattes](https://img.shields.io/badge/Lattes-CNPq-blue)](http://lattes.cnpq.br/2723811288754046)
[![GitHub](https://img.shields.io/badge/GitHub-Profile-black?style=flat&logo=github)](https://github.com/WevertonGomesCosta)
[![Google Scholar](https://img.shields.io/badge/Google%20Scholar-Profile-4285F4?style=flat&logo=google-scholar&logoColor=white)](https://scholar.google.com.br/citations?hl=pt-BR&user=eJNKcHsAAAAJ)

Este repositório contém o código, dados e documentação das análises realizadas no **programa de melhoramento de mandioca da Embrapa**, no contexto do projeto **NextGen Cassava (Year 6 – 2022/2023)**.  
As análises incluem **avaliação de ensaios de campo, caracterização fenotípica, estimação de BLUPs, índices de seleção e integração de características de qualidade**.

---

## 📂 Estrutura do Projeto

- `data/` → arquivos de dados de entrada (fenótipos, metadados, fieldbooks)  
- `analysis/` → código em RMarkdown com as etapas do pipeline:
  - `Trials and traits 2023.Rmd` → número de ensaios e características por ano  
  - `Phenotype Data.Rmd` → limpeza e estruturação dos dados fenotípicos  
  - `Blups cycles.Rmd` → estimação de BLUPs, herdabilidade e índices de seleção  
- `output/` → tabelas e figuras geradas (gráficos de progresso genético, boxplots, índices de seleção)  
- `README.md` → documentação do projeto  

---

## 🚀 Pipeline Analítico

### 1. Ensaios e Características
- Importação de metadados do **CassavaBase**.  
- Cálculo do número de ensaios por ano (2018–2023).  
- Quantificação do número de características avaliadas (69 no total).  
- Visualizações: gráficos de barras com evolução temporal.

### 2. Estruturação dos Dados Fenotípicos
- Importação de dados de fenótipo e metadados.  
- Definição das populações **GS-C0, GS-C1 e GS-C2**.  
- Identificação de blocos, repetições, checks e testes.  
- Criação de variáveis de delineamento experimental (`yearInLoc`, `trialInLocYr`, `repInTrial`, `blockInTrial`).  
- Controle de qualidade dos dados (densidade de distribuição por ensaio).

### 3. Estimação de BLUPs e Herdabilidade
- Modelos mistos ajustados com o pacote **metan**.  
- Estimação de BLUPs por ensaio e em análise conjunta.  
- Cálculo da herdabilidade (H²) por característica.  
- Seleção de ensaios com H² ≥ 0.5 para análise de ganho genético.

### 4. Comparação entre Ciclos (C0, C1, C2)
- Regressão linear para avaliar ganho genético entre ciclos.  
- Boxplots comparando checks e testes.  
- Índice de seleção (SI) integrando múltiplas características (FRW, FSW, DRY, DMCg, StC, PA).  
- Ranking dos 30 melhores clones por ciclo.

### 5. Integração com Qualidade e Tolerância à Seca
- Análises de **tolerância à seca** com modelos mistos multiambiente.  
- Avaliação de **características de qualidade**: deterioração pós-colheita, cozimento, amilose, teor de amido e matéria seca.  
- Uso de **NIRS** para predição de atributos de qualidade.  
- Planos de integração com **GWAS** para identificação de genes candidatos.

### 6. Resultados Apresentados no NextGen 2023
- Mais de **240 ensaios** inseridos no CassavaBase desde 2018.  
- **3403 clones avaliados** em 2022/2023 (C0, C1, C2).  
- Ganhos genéticos consistentes em características de rendimento.  
- Estratégias de seleção combinando **BLUPs + seleção genômica** para tolerância à seca.  

---

## 📊 Tecnologias Utilizadas

- **R** (pacotes: `tidyverse`, `metan`, `ggplot2`, `ggpubr`, `data.table`, `genomicMateSelectR`)  
- **RMarkdown** para documentação reprodutível  
- **Git/GitHub** para versionamento  

---

## 🔧 Como Reproduzir

1. Clone este repositório:
   ```bash
   git clone https://github.com/WevertonGomesCosta/analisys-next-gen-2022.git
   ```
2. Abra o projeto no **RStudio**.  
3. Execute os arquivos `.Rmd` em `analysis/` para reproduzir as análises.  

---

## 📌 Autores

- **Weverton Gomes Costa** – Pós-Doutorando, Embrapa Mandioca e Fruticultura  
- **Eder Jorge de Oliveira** – Coordenador do Projeto, Embrapa Mandioca e Fruticultura  

[Site pessoal de Weverton](https://wevertongomescosta.github.io/)  

---

## 📜 Licença

Este projeto é distribuído sob a licença **Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License**. Consulte o arquivo `LICENSE` para mais detalhes.

---

# Cassava Breeding – NextGen 2022 Analyses (English Version)

This repository contains the code, data, and documentation of the analyses carried out in the **cassava breeding program at Embrapa**, within the scope of the **NextGen Cassava project (Year 6 – 2022/2023)**.  
The analyses include **field trial evaluation, phenotypic characterization, BLUP estimation, selection indices, and integration of quality traits**.

---

## 📂 Project Structure

- `data/` → input data files (phenotypes, metadata, fieldbooks)  
- `analysis/` → RMarkdown scripts with the analysis pipeline:
  - `Trials and traits 2023.Rmd` → number of trials and traits per year  
  - `Phenotype Data.Rmd` → cleaning and structuring phenotypic data  
  - `Blups cycles.Rmd` → BLUP estimation, heritability, and selection indices  
- `output/` → generated tables and figures (genetic progress plots, boxplots, selection indices)  
- `README.md` → project documentation  

---

## 🚀 Analytical Pipeline

1. **Trials and Traits** – quantification of trials and traits evaluated per year.  
2. **Phenotypic Data** – cleaning, structuring, and defining GS populations (C0, C1, C2).  
3. **BLUPs and Heritability** – mixed models fitted with the **metan** package.  
4. **Cycle Comparisons** – regression and boxplots comparing genetic gain across cycles.  
5. **Integration with Quality and Drought Tolerance** – multi-environment models, NIRS predictions, and GWAS perspectives.  
6. **NextGen 2023 Results** – over 240 trials, 3403 clones evaluated, consistent genetic gains, and genomic selection strategies.  

---

## 📊 Technologies Used

- **R** (packages: `tidyverse`, `metan`, `ggplot2`, `ggpubr`, `data.table`, `genomicMateSelectR`)  
- **RMarkdown** for reproducible documentation  
- **Git/GitHub** for version control  

---

## 🔧 How to Reproduce

1. Clone this repository:
   ```bash
   git clone https://github.com/WevertonGomesCosta/analisys-next-gen-2022.git
   ```
2. Open the project in **RStudio**.  
3. Run the `.Rmd` scripts in `analysis/` to reproduce the analyses.  

---

## 📌 Authors

- **Weverton Gomes Costa** – Postdoctoral Researcher, Embrapa Cassava & Fruits  
- **Eder Jorge de Oliveira** – Project Coordinator, Embrapa Cassava & Fruits  

[Weverton’s personal website](https://wevertongomescosta.github.io