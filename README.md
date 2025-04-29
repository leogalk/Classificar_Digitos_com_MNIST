# Classificador de Dígitos com Redes Neurais Artificiais (RNA) no MNIST

Este projeto implementa uma Rede Neural Artificial (ANN) para a classificação de dígitos utilizando o conjunto de dados MNIST. O foco principal é comparar o impacto de diferentes tamanhos de lote no tempo de treinamento e no desempenho do modelo.

## Descrição do Projeto

Os principais objetivos são:
- Comparar diferentes tamanhos de lote (16, 32, 128, 512, 2048, 8192, 32768, lote completo)
- Analisar como o tamanho do lote afeta o tempo de treinamento
- Avaliar o desempenho e a precisão do modelo
- Testar a robustez do modelo utilizando ruído Gaussiano

The neural network consists of 2 hidden layers with ReLU activation and dropout regularization. Gaussian noise is added to the input data to evaluate model robustness in more realistic scenarios.

## Bibliotecas Utilizadas

- TensorFlow / Keras
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Pandas

## Como Executar esse programa

1. Clone o repositório
2. Abra o notebook Jupyter no Google Colab ou no Jupyter Lab
3. Execute todas as células na ordem de cima para baixo

Dica: Para tamanhos de lote maiores (8192, 32768), é recomendada memória de GPU suficiente

## Implementação do Ruído Gaussiano

O ruído Gaussiano é adicionado aos dados de entrada utilizando a camada GaussianNoise do TensorFlow:

# from tensorflow.keras.layers import Dense, Flatten, Dropout, GaussianNoise

# Adicionar ruído Gaussiano na entrada - isso ajuda na robustez
        GaussianNoise(noise_stddev, input_shape=(28, 28)),
