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
        - wQL = 0.336 (Apresenta uma boa fidelidade de predições para os 3 cenários P10, P50 e P90);
        - MAPE = 1.402 (Apresenta uma taxa de erro relativamente baixa, 1,4% relacionado a demanda real);
        - WAPE = 0.540 (Os erros relacionados aos pesos dos alvos mais importantes estão balanceados, garantindo uma boa previsão pelo tempo);
        - RMSE = 35.388 (Muito provavelmente devido a variação alta de preços a descrepância entre a predição e os valores reais se tornarão verdadeiros para cada faixa de valor variável);
        - MASE = 0.818 (O modelo indica uma melhora significativa na previsão);

### 4. Prever

-   Predição de estoque por produto:
    -  
Todos os produtos apresentaram valores flutuantes de estoque, a lista a seguir apresenta os picos de entrada dos produtos previsto para os próximos 9 dias:

    - Item 13 = Máxima de 95 em estoque com mínimo no 15 para o último dia seguinte; (80)
    - Item 18 = Variações menores com máxima de 96 em estoque e mínimo de 22; (74)
    - Item 06 = Variações menores com máxima de 96 em estoque e mínimo de 16; (80)
    - Item 07 = Variações menores com máxima de 93 em estoque e mínima de 19; (74)
    - Item 17 = menor 96/13; (83)
    - Item 23 = menor 86/16; (70)
    - Item 03 = menor 89/18; (71)
    - Item 20 = menor 90/14; (76)
    - Item 05 = menor 81/10; (71)
    - Item 14 = 90/13; (77)
    - Item 10 = 92/10; (82)
    - Item 21 = 85/16; (69)
    - Item 16 = 95/10; (85)
    - Item 11 = 86/13; (73)
    - Item 02 = 88/12; (76)
    - Item 24 = otimista 90/13; (77)
    - Item 09 = otimista 90/17; (73)
    - Item 12 = otimista 87/10; (77)
    - Item 25 = menor 86/10; (76)
    - Item 08 = otimista 98/20; (78)
    - Item 22 = otimista 98/21; (77)
    - Item 15 = 95/09; (86)
    - Item 19 = menor 95/20; (75)
    - Item 04 = 90/15; (75)
    - Item 01 = 91/13. (78)

_LEGENDA:_ menor = menor variação a cada dia, otimista = maior entrada e saída de estoque.

_I:_ Item 

_CONCLUSÃO:_ desconsiderando os produtos com menor variação de estoque, temos alguns otimistas que no modelo prevemos que entrem mais produtos pois as saídas também serão maiores (todos com valor da mediana na casa 70+, respectivamente [I24, I09, I12, I08 e I22]). E os com maior mediana de saída I13, I10, I16 com mediana até 85 e no topo o item com maior probabilidade de vendas I04 com mediana de 86.
