# 📈 Modelo Preditivo do Ibovespa  
### FIAP – Pós-Tech Data Analytics  
### Prova Substitutiva – Fase 2  

Este repositório contém o projeto completo de modelagem preditiva do **Índice Ibovespa**, desenvolvido como entrega da **Prova Substitutiva – Fase 2**, na trilha de **Cientista de Dados**.

O objetivo é construir um modelo de série temporal capaz de prever o **fechamento diário do Ibovespa** com **assertividade mínima de 80%**, utilizando técnicas de exploração, decomposição, testes estatísticos e comparação multimodelo.

---

# 🗂 Estrutura do Repositório

```
Fiap_project/
├── data/
│   └── Dados Históricos - Ibovespa.csv
├── notebooks/
│   └── modelo_preditivo_ibovespa_final_completo_metricas.ipynb
├── reports/
│   ├── projeto_ibovespa_artigo_cientifico_atualizado.docx
│   └── projeto_ibovespa_final_premium.pdf
└── README.md
```

---

# 📘 Descrição do Projeto

- **Índice analisado:** Ibovespa  
- **Fonte dos dados:** Investing.com  
- **Período:** 04/01/2021 a 14/11/2025  
- **Frequência:** Dias úteis (Business Days), com *forward fill*

O projeto realiza:

### ✔ Storytelling da série temporal  
Identificação de picos de alta/baixa, eventos econômicos, impacto de juros, fluxo estrangeiro e rupturas de tendência.

### ✔ Decomposição da série  
Separação em tendência, sazonalidade anual (≈ 252 pregões por ano) e componente irregular.

### ✔ Teste ADF (Augmented Dickey-Fuller)  
Verificação de estacionariedade e necessidade de diferenciação.

### ✔ ACF e PACF  
Fundamentação estatística do modelo ARIMA(1,1,1).

### ✔ Comparação multimodelo  
- ARIMA(1,1,1)  
- Holt-Winters (tendência aditiva)  
- Naive (Random Walk)

### ✔ Métricas estatísticas completas  
Incluindo análise crítica do erro, erro diário, MAPE segmentado e assertividade.

### ✔ Previsão dos próximos 15 dias úteis  
Utilizando Holt-Winters como modelo de suavização da tendência.

---

# 🤖 Modelos Avaliados

## **1. Naive (Random Walk) – Baseline mais forte**
Modelo simples e extremamente eficaz em mercados eficientes.

**Desempenho:**  
- MAPE ≈ **0,55%**  
- Assertividade ≈ **99,45%**

---

## **2. Holt–Winters – Modelo paramétrico complementar**
Indicado para projeções multi-step e tendência suavizada.

**Desempenho:**  
- MAPE ≈ **4,83%**

Observação crítica: falha em mudanças bruscas de tendência (erro final > 10%), mas útil para projeções de cenário.

---

## **3. ARIMA(1,1,1) – Modelo estatístico clássico**
Estruturado com base em ACF, PACF e ADF.

**Desempenho:**  
- MAPE ≈ **5,20%**

---

# 📊 Tabela Consolidada de Métricas

| Modelo                  | MAE  | RMSE | MAPE   | Assertividade |
|------------------------|------|------|--------|---------------|
| ARIMA(1,1,1)           | 7.72 | 9.16 | 5.20%  | 94.80%        |
| Holt-Winters           | 7.18 | 8.58 | 4.83%  | 95.17%        |
| Naive (Random Walk)    | 0.79 | 0.99 | 0.55%  | 99.45%        |

> A assertividade foi definida como **100% − MAPE**.  
> As análises detalhadas de erro (diário e segmentado) estão documentadas no notebook.

---

# ▶ Como Executar o Notebook no Google Colab

1. Faça o upload de:  
   - `modelo_preditivo_ibovespa_final_completo_metricas.ipynb`  
   - `Dados Históricos - Ibovespa.csv`

2. Insira na primeira célula:

```python
from google.colab import files
uploaded = files.upload()
```

3. Depois garanta que o caminho esteja assim:

```python
caminho = "Dados Históricos - Ibovespa.csv"
df = pd.read_csv(caminho)
```

4. Execute tudo:  
**Runtime > Run all**

---

# 📄 Relatórios Acadêmicos

Na pasta **reports/** você encontrará:

- **Artigo científico** (`.docx`)  
- **Versão PDF premium**  
- **Modelo com storytelling completo**  

Ambos com redação formal, metodologia científica e estrutura conforme exigido pela avaliação.

---

# 👤 Autor

**Nome:** Diogo Abreu de Siqueira  
**Curso:** Pós-Tech Data Analytics – FIAP  
**Entrega:** Prova Substitutiva – Fase 2  

---

# ⭐ Observação Final

Este repositório foi estruturado no formato profissional de projetos de Data Science, ideal para:

- portfólio  
- apresentação acadêmica  
- utilização real em investigações de mercado  
