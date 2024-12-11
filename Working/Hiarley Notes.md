---
Status: Ativo
data: 2024-09-27T16:14:00
tags:
  - Seaborn
  - Matriz_correlacao
  - Python
Contribuição:
  - Hiarley
---
---
#### Importação de Bibliotecas

O código importa as bibliotecas necessárias para análise de dados e visualização:

```python
import seaborn as sb
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```
- [`seaborn`](vscode-file://vscode-app/c:/Users/Marcos%20Hiarley/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-sandbox/workbench/workbench.html) (sb): Biblioteca para visualização de dados baseada no Matplotlib.
- [`pandas`](vscode-file://vscode-app/c:/Users/Marcos%20Hiarley/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-sandbox/workbench/workbench.html) (pd): Biblioteca para manipulação e análise de dados.
- [`numpy`](vscode-file://vscode-app/c:/Users/Marcos%20Hiarley/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-sandbox/workbench/workbench.html) (np): Biblioteca para operações matemáticas e manipulação de arrays.
- [`matplotlib.pyplot`](vscode-file://vscode-app/c:/Users/Marcos%20Hiarley/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-sandbox/workbench/workbench.html) (plt): Biblioteca para criação de gráficos.

#### Carregamento dos Dados
```python
df = pd.read_csv('kag_risk_factors_cervical_cancer.csv', sep=",", na_values='?')
```

Carrega o conjunto de dados `kag_risk_factors_cervical_cancer.csv` em um DataFrame do Pandas, tratando os valores '?' como valores ausentes (NaN).

#### Cálculo da Matriz de Correlação
```python
correlation_matrix = df.corr()
```
Calcula a matriz de correlação entre as variáveis do DataFrame.

#### Configuração e Criação do Mapa de Calor
```python
plt.figure(figsize=(12, 8))
sb.heatmap(correlation_matrix, annot=True, cmap='coolwarm', linewidths=0.5)
plt.show()
```

1. Configura o tamanho da figura para 12x8 polegadas.
2. Cria um mapa de calor da matriz de correlação usando [`seaborn.heatmap`](vscode-file://vscode-app/c:/Users/Marcos%20Hiarley/AppData/Local/Programs/Microsoft%20VS%20Code/resources/app/out/vs/code/electron-sandbox/workbench/workbench.html), com anotações das correlações, um esquema de cores 'coolwarm' e linhas de grade com largura de 0.5.
3. Exibe o gráfico gerado.
---



$$
$$













