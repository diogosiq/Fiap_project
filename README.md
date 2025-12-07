# 📈 Modelo Preditivo do Ibovespa  
### FIAP – Pós-Tech Data Analytics  
### Prova Substitutiva – Fase 2  

Este repositório contém o projeto de modelagem preditiva do **Índice Ibovespa**, entregue como parte da **Prova Substitutiva – Fase 2** do curso Pós-Tech em Data Analytics da FIAP.

O objetivo é desenvolver um modelo de série temporal capaz de prever o **fechamento diário do Ibovespa**, com **assertividade mínima de 80%**, aplicando uma análise completa baseada em métodos estatísticos e interpretação crítica dos resultados.

---

# 📁 Arquivos do Repositório

```
.
├── Dados Históricos - Ibovespa.csv
└── modelo_preditivo_ibovespa_completo_metricas_time_series_FIAP_FINAL.ipynb
```

### **`Dados Históricos - Ibovespa.csv`**  
Base histórica utilizada para a modelagem, contendo o fechamento diário do Ibovespa.

### **`modelo_preditivo_ibovespa_completo_metricas_time_series_FIAP_FINAL.ipynb`**  
Notebook **executado**, contendo todo o passo a passo da análise:

- exploração e storytelling da série temporal  
- decomposição da série  
- teste ADF  
- análise de autocorrelação (ACF/PACF)  
- construção de modelos (Naive, Holt-Winters, ARIMA)  
- métricas estatísticas completas  
- previsão dos próximos 15 dias úteis  
- análise crítica dos modelos  

---

# 🧠 Storytelling e Análise da Série Temporal

A série histórica do Ibovespa (2021–2025) apresenta:

- ciclos de **valorização** associados a otimismo econômico e fluxo estrangeiro  
- períodos de **queda** motivados por incerteza fiscal, juros e eventos globais  
- movimentos bruscos em períodos de volatilidade  
- tendência estrutural de longo prazo  
- componente irregular expressivo  

O storytelling contextualiza picos de alta e baixa, relacionando-os a eventos macroeconômicos relevantes.

---

# 🔬 Métodos Aplicados

### ✔ Decomposição da Série  
Separação em tendência, sazonalidade anual e componente irregular.

### ✔ Teste de Estacionariedade (ADF)  
Confirmação da necessidade de diferenciação da série original.

### ✔ ACF e PACF  
Base estatística para o modelo ARIMA(1,1,1).

### ✔ Modelos Avaliados  
- **Naive (Random Walk)** – melhor baseline em finanças  
- **Holt-Winters** – suavização com tendência aditiva  
- **ARIMA(1,1,1)** – modelo paramétrico clássico  

---

# 📊 Métricas Estatísticas Comparativas

| Modelo                  | MAE  | RMSE | MAPE   | Assertividade |
|------------------------|------|------|--------|---------------|
| ARIMA(1,1,1)           | 7.72 | 9.16 | 5.20%  | 94.80%        |
| Holt-Winters           | 7.18 | 8.58 | 4.83%  | 95.17%        |
| Naive (Random Walk)    | 0.79 | 0.99 | 0.55%  | 99.45%        |

> ✔ Todos os modelos superaram 80% de assertividade.  
> ✔ O Naive foi o mais forte em 1-step ahead.  
> ✔ O Holt-Winters demonstrou limitações em rupturas bruscas — analisado com erro diário e MAPE segmentado no notebook.  

---

# 📅 Previsão dos Próximos 15 Dias Úteis

Realizada com **Holt-Winters**, que produz uma tendência suavizada e adequada para projeções multi-step.

---

# ▶ Como Executar o Notebook no Google Colab

1. Acesse: https://colab.research.google.com  
2. Faça upload de:
   - `modelo_preditivo_ibovespa_completo_metricas_time_series_FIAP_FINAL.ipynb`
   - `Dados Históricos - Ibovespa.csv`
3. Execute tudo com:
```
Runtime > Run all
```
4. Certifique-se de que o código inicial use:
```python
caminho = "Dados Históricos - Ibovespa.csv"
```

---

# 👤 Autor

**Nome:** Diogo Abreu de Siqueira  
**RM:** 357870  
**Curso:** Pós-Tech Data Analytics – FIAP  
**Entrega:** Prova Substitutiva – Fase 2  
