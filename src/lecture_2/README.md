The purpose of artificial intelligence is to find values (weights or hypotheses "w") that, when interacting with the input data "x", return values that are as close as possible to the expected output values "y".

In supervised machine learning, the weights are adjusted to find a common denominator among the training data. This is done by minimizing the average deviation between the training output "y" and the interaction of the weights "w" with the input values "x". Essentially, we want to find a value for "w" such that the expression "y - wx" is as close to zero as possible.

To achieve this, we use the gradient descent algorithm, which operates as follows:

The gradient descent is the algorithm that will find the value of "w". It will do this by:

1 - Creating a function that calculates the mean of the distance of the standard deviation of the values x and y in the dataset in such a way that when summing the results of the differences of the input vector values, the negative difference results do not cancel out the positive results. To do this, we calculate the square of the difference:
h(w) = 1/nΣ(y - wx)²

2 - Using partial derivatives to calculate how the adjustment of the weights "w" affects the final result of this function. In other words, we create a function to find the vector variation of "w" over the function h(w). The partial derivative with respect to "w" is given by:
∂w/∂h(w) = 2/nΣx(y-wx)

3 - Now we use the value of the partial derivative to update the weight (w) in order to try to reach the local minimum of the function h(w) so that the result of the function h(w) returns the minimum standard deviation (i.e., as close to 0 as possible). To move towards the local minimum of the function, the intuitive approach would be to simply subtract the weight value by its partial derivative "w - ∂w/∂h(w)"  but that is not enough. When we decrease the weight value by its partial derivative, we are moving negatively as much as possible within the function, which might cause us to overshoot the local minimum. To prevent this, we use what is called the learning rate (t), a constant that reduces the step size towards the local minimum of the function. This value is usually "0.01" but must be calibrated to take steps that are neither too small nor too large:
w := w - ∂w/∂h(w) * t

We use this algorithm to repeatedly update the value of w until we reach the optimal weight.

Stochastic gradient descent, unlike gradient descent which seeks to correct the deviation of input and output data by analyzing the mean of the standard deviation and reaching the local minimum of the mean squared error function, seeks to correct the deviation using the input and output data individually. In other words, for each weight update, the algorithm adjusts the deviation of only one input-output pair at a time. This way, instead of finding the local minimum, the value found is potentially more precise, possibly being the global minimum. However, this works better for datasets with many examples.

In practice:

- Stochastic gradient descent is much more commonly used.
- The learning rate usually starts with large values and decreases during the weight update iteration.

-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=

O proposito da inteligencia artificial é encontrar valores (pesos ou hipoteses "w") que ao interagir com os dados de entrada "x", retornem valores que se aproximem o máximo possível dos valores de saída esperados "y"

Na aprendizagem de máquina supervisionada, os pesos são ajustados para encontrar um denominador comum entre os dados de treinamento. Isso é feito minimizando o desvio médio entre a saída de treinamento "y" e a interação dos pesos "w" com os valores de entrada "x". Em essência, queremos encontrar um valor para "w" de modo que a expressão "y - wx" seja tão próxima de zero quanto possível.

Para alcançar isso, utilizamos o algoritmo de gradiente descendente, que opera da seguinte maneira:
 
 O gradiente descendente é o algoritimo que irá encontrar o valor de "w", ele irá fazer isso:
 
 1 - Criando uma função que calcule a media de distancia do desvio padrão dos valores x e y do dataset de forma que ao realizar a soma do resultado da diferença dos valores do vetor de entrada os resultados da diferença que retornaram valores negativos não anulem os resultados positivos, para isso calculamos o quadrado da diferença:
  h(w) = 1/nΣ(y - wx)²
 
2 - Utilizamos as derivadas parciais para calcular como o ajuste dos pesos "w" afeta o resultado final desta função, ou seja fazemos uma função para encontramos o valor de variação vetorial de "w" sobre a função h(w). A derivada parcial em relação a "w" é dada por: 
∂w/∂h(w) = 2/nΣx(y-wx)


3 - Agora usamos o valor da derivada parcial para atualizar o peso (w) de forma a tentarmos alcançar o minimo local da função h(w) para que assim o resultado da função h(w) retorne o desvio padrão minimo da função (ou seja, o mais proximo de 0). Para irmos em direção ao minimo local da função o intuitivo seria apenas subtraimos o valor do peso pelo de sua derivada parcial "w - ∂w/∂h(w)", mas isso não é tudo, quando diminuimos o valor do peso pelo de sua derivada parcial estamos nos movendo negativamente o maximo possivel da variação daquele peso dentro da função, dessa forma podemos acabar encontrando o valor minimo local da função e passando por ele por andarmos demais. Para que isso não aconteça usamos oque chamamos de taxa de aprendizando (t), uma constante que diminui o tamanho do "passo" dado em direção ao minimo local da função, esse valor costuma ser "0.01", mas deve ser calibrado para dar passos nem muito pequenos e nem muito grandes:
w := w - ∂w/∂h(w) * t

Usamos este algoritimo para atualizar o valor de w repetidamente até chegar ao peso ideal

O gradiente estocástico, ao contrário do gradiente descendente que busca a correção do desvio dos dados de entrada e saída analisando a média do desvio padrão e chegando ao mínimo local da função de erro médio quadrático, procura corrigir o desvio usando os dados de entrada e saída individualmente. Ou seja, para cada atualização do peso, o algoritmo ajusta o desvio de apenas uma entrada e saída por vez. Dessa forma, em vez de encontrar o mínimo local, o valor encontrado é potencialmente mais preciso, podendo ser o mínimo global. No entanto, isso funciona melhor para conjuntos de dados com muitos exemplos.

 Na pratica:
 - O gradiente estocratico é muito mais ultilizado
 - A taxa de apredizada costuma começar com valores grandes e ir diminuindo durante a iteração de atualização do peso 

-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=-=

    
