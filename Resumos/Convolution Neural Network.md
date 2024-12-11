---
Status: Ativo
data: 2024-12-11T16:00:00
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
- O Filtro opera como uma convolução matemática sobre os dados gerando um mapa de características (**Feature Maps**)
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

---
# Principais modelos de CNN utilizados
- **AlexNet**: Foi um dos primeiros a demonstrar o potencial das CNNs em competições de visão computacional, especialmente na ImageNet em 2012. Ele usa várias camadas convolucionais e pooling, seguido por camadas totalmente conectadas.
    
- **VGGNet**: Conhecida por sua simplicidade e profundidade fixa (geralmente com 16 ou 19 camadas). Ele utiliza pequenas janelas de convolução (3x3) e é popular em benchmarks devido à sua eficácia.
    
- **ResNet (Residual Network)**: Introduziu blocos residuais, que ajudam no treinamento de redes profundas ao resolver problemas de gradiente desaparecendo. Este modelo é usado em muitas aplicações modernas.
    
- **Inception (ou GoogLeNet)**: Conhecida por seu design de "módulos de inception", que processam diferentes tamanhos de filtros convolucionais em paralelo, combinando-os em uma única saída.
    
- **EfficientNet**: Otimiza o desempenho e o custo computacional ajustando a largura, profundidade e resolução da rede de maneira equilibrada.
    
- **YOLO (You Only Look Once)**: Amplamente utilizado em detecção de objetos em tempo real. Diferente das CNNs clássicas, YOLO processa toda a imagem em uma única passada.
    
- **DenseNet (Dense Convolutional Network)**: Introduz conexões densas entre camadas convolucionais, reutilizando recursos e promovendo um fluxo de gradiente eficiente.



