# 📊 Previsão de Estoque Inteligente na AWS com [SageMaker Canvas](https://aws.amazon.com/pt/sagemaker/canvas/)

Previsão de Estoque Inteligente na AWS com SageMaker Canvas. Neste Lab DIO, Eu fiz a previsão de estoque com preço variável com inclusão de novos produtos!

## 🎯 Objetivos Deste Desafio de Projeto (Lab)

![image](https://github.com/digitalinnovationone/lab-aws-sagemaker-canvas-estoque/assets/730492/72f5c21f-5562-491e-aa42-2885a3184650)

## 🚀 Passo a Passo

### 1. Selecionar Dataset

-  "dataset-1000-com-preco-variavel-e-renovacao-estoque.csv"

### 2. Construir/Treinar

-  Eu fiz primeiro uma building agrupando por preço, mas os dados não se mostraram fiés para predição. Então deixei com todos os valores, fazendo assim uma análise de produto a produto independente da variação de preço, apenas de acordo com sua quantidade e inclusão nos estoques para até 9 dias! 

### 3. Analisar

-   Métricas de performance do modelo:
    - O preço variável tem um impacto sigificativo na previsão dos estoques, porém como não pude obetr fidelidade para a variação de preço eu segui com a predição de todos os valores por produto sendo assim:
      __- wQL = 0.336 (Apresenta uma boa fidelidade de predições para os 3 cenários P10, P50 e P90);__
      __- MAPE = 1.402 (Apresenta uma taxa de erro relativamente baixa, 1,4% relacionado a demanda real);__
      __- WAPE = 0.540 (Os erros relacionados aos pesos dos alvos mais importantes estão balanceados, garantindo uma boa previsão pelo tempo);__
      __- RMSE = 35.388 (Muito provavelmente devido a variação alta de preços a descrepância entre a predição e os valores reais se tornarão verdadeiros para cada faixa de valor variável);__
      __- MASE = 0.818 (O modelo indica uma melhora significativa na previsão);__

### 4. Prever

-   Predição de estoque por produto:
    -  
