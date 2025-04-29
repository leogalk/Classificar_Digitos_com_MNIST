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

 Adicionar ruído Gaussiano na entrada - isso ajuda na robustez
        GaussianNoise(noise_stddev, input_shape=(28, 28)),


Nesse trabalho o foco foi a diferenciação entre os resultados das batchs tendo os testes sendo realizados em batchs de [16, 32, 128, 512, 2048, 8192, 32768] com 10 epocas e a taxa de noise de 0,3 que é o mais padrão modificando a imagem original não tanto a ponto de se tornar quase impossivel de identificar o algarismo.

os codigos mais relacionados a essas funções são:

 - A função create_model(noise_stddev=0.3), que define a arquitetura da rede neural, aplicando a camada GaussianNoise logo na entrada, seguida de duas camadas densas com ativação ReLU e regularização por dropout.

 - A função train_and_evaluate_model(batch_size, epochs=10, noise_stddev=0.3), responsável por treinar o modelo com diferentes tamanhos de batch e registrar o histórico de treinamento para análise posterior.

 - A função plot_learning_curves(histories, batch_sizes), que gera gráficos comparativos entre a acurácia e a perda de validação de cada batch size utilizado, permitindo uma visualização clara das diferenças de desempenho.

Na parte de verificação temos o teste do batch 32 que se provou o mais efetivo tanto em acuracia quanto do tempo nescessario para treina-lo ele pega 50 numeros aleatorios e faz a verificação comparando a previsão e o real valor do numero.
