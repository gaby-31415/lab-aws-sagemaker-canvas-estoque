# 📊 Previsão de Estoque Inteligente na AWS com [SageMaker Canvas](https://aws.amazon.com/pt/sagemaker/canvas/)

O SageMaker Canvas é uma ferramenta da Amazon Web Services (AWS) que permite a criação de modelos de machine learning sem a necessidade de escrever código. Voltado para analistas e profissionais de negócios, o Canvas facilita o desenvolvimento de previsões baseadas em dados usando uma interface visual intuitiva. Ele oferece integração com outras soluções AWS, como o SageMaker, para que usuários possam preparar dados, treinar modelos e gerar previsões de forma simples e eficiente, tudo em um ambiente visual drag-and-drop.

## Usando o Data Wrangler

Nesta tela, iremos preparar os dados que iremos analisar com o Data Wrangler. 

<img width="959" alt="Data flow" src="https://github.com/user-attachments/assets/6d79a2eb-f008-422c-aea6-cdf4bea7da68">

<img width="959" alt="image" src="https://github.com/user-attachments/assets/b287fed0-a1d5-4dcb-9979-e4e2f38ee523">

É possível rodar uma análise da qualidade dos dados inseridos, podendo analisar possíveis duplicações, assim como anomalias em células e colunas antes de prosseguir.
<img width="959" alt="image" src="https://github.com/user-attachments/assets/087979ec-5a3b-4b08-8d26-79efa32dbb15">




### 1. Selecionar Dataset

-   Navegue até a pasta `datasets` deste repositório. Esta pasta contém os datasets que você poderá escolher para treinar e testar seu modelo de ML. Sinta-se à vontade para gerar/enriquecer seus próprios datasets, quanto mais você se engajar, mais relevante esse projeto será em seu portfólio.
-   Escolha o dataset que você usará para treinar seu modelo de previsão de estoque.
-   Faça o upload do dataset no SageMaker Canvas.

### 2. Construir/Treinar

Em nosso caso, iremos analisar a previsão de estoque de acordo com o preço dos produtos
<img width="959" alt="image" src="https://github.com/user-attachments/assets/ef777326-6e9b-433c-8d60-682ed0ab2d2d">

Adicinamos também a variável de feriado, no caso os feriados brasileiros. Mantivemos o modelo de Time & Series forecast, já que queremos analisar dados passados e prever o futuro. 
<img width="950" alt="image" src="https://github.com/user-attachments/assets/8d2df409-26fe-472c-8a08-c17638abb9be">



### 3. Analisar

-   Após o treinamento, examine as métricas de performance do modelo.
-   Verifique as principais características que influenciam as previsões.
-   Faça ajustes no modelo se necessário e re-treine até obter um desempenho satisfatório.
   <<img width="959" alt="image" src="https://github.com/user-attachments/assets/c99b3011-8553-44df-9d99-49a9f8c21c44">



### 4. Prever

-   Use o modelo treinado para fazer previsões de estoque.
-   Exporte os resultados e analise as previsões geradas.
-   Documente suas conclusões e qualquer insight obtido a partir das previsões.

## 🤔 Dúvidas?

Esperamos que esta experiência tenha sido enriquecedora e que você tenha aprendido mais sobre Machine Learning aplicado a problemas reais. Se tiver alguma dúvida, não hesite em abrir uma issue neste repositório ou entrar em contato com a equipe da DIO.
