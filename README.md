# 🛰️ Ciência de Dados Aplicada ao Monitoramento de Recursos Hídricos

**Estudo de Caso: Represa de Furnas - MG**

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange)
![Google Earth Engine](https://img.shields.io/badge/GEE-Earth_Engine-success)
![DOI](https://img.shields.io/badge/DOI-10.5281%2Fzenodo.20518318-blue)

Este repositório contém o código-fonte e o pipeline de dados desenvolvidos para o Trabalho de Diplomação (TCC) em Ciência da Computação pela **PUC Minas - Campus Poços de Caldas**.

O projeto propõe um modelo inédito de monitoramento proativo da segurança hídrica e energética brasileira, cruzando dados orbitais de satélite (Missão Sentinel-2 / Agência Espacial Europeia) com métricas operacionais do Operador Nacional do Sistema Elétrico (ONS).

## 🎯 Principais Descobertas

- **Geomorfologia e Volume Morto:** Validação do espelho d'água via índice NDWI com 84,11% de correlação com o ONS, comprovando matematicamente o fenômeno do "Volume Morto" em vales de fundo plano.
- **Inércia Hidrológica (_Time Lag_):** Mapeamento do efeito "Solo Esponja", atestando um atraso sistêmico de 4 meses entre o pico pluviométrico (ENA) e a recuperação volumétrica da represa.
- **O "Limiar do Pânico" Econômico:** Identificação de uma correlação inversamente proporcional ($r = -0.75$) entre o Volume Útil e o acionamento de termelétricas, revelando que a cota de 30% funciona como um gatilho não-oficial para um aumento de ~800% no despacho de energia fóssil emergencial.
- **Degradação Limnológica:** Rastreamento de episódios severos de eutrofização (NDCI) e assoreamento (NDTI) durante os picos de esvaziamento.

## 📂 Estrutura do Repositório

O projeto segue boas práticas de engenharia de dados, separando claramente o código (notebooks) dos dados brutos e processados.

```text
📦 furnas-analysis
 ┣ 📂 data/                   # (Ignorado pelo Git, baixe via Zenodo)
 ┃ ┣ 📂 processed/            # Dados consolidados após ETL
 ┃ ┃ ┣ 📂 ons/                # Séries limpas do setor elétrico (Bronze)
 ┃ ┃ ┣ 📂 output/             # Matrizes de cruzamento estatístico e resultados
 ┃ ┃ ┗ 📂 satellite/          # Histórico de índices orbitais do GEE
 ┃ ┗ 📂 raw/                  # Dados diários brutos (ONS)
 ┃   ┣ 📂 daily/
 ┃   ┣ 📂 ena/
 ┃   ┗ 📂 termicas/
 ┣ 📂 notebooks/              # Pipelines de Análise e ETL
 ┃ ┣ 📜 ons_raw_to_bronze.ipynb  # Limpeza e consolidação de dados terrestres
 ┃ ┗ 📜 furnas_analysis.ipynb    # Aquisição GEE, modelagem e plotagem de gráficos
 ┣ 📜 .gitignore              # Proteção de artefatos temporários e dados massivos
 ┣ 📜 requirements.txt        # Dependências do projeto
 ┗ 📜 README.md               # Documentação do repositório
```
