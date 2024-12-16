---
Status: Ativo
data: 2024-09-27T16:14:00
tags:
  - Rede_Neural
  - Visao_Computacional
Contribuição:
  - Hiarley
Reference: "[[Gradient-Based Learning Applied.pdf]]"
---
---
### **Principais Insights e Objetivos**

- **Aprendizado Automático**: Métodos de aprendizado têm sido fundamentais para o sucesso em aplicações como reconhecimento de fala contínua e escrita manual.
- **Mudança de Paradigma**: A ênfase está passando de heurísticas manuais para sistemas automáticos, possibilitados pelos avanços em tecnologia e aprendizado de máquina.

---

### **Estrutura Tradicional de Reconhecimento de Padrões**

1. **Extrator de Características**:
    - Transforma padrões em vetores ou símbolos de baixa dimensão, mais fáceis de comparar e invariantes a distorções.
    - Geralmente é manual e específico para a tarefa, exigindo esforço significativo de design.
2. **Classificador**:
    - Treinável e de uso geral, mas dependente da qualidade das características extraídas.
    - A precisão do reconhecimento é limitada pela habilidade do projetista em definir boas características.

---

### **Desafios e Limitações Históricas**

- Criar bons extratores de características é trabalhoso e precisa ser repetido para cada problema.
- Os classificadores anteriores não lidavam bem com espaços de alta dimensão, exigindo redução dimensional.

---

### **Avanços Recentes**

1. **Computação Mais Potente**:
    - Hardware mais rápido e acessível permite métodos intensivos computacionalmente.
2. **Grandes Conjuntos de Dados**:
    - Dados reais em grande volume ajudam a superar a dependência de características manuais.
3. **Técnicas Avançadas de Aprendizado**:
    - Redes neurais modernas lidam bem com entradas de alta dimensão e decisões complexas.

---

### **Arquiteturas Especializadas**

- **Redes Neurais Convolucionais (CNNs)**:
    - Incorporam invariâncias de formas 2D usando conexões locais e compartilhamento de pesos.
    - Projetadas para tarefas como reconhecimento de caracteres manuscritos.

---

### **Estudos de Caso e Aplicações**

1. **Reconhecimento de Dígitos Manuscritos**:
    - Comparação de diferentes métodos de aprendizado em conjuntos de dados de referência.
2. **Compreensão de Documentos**:
    - Integração de módulos treinados para reduzir erros gerais usando Redes de Transdução Treináveis (GTNs).
    - Aplicações incluem reconhecimento de palavras e frases completas.

---

### **Conceitos Avançados**

1. **Método HOS**:
    - Técnica clássica para reconhecimento de sequências de palavras.
2. **Treinamento Baseado em Gradiente**:
    - Métodos para treinar sem necessidade de segmentação manual.
3. **NN de Deslocamento Espacial**:
    - Elimina heurísticas de segmentação ao escanear entradas em várias localizações.

---

### **Implementação Prática**

- **LeNet-5**:
    - Rede neural convolucional usada em sistemas comerciais, como reconhecimento de cheques bancários.
    - Processa milhões de cheques mensalmente nos Estados Unidos, mostrando a eficácia de NNs.


---
### **Aprendizado a Partir de Dados**

- O aprendizado automático baseia-se em funções parametrizadas para transformar padrões de entrada em saídas desejadas, avaliadas por uma **função de perda** que mede os erros.
- O objetivo do aprendizado é minimizar a perda média usando um conjunto de dados de treinamento.
- A capacidade do modelo e o número de amostras afetam a **generalização**. O erro no conjunto de teste diminui com mais dados, mas há um equilíbrio entre capacidade do modelo e precisão no teste.

---

### **Minimização Baseada em Gradiente**

1. **Fundamentos**:
    - Minimizar funções contínuas é mais simples do que funções discretas.
    - A abordagem calcula gradientes para ajustar parâmetros e reduzir a função de perda.
2. **Métodos**:
    - **Descida do Gradiente**: Algoritmo básico que ajusta os parâmetros iterativamente.
    - **Gradiente Estocástico (Online)**: Atualiza os parâmetros usando gradientes baseados em exemplos únicos, sendo mais eficiente em grandes conjuntos de dados.
3. **Avanços**:
    - Apesar de limitações teóricas, redes neurais profundas se beneficiam de técnicas como **backpropagation**, que calcula gradientes de forma eficiente.

---

### **Backpropagation e Sucessos**

- Popularizado nos anos 80, o algoritmo de backpropagation permite o aprendizado em redes profundas com múltiplas camadas.
- Avanços ocorreram devido à superação do problema de mínimos locais, especialmente em redes com capacidade excedente.

---

### **Reconhecimento de Escrita Manual**

- Redes Neurais Convolucionais (CNNs) têm excelente desempenho no reconhecimento de dígitos manuscritos.
- Problemas como segmentação de caracteres (separação de letras vizinhas) são desafiadores. Métodos tradicionais como HOS dependem de heurísticas, mas abordagens baseadas em gradiente, como redes treináveis globalmente, têm mostrado melhores resultados.

---

### **Sistemas Treináveis Globalmente**

- Sistemas de reconhecimento de padrões geralmente envolvem múltiplos módulos (segmentação, reconhecimento, pós-processamento), otimizados individualmente.
- Uma abordagem mais eficiente é treinar o sistema inteiro para minimizar uma **função de perda global**, representando a probabilidade de erro em nível de documento.
- Isso é viável se o sistema for projetado como uma rede de módulos diferenciáveis, permitindo o uso de gradientes para ajustar todos os parâmetros.

---

### **Sistemas de Grafos Treináveis (GTNs)**

- Os GTNs são extensões de redes neurais tradicionais, onde a informação de estado é representada por grafos.
- Cada módulo de um GTN processa grafos para produzir novos grafos, e os gradientes são calculados para treinar todos os módulos conjuntamente.
---
### CONVOLUTIONAL NEURAL NETWORKS FOR I SOLATED CHARACTER RECOGNITION

- **Aprendizado a partir de entradas brutas**:
    
    - Redes convolucionais (CNNs) conseguem aprender diretamente de imagens normalizadas por tamanho e centralizadas, reduzindo a dependência de extratores de características projetados manualmente.
    - Isso contrasta com abordagens tradicionais que separam a extração de características da classificação.
- **Limitações das redes totalmente conectadas**:
    
    - **Explosão de parâmetros**: Camadas totalmente conectadas para imagens de entrada grandes resultam em um número impraticável de pesos (por exemplo, dezenas de milhares), aumentando a capacidade do sistema e exigindo grandes conjuntos de treinamento.
    - **Restrições de hardware**: Requisitos de memória dessas arquiteturas podem dificultar a implementação prática.
    - **Falta de invariância**: Redes totalmente conectadas não possuem invariâncias embutidas a translações, distorções e variações de posição nos dados de entrada.
- **Benefícios das CNNs**:
    
    - **Compartilhamento de pesos**: As CNNs utilizam configurações de pesos replicados em regiões espaciais, obtendo invariância a translações de forma natural e reduzindo o número de parâmetros.
    - **Consciência da topologia de entrada**: Camadas convolucionais respeitam a estrutura local 2D das imagens, aproveitando correlações espaciais entre pixels. Isso permite que as CNNs detectem padrões, como bordas e cantos, de maneira mais eficiente.
    - **Eficiência**: Restringir os campos receptivos das unidades ocultas a regiões locais reduz a complexidade computacional e melhora a capacidade da rede de aprender características distintivas.
- **Desafios com pré-processamento**:
    
    - Imagens de caracteres requerem pré-processamento (por exemplo, normalização de tamanho, centralização), mas esses passos não são perfeitos. A variabilidade nos estilos de escrita e nos métodos de pré-processamento (como normalização em nível de palavra) introduz desafios, como variações de posição, inclinação e tamanho.
- **Design de redes convolucionais**:
    
    - Estruturando redes para extrair e combinar características locais, as CNNs conseguem generalizar melhor diante de variações nos dados de entrada, enquanto reduzem a redundância nas instâncias de treinamento.


