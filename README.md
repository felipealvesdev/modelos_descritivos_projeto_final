# Projeto Final: Análise de Mobilidade e Transporte Metropolitano

**Autor:** Felipe Alexandre Alves da Silva  
**Disciplina:** Modelos Descritivos  
**Professor:** Matheus Lacerda  
**Data de entrega:** 11/10/2026  

---

## 📌 Objetivo do Projeto

Este projeto utiliza técnicas de **Aprendizado Não Supervisionado (Clusterização)** para analisar dados de mobilidade urbana em **22 Regiões Metropolitanas brasileiras**. O objetivo é agrupar regiões com características operacionais e financeiras semelhantes, gerando insights estratégicos que possam embasar decisões de gestores públicos e privados do setor de transporte.

## 🎯 Problemática

> **"Quais são os diferentes perfis operacionais das Regiões Metropolitanas brasileiras e como podemos agrupá-las para direcionar investimentos e políticas públicas de mobilidade?"**

---

## 📊 Sobre os Dados

A base utilizada é o **PEMOB 2025** (Pesquisa Nacional de Mobilidade Urbana), contendo informações sobre infraestrutura, operação, demanda, finanças e tecnologia do transporte público nas Regiões Metropolitanas brasileiras.

Foram selecionadas **5 variáveis** representativas das dimensões fundamentais da mobilidade:

| Dimensão | Variável | Descrição |
|----------|----------|-----------|
| Infraestrutura | `Terminais` | Nº de terminais rodoviários |
| Infraestrutura | `Frota_Onibus` | Frota de ônibus operacionais |
| Operação | `Km_Percorrida` | Km percorrida por ônibus em 2024 |
| Qualidade | `Idade_Frota` | Idade média da frota (anos) |
| Demanda | `Passageiros_Comuns` | Nº de passageiros comuns |

---

## 📂 Estrutura do Repositório

```
├── data/
│   ├── raw/                              # Base original PEMOB 2025
│   └── processed/                        # Base com clusters atribuídos
├── notebooks/
│   └── 01_analise_mobilidade.ipynb       # Análise completa (EDA, K-Means, Hierárquico)
├── reports/
│   └── presentation/
│       └── felipe alves Analise-de-Mobilidade-Urbana.pdf  # Slides para o CEO
├── README.md
└── requirements.txt
```

---

## 🛠️ Como Executar

1. Clone este repositório:
   ```bash
   git clone https://github.com/felipealvesdev/modelos_descritivos_projeto_final.git
   cd modelos_descritivos_projeto_final
   ```

2. Instale as dependências:
   ```bash
   pip install -r requirements.txt
   ```

3. Abra o notebook e execute as células **na ordem, de cima para baixo**:
   ```
   notebooks/01_analise_mobilidade.ipynb
   ```

---

## 📊 Metodologia

1. **Análise Exploratória dos Dados (EDA)** — distribuições, outliers e correlações
2. **Tratamento de dados nulos** e **padronização** (`StandardScaler`)
3. **K-Means** com escolha do K pelo **Método do Cotovelo**
4. **Clusterização Hierárquica Aglomerativa** (validação via Dendrograma)
5. **Avaliação** com múltiplas métricas internas:
   - Silhouette Score
   - Davies-Bouldin Index
   - Calinski-Harabasz Index
6. **Tradução dos resultados** para linguagem de negócios (slides do CEO)

---

## 🔍 Principais Resultados

Foram identificados **3 perfis operacionais distintos**:

| Cluster | Perfil | RMs | Frota Média | Idade Média |
|---------|--------|-----|-------------|-------------|
| 0 | **Capitais Regionais** | 7 (31.8%) | ~1.326 ônibus | ~9 anos |
| 1 | **Regiões em Desenvolvimento** | 13 (59.1%) | ~113 ônibus | ~15 anos |
| 2 | **Metrópoles Globais** | 2 (9.1%) | ~3.690 ônibus | ~7 anos |

**Métricas de avaliação:**
- **Silhouette Score:** 0.5383 (estrutura forte e bem definida)
- **Davies-Bouldin Index:** ver notebook
- **Calinski-Harabasz Index:** ver notebook

---

## 💡 Recomendações Estratégicas

- **Cluster 0 (Capitais Regionais)** → Modernização de frota, adoção de AVL/bilhetagem eletrônica e expansão da integração tarifária.
- **Cluster 1 (Regiões em Desenvolvimento)** → Programa emergencial de renovação de frota e ampliação de terminais (ROI alto).
- **Cluster 2 (Metrópoles Globais)** → Liderar transição para mobilidade elétrica, IA e IoT.

---

## 🔗 Links

- **Repositório:** [github.com/felipealvesdev/modelos_descritivos_projeto_final](https://github.com/felipealvesdev/modelos_descritivos_projeto_final)
- **Base de dados:** [PEMOB 2025 — Pesquisa Nacional de Mobilidade Urbana](https://www.gov.br/cidades/pt-br/assuntos/mobilidade-urbana/pesquisa-nacional-de-mobilidade-urbana-pemob-2025) — Ministério das Cidades
- **Slides para o CEO:** [`reports/presentation/felipe alves Analise-de-Mobilidade-Urbana.pdf`](reports/presentation/felipe%20alves%20Analise-de-Mobilidade-Urbana.pdf)

---

## 📚 Referências

- JAMES, G. et al. *An Introduction to Statistical Learning*. Springer, 2013.
- DEZA, M. M.; DEZA, E. *Encyclopedia of Distances*. Springer, 2009.
- Documentação scikit-learn: [K-Means](https://scikit-learn.org/stable/modules/clustering.html#k-means)
- Documentação SciPy: [Hierarchical Clustering](https://docs.scipy.org/doc/scipy/reference/cluster.hierarchy.html)