# Projeto TelecomX - Predição de Churn

## 📌 Propósito da Análise
O objetivo principal deste projeto é **prever o churn de clientes** (evasão/cancelamento) com base em variáveis relevantes do perfil e comportamento dos clientes.  
Essa análise possibilita à empresa **identificar fatores críticos que influenciam a saída de clientes** e, a partir disso, **direcionar estratégias de retenção** mais eficazes.

---

## 📂 Estrutura do Projeto
A organização dos arquivos é a seguinte:

- **`TelecomX_parte2_BR_corrigido.ipynb`** → Notebook principal da análise, já revisado e corrigido.
- **`dados_tratados.csv`** → Base de dados limpa e pré-processada utilizada para treinar e avaliar os modelos.
- **`/visualizacoes`** (opcional) → Pasta sugerida para armazenar gráficos gerados, como:
  - Distribuição de variáveis numéricas e categóricas.
  - Matrizes de confusão.
  - Importância das variáveis (Permutation Importance).

---

## ⚙️ Preparação dos Dados

### 1. Classificação das variáveis
- **Numéricas:** colunas identificadas automaticamente como quantitativas (valores contínuos ou discretos).  
- **Categóricas:** colunas não numéricas (strings ou categorias) que foram transformadas via *One-Hot Encoding*.

### 2. Etapas de transformação
- **Imputação de valores ausentes:**  
  - Numéricas → substituídas pela mediana.  
  - Categóricas → substituídas pelo valor mais frequente.  
- **Normalização:**  
  - Numéricas escaladas com `StandardScaler` (média 0, desvio padrão 1).  
- **Codificação:**  
  - Variáveis categóricas codificadas com `OneHotEncoder` (tratando categorias desconhecidas).

### 3. Separação treino/teste
- **80% treino**  
- **20% teste**  
- **Estratificação** aplicada no caso de classificação binária para manter a proporção das classes.

### 4. Justificativas de escolhas
- **RandomForestClassifier** → escolhido por ser robusto, lidar bem com variáveis mistas e fornecer boa interpretabilidade via importância de variáveis.  
- **Validação Cruzada Estratificada (5-folds)** → garante avaliação justa em classes desbalanceadas.  
- **Permutation Importance** → usado para medir a contribuição de cada variável original, facilitando interpretação para o negócio.

---

## 📊 Exemplos de Gráficos e Insights

Durante a análise exploratória e a modelagem, alguns gráficos e insights foram gerados:

1. **Distribuição das variáveis** → mostrou diferenças relevantes entre clientes que ficaram e que saíram.  
2. **Matriz de confusão** → revelou a proporção de acertos e erros por classe.  
3. **Importância das variáveis** → evidenciou quais fatores têm maior peso na previsão de churn.  
   - Exemplo: variáveis de **tempo de contrato**, **tipo de plano** e **uso de determinados serviços** apareceram entre os mais relevantes.

Esses gráficos ajudam a **direcionar estratégias de retenção** para segmentos de maior risco.

---

## ▶️ Instruções de Execução

### 1. Pré-requisitos
Certifique-se de ter o **Python 3.8+** instalado. As principais bibliotecas necessárias são:

```bash
pip install pandas numpy matplotlib scikit-learn nbformat
```

### 2. Arquivos necessários
Coloque os arquivos:
- `dados_tratados.csv`
- `TelecomX_parte2_BR_corrigido.ipynb`

na mesma pasta do projeto.

### 3. Execução do notebook
Abra o Jupyter Notebook ou VSCode e rode:

```bash
jupyter notebook TelecomX_parte2_BR_corrigido.ipynb
```

ou no VSCode simplesmente **abrir e executar as células** do notebook.

---

## ✅ Conclusão Estratégica

O projeto mostrou que é possível **identificar fatores-chave do churn** e utilizá-los para:
- Priorizar clientes em risco.  
- Planejar ações de retenção direcionadas.  
- Monitorar indicadores relevantes de forma recorrente.  
- Apoiar decisões estratégicas com base em evidências.

---

📧 *Dúvidas e contribuições são bem-vindas!*
