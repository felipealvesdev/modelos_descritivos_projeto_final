# Projeto Final: Análise de Mobilidade e Transporte Metropolitano

**Autor:** Seu Nome Completo
**Disciplina:** Aprendizado Descritivo - Modelos Não Supervisionados
**Professor:** Matheus Lacerda

## 📌 Objetivo do Projeto
Este projeto utiliza técnicas de Aprendizado Não Supervisionado (Clusterização) para analisar dados de mobilidade urbana em Regiões Metropolitanas brasileiras. O objetivo é agrupar regiões com características operacionais e financeiras semelhantes para embasar recomendações estratégicas.

## 📂 Estrutura do Repositório
- `data/raw/`: Base de dados original (PEMOB 2025).
- `notebooks/`: Jupyter Notebook com toda a análise, justificativas e modelagem.
- `reports/`: Gráficos gerados e apresentação final (Slides para o CEO).

## 🛠️ Como Executar
1. Clone este repositório.
2. Instale as dependências: `pip install -r requirements.txt`
3. Abra o notebook em `notebooks/01_analise_mobilidade.ipynb` e execute as células.

## 📊 Metodologia
1. Análise Exploratória dos Dados (EDA)
2. Tratamento de dados nulos e padronização (StandardScaler)
3. Aplicação de K-Means e Clusterização Hierárquica
4. Avaliação com Silhouette Score e Inércia
5. Tradução dos resultados para linguagem de negócios.