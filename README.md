# 📊 Previsão de Estoque Inteligente na AWS com [SageMaker Canvas](https://aws.amazon.com/pt/sagemaker/canvas/)

O SageMaker Canvas é uma ferramenta da Amazon Web Services (AWS) que permite a criação de modelos de machine learning sem a necessidade de escrever código. Voltado para analistas e profissionais de negócios, o Canvas facilita o desenvolvimento de previsões baseadas em dados usando uma interface visual intuitiva. Ele oferece integração com outras soluções AWS, como o SageMaker, para que usuários possam preparar dados, treinar modelos e gerar previsões de forma simples e eficiente, tudo em um ambiente visual drag-and-drop.

## Usando o Data Wrangler

Nesta tela, iremos preparar os dados que iremos analisar com o Data Wrangler. 

Aqui inserimos o nosso dataset (utilizamos um arquivo .csv com dados de estoque)

Agora passaremos a nossa planilha por uma avaliação de qualidade de dados, onde também podemos limitar a quantidade de dados a serem analisados.


<img width="959" alt="Data flow" src="https://github.com/user-attachments/assets/6d79a2eb-f008-422c-aea6-cdf4bea7da68">



<img width="959" alt="image" src="https://github.com/user-attachments/assets/b287fed0-a1d5-4dcb-9979-e4e2f38ee523">


É possível rodar uma análise da qualidade dos dados inseridos, onde a ferramenta retorna um feedback acerca dos dados inseridos, assim podendo analisar possíveis duplicações, anomalias em células e colunas antes de prosseguir.

<img width="959" alt="image" src="https://github.com/user-attachments/assets/087979ec-5a3b-4b08-8d26-79efa32dbb15">


É possível, desta tela já seguirmos para a próxima fase de criação do modelo.




### 1. Aba Selecionar Dataset

Nesta aba, caso não tenha utilizado o Data Wrangler para pré analisar e tratar os dados, você pode selecionar um dos datasets disponibilizados pelo SageMaker Canvas para treinar o seu modelo, ou utilizar o seu próprio Dataset, assim utilizando casos reais de sua preferência. 


### 2. Construir/Treinar

Aqui nós podemos utilizar o AutoML para explorar e otimizar automaticamente modelos para casos específicos.

Podemos treinar modelos para regressão, classificação, previsão de séries temporais, processamento de linguagem natural, visão computacional e ajuste fino de modelos de base com apenas alguns cliques.

Em nosso caso, iremos analisar o estoque de acordo com o preço dos produtos.

<img width="959" alt="image" src="https://github.com/user-attachments/assets/ef777326-6e9b-433c-8d60-682ed0ab2d2d">


Adicinamos também uma variável de feriado, no caso os feriados brasileiros. Mantivemos o modelo de Time & Series forecast, já que queremos analisar dados passados e prever o futuro. 

<img width="950" alt="image" src="https://github.com/user-attachments/assets/8d2df409-26fe-472c-8a08-c17638abb9be">


A ferramenta recomenda alguns parâmetros que podem ser alterados conforme necessidade e desejo do usuário.





### 3. Analisar

Após o treinamento, que pode ser rápido (utilizando o quick build) ou mais preciso com um tempo maior para conclusão (standard build) podemos examinar as métricas de performance do nosso modelo criado. 

Aqui também podemos fazer ajustes no modelo criado se necessário e também treiná-lo até obter um desempenho satisfatório.

   <<img width="959" alt="image" src="https://github.com/user-attachments/assets/c99b3011-8553-44df-9d99-49a9f8c21c44">

Após a conclusão da análise, o modelo nos retorna alguns dados de métricas de erro amplamente utilizadas em modelos de Machine Learning e análise de Forecast em geral. 

Algumas definições, resumidamente, das métricas na imagem apresentada: 

- Avg. wQL (Weighted Quantile Loss Média): Avalia a precisão das previsões com base em quantis, ponderando erros de acordo com sua importância. É útil em previsões de séries temporais, especialmente para intervalos de confiança.

- MAPE (Mean Absolute Percentage Error): Mede a precisão das previsões em termos percentuais, calculando a média das diferenças absolutas entre os valores previstos e os reais, divididas pelos valores reais. Expressa o erro como uma porcentagem.

- WAPE (Weighted Absolute Percentage Error): Similar ao MAPE, mas pondera os erros absolutos pelo valor total observado, o que dá uma visão mais balanceada do erro em relação ao tamanho dos dados.

- RMSE (Root Mean Square Error): Mede a precisão das previsões calculando a raiz quadrada da média dos erros quadráticos. Penaliza erros grandes, tornando-o sensível a outliers.

- MASE (Mean Absolute Scaled Error): Compara a precisão de um modelo de previsão com um modelo de referência, como uma previsão ingênua (último valor observado). É escalado, o que permite a comparação entre diferentes séries temporais.


### 4. Prever

Agora já podemos utilizar o modelo gerado para realizar previsões de estoque. 


