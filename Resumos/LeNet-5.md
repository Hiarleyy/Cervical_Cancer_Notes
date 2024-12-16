---
Status: Ativo
data: 2024-12-16T11:34:00
tags:
  - LeNet-5
  - Rede_Neural
Contribuição:
  - Hiarley
---
---

### Design do LeNet-5: Arquitetura para Reconhecimento de Dígitos

#### **Estrutura Geral**
O LeNet-5 é composto por sete camadas treináveis (excluindo a entrada) que incluem camadas convolucionais, de subamostragem (pooling) e totalmente conectadas. Cada camada foi projetada para realizar uma tarefa específica, como extração de características, redução da dimensionalidade e classificação.

---

#### **2. Componentes do LeNet-5**

1. **Entrada**:
    
    - **Dimensão**: Uma imagem de tamanho fixo 32×3232 \times 3232×32 pixels, em escala de cinza (1 canal).
    - **Pré-processamento**: Antes de ser inserida no modelo, a imagem passa por normalização (centralização e redimensionamento), garantindo uniformidade.
2. **Camada Convolucional 1 (C1)**:
    
    - **Operação**: Convolução com 6 filtros (5×55 \times 55×5), produzindo 6 mapas de características (feature maps).
    - **Saída**: Cada mapa de características tem tamanho 28×2828 \times 2828×28 (redução devido à convolução).
    - **Objetivo**: Detectar padrões locais simples, como bordas e cantos.
3. **Camada de Subamostragem (S2)**:
    
    - **Operação**: Subamostragem (average pooling) com fator 2×22 \times 22×2, reduzindo o tamanho dos mapas para 14×1414 \times 1414×14.
    - **Objetivo**: Reduzir a dimensionalidade, mantendo informações relevantes e introduzindo invariância a pequenas translações.
4. **Camada Convolucional 2 (C3)**:
    
    - **Operação**: Convolução com 16 filtros (5×55 \times 55×5), conectados a subconjuntos dos mapas da camada anterior.
    - **Saída**: Mapas de características de tamanho 10×1010 \times 1010×10.
    - **Objetivo**: Detectar padrões mais complexos, como combinações de bordas e formas.
5. **Camada de Subamostragem (S4)**:
    
    - **Operação**: Average pooling (2×22 \times 22×2), reduzindo os mapas para 5×55 \times 55×5.
    - **Objetivo**: Similar à camada S2, com maior compactação das informações.
6. **Camada Convolucional 3 (C5)**:
    
    - **Operação**: Convolução com 120 filtros (5×55 \times 55×5), conectados a todos os mapas da camada anterior.
    - **Saída**: Vetor de 120 características (1D).
    - **Objetivo**: Reduzir dimensionalidade enquanto extrai características globais.
7. **Camada Totalmente Conectada (F6)**:
    
    - **Operação**: Camada densa com 84 neurônios.
    - **Objetivo**: Combinar as características extraídas para distinguir entre classes.
8. **Saída (F7)**:
    
    - **Operação**: Camada com 10 neurônios (uma para cada dígito de 0 a 9).
    - **Ativação**: Softmax, para gerar probabilidades de cada classe.
    - **Objetivo**: Classificar o dígito manuscrito.







