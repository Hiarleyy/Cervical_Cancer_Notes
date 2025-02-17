---
data: 2025-02-12T09:58:00
Autor:
  - Pablo Deoclecia dos Santos, Erika Yahata, Talita Santos Piheiro, Fellipe Soares de Oliveira, Priscyla Waleska Simões
Reference: "[[Algoritmos+de+Machine+Learning+para+Predição+da+Sobrevida+do+Câncer+de+Mama.pdf]]"
tags:
  - "#NaiveBayers"
  - "#RandomForest"
  - MultiLayerPerceptron
  - "#AdaBoost"
---

---
*Síntese*: 

Estudo descritivo que considerou dados de 1.570 pacientes com câncer de mama estágio I-III. A técnica Synthetic Minority Oversampling Technique foi aplicada devido ao desbalanceamento do conjunto de dados. Foram considerados no estudo os algoritmos Naive Bayes, Random Forest, Multilayer Perceptron e AdaBoost, e como estratégia de aprendizagem a validação cruzada. Resultados: O modelo desenvolvido a partir do algoritmo Random Forest apresentou maior acurácia (96,2%; IC95%: 95,5%- 96,9%) e especificidade (97,4%; IC95%: 96,6%-98,2%); e o modelo desenvolvido a partir do AdaBoost, maior sensibilidade (95,3%; IC95%: 94,3%-96,4%). Conclusão: Assim, dentre os modelos apresentados em nosso estudo, o desenvolvido a partir do algoritmo Random Forest apresentou, no geral, as melhores medidas de avaliação na predição da sobrevida do Câncer de Mama.

Estudo descritivo que considerou um dataset público oriundo de um estudo realizado no hospital Sun Yat-sen Memorial, em Guangzhou na China, e conduzido entre janeiro de 2000 a dezembro de 2010 com dados de 1.570 pacientes com câncer de mama estágio I-III tratadas em ambiente hospitalar. A Tabela 1 ilustra os atributos considerados no estudo. No pré-processamento foi realizada a categorização e dicotomização dos atributos numéricos pela média. A técnica de reamostragem e imputação de dados sintéticos Synthetic Minority Oversampling Technique (SMOTE) foi aplicada, devido ao desbalanceamento do dataset.


![[Pasted image 20250212101220.png]]

A Tabela 2 apresenta as características da amostra antes e após a reamostragem com a aplicação do SMOTE no dataset original devido ao desbalanceamento da classe que desejamos analisar no nosso estudo, o desfecho Óbito e Sobrevida.

![[Pasted image 20250212101253.png]]

### Resultados
![[Pasted image 20250212101322.png]]