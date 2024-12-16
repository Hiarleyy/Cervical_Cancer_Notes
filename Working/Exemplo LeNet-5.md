---
Status: Ativo
data: 2024-12-16T15:37:00
tags:
  - LeNet-5
  - Rede_Neural
Contribuição:
  - Hiarley
---
---


# MNIST Classifier Documentation
**Este script implementa um classificador de dígitos manuscritos usando a arquitetura LeNet-5 e o dataset MNIST.**
## Importações

```python
from tensorflow.keras.layers import Conv2D, AveragePooling2D, Flatten, Dense
from tensorflow.keras.utils import to_categorical
from tensorflow.keras.datasets import mnist
import numpy as np
import matplotlib.pyplot as plt````

	Importa as bibliotecas necessárias para a construção e treinamento do modelo, bem como para a manipulação de dados e visualização.
## Carregamento e Pré-processamento dos Dados
```python
(x_train, y_train), (x_test, y_test) = mnist.load_data()
x_train = x_train.reshape(-1, 28, 28, 1).astype('float32') / 255.0
x_test = x_test.reshape(-1, 28, 28, 1).astype('float32') / 255.0
y_train = to_categorical(y_train, num_classes=10)
y_test = to_categorical(y_test, num_classes=10)
```
	Carrega o dataset MNIST e realiza o pré-processamento dos dados, incluindo a normalização das imagens e a conversão dos rótulos para o formato categórico.
## Construção do Modelo
```python 
model = Sequential([
    Conv2D(filters=6, kernel_size=(5, 5), activation='tanh', input_shape=(28, 28, 1), padding='same'),
    AveragePooling2D(pool_size=(2, 2), strides=2),
    Conv2D(filters=16, kernel_size=(5, 5), activation='tanh'),
    AveragePooling2D(pool_size=(2, 2), strides=2),
    Flatten(),
    Dense(units=120, activation='tanh'),
    Dense(units=84, activation='tanh'),
    Dense(units=10, activation='softmax')
])
```
	Define a arquitetura do modelo LeNet-5 usando a API Sequencial do Keras.
## Compilação do Modelo
```python
model.compile(optimizer='adam', loss='categorical_crossentropy', metrics=['accuracy'])
```
	Compila o modelo especificando o otimizador, a função de perda e a métrica de avaliação.
## Treinamento do Modelo

```python
model.fit(x_train, y_train, batch_size=32, epochs=10, validation_split=0.2)
```
	Treina o modelo usando os dados de treinamento, com um tamanho de batch de 32 e por 10 épocas. Utiliza 20% dos dados de treinamento para validação.
## Avaliação do Modelo
```python
test_loss, test_acc = model.evaluate(x_test, y_test)
print(f"Acurácia no conjunto de teste: {test_acc:.2f}")
```
## Output do Mnist

``` python
def mostrar_exemplos(numero, dataset, labels):
    if numero < 0 or numero > 9:
        print("Por favor, insira um número entre 0 e 9.")
        return
    # Converter rótulos one-hot para valores escalares
    labels_scalar = np.argmax(labels, axis=1)
    # Filtrar imagens correspondentes ao número
    indices = np.where(labels_scalar == numero)[0]
    print(f"Encontrados {len(labels)} exemplos para o número {numero}.") 
    if len(indices) == 0:
        print(f"Nenhum exemplo encontrado para o número {numero}.")
        return
    exemplo = dataset[indices[:5]].reshape(-1,28, 28)  # Redimensionar para 2D para exibição
    plt.figure(figsize=(10, 2))
    for i, exemplo in enumerate(exemplo):
        plt.subplot(1, 5, i + 1)
        plt.imshow(exemplo, cmap='gray')
        plt.axis('off')
    plt.suptitle(f"Exemplos do número {numero}", fontsize=16)
    plt.show()
    
while True:
    try:
        numero = int(input("Digite um número entre 0 e 9 para ver exemplos (ou -1 para sair): "))
        if numero == -1:
            print("Encerrando o programa.")
            break
        mostrar_exemplos(numero, x_train, y_train)
    except ValueError:
        print("Entrada inválida. Por favor, insira um número entre 0 e 9.")
```
	A função recebe um imput do teclado, sendo um algarismo de 0 a 9, após isso realiza uma busca no dataset definido e retorna os primeiros 5 resultados referente ao número escolhido