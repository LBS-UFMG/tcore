# Predição de Temperatura Central (tcore) com Machine Learning

Este repositório contém dados e modelos para o estudo de desenvolvimento de algoritmos de predição da temperatura central de atletas durante exercícios físicos, utilizando técnicas de aprendizado de máquina.

## Estrutura do Repositório

- **data/**: Dados utilizados nos experimentos.
	- `dados-organizados-1-1km.csv`: Dataset principal já tratado para modelagem.
	- `raw_data.tsv`, `reduced_dataset.tsv`: Dados brutos e versões reduzidas para testes.
- **models/**: Notebooks e arquivos de modelagem.
	- `modelo-1-1km-refatorado.ipynb`, `teste-impacto-escalonamento.ipynb`, `modelo-final-1-1km.ipynb`: Notebooks em Python para avaliação, comparação e interpretação dos modelos.
	- `regression_models.ows`: Arquivo do Orange Data Mining para regressão linear.
- **README.md**

## Principais Funcionalidades

- Avaliação de diferentes algoritmos de regressão (Lasso, DecisionTree, RandomForest, XGBoost).
- Comparação de conjuntos de variáveis (features) e impacto do pré-processamento (escalonamento).
- Visualização dos resultados (gráficos de desempenho, tabelas comparativas).
- Interpretação dos modelos com SHAP para análise de importância das variáveis.

## Como Utilizar

1. Instale as dependências listadas em `requirements.txt`.
2. Execute os notebooks em `models/` para reproduzir os experimentos e visualizar os resultados.
3. Os dados necessários estão em `data/`. Ajuste o caminho dos arquivos nos notebooks se necessário.

## Sobre

Este projeto foi desenvolvido como material suplementar para artigo científico sobre predição da temperatura central de atletas. Para dúvidas, sugestões ou colaborações, entre em contato com os autores do artigo ou abra uma issue.