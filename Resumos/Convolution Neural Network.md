---
Status: Ativo
data: 
tags:
  - Visao_Computacional
  - Rede_Neural
Contribuição:
  - Hiarley
---
---

Redes Neurais Convolucionais (CNNs - _Convolutional Neural Networks_) são uma classe de redes neurais artificiais projetadas para processar dados estruturados em grades, como imagens e séries temporais. Elas são amplamente utilizadas em aplicações de visão computacional, reconhecimento de padrões, processamento de imagens e vídeos, e em outras áreas que envolvem dados visuais ou sequenciais.

## Estrutura das Redes Neurais Convolucionais

### 1. **Camadas Convolucionais:**
- Camadas de aplicação de filtros (Kernels) sobre os dados de entrada a fim de extrair as características desejadas (bordas,texturas e formas)
- O Filtro opera como uma convolução matemática sobre os dados gerando um mapa de características (<span style="background:#ff4d4f">feature maps</span>)
- Operações como essas permitem que a rede capture as informações espaciais e hierárquicas

### 2. **Camadas de Pooling:**
-  Reduzem as dimensões dos mapas de características, a fim de manter as informações relevantes. reduzindo a quantidade de parâmetros e o custo computacional
-  Métodos de pooling mais conhecidos são: **Max Pooling**(seleciona o maior valor de uma região) e o **average pooling** (cálculo da média)
- a operação de pooling é altamente importante para a robustez da rede, a deixando menos sensível a pequenas variações de entrada que contribuem para uma mudança dos resultados esperados
### 3. **Camadas de Flatten:**
- Prepara os dados para serem processados pelas camadas densas (*fully connected*), onde requerem **entradas unidimensionais (vetores)**
- Facilitar a integração dos recursos extraídos em decisões finais, como classificação ou predição.
- Se a saída de uma camada convolucional ou de pooling tem dimensões $s =  h . w . c$ (Altura,largura,número de canais), a camada Flatten transforma isso em um vetor de dimensão $h . w. c$
- Geralmente, a camada _Flatten_ é colocada logo após as camadas convolucionais/pooling e antes da primeira camada densa.




