# MVP_Engenharia de Dados 

![image](https://github.com/PatriciaSoaresSPereira/mvp/assets/136263539/47488a39-178b-4151-a771-770c8387057f)

**Descrição:**

Esse trabalho, foi construído um pipeline de dados extraído do site da Kaggle, qual a escolha do Dataset: Vendas da Amazon no formato csv, os dados são abertos e a tecnologia na nuvem AWS (Amazon).


**Objetivo:**

Este conjunto de dados consiste em mais de 1.000 produtos reais com seus números de identificação listados no mercado da Amazon, especificamente da região da Índia. Percebi que a região devido à moeda usada no conjunto de dados é a Rupia Índia. Meu objetivo é limpar e preparar os dados porque os dados brutos são muito desorganizados. Em seguida, passarei a encontrar insights sobre os dados e tentarei elaborar na forma de visualização.

1)   Racking de vendas de produtos e subcategoria mais vendidas.
2)   Top dos 5 mais produtos vendidos mais caro com descontos.
3)   Top dos 5 mais produtos mais baratos com descontos.
4)   Quais as classificações dos produtos e subcategoria mais vendidos. 
6)   Avaliação do Feedback do cliente sobre o produto e categoria e os seus sentimentos ao receber a mercadoria a pós-vendas.

   **Detalhamento:**
   
   A escolha do site https://www.kaggle.com/datasets/karkavelrajaj/amazon-sales-dataset em formato cvs, onde os dados são abertos serão analisados na plataforma AWS.
   
   Informação tabela do dataset da Vendas da Amazon.

 **Características**

product_id - ID do produto

product_name - Nome do produto

categoria - Categoria do Produto

desconto_preço - Preço com desconto do produto

actual_price - Preço real do produto

desconto_percentagem - Porcentagem de desconto do produto

rating - Avaliação do Produto

rating_count – Número de pessoas que votaram na classificação da Amazon

about_product - Descrição sobre o produto

user_id - ID do usuário que escreveu a avaliação do produto

user_name - Nome do usuário que escreveu a avaliação do produto

review_id - ID da avaliação do usuário

review_title - Breve revisão

**Coleta:**

![amazon](https://github.com/PatriciaSoaresSPereira/mvp/assets/136263539/797d9176-0186-4b7a-b123-8970df9fc78b)


O Dataset escolhido foi do site Kaggle, Vendas da Amazon e o serviço inserido foi da Plataforma em nuvem da AWs que integra todos os tipos de bancos relacionais e não relacionais e formatos de dados exemplos:csv, json e etc.....

Eu criei um Bucket no S3, com os dados brutos que tem o nome **mvppipeline** está vazio e o glue ele detecta automaticamente os dados do esquema   que são dados pesquisável para utilização, não precisa de servidor e flexivel ao padrão aberto e gera código personalizado que escolhi python.

Eu criei crawler no serviço do Glue e catalogei os dados mvp2, onde será transformado onde é espelhado s3 dados, dei permissão ao ao glue lê da Pasta s3://mvppipeline/amazon.csv ele vai roda quando eu clicar no botão. O esquema, coluna que ele detectar salvará dentro Database que criei.
Eu rodei o Crawler Mvp2 ele detectou o esquema das duas tabelas que criei , que foi catalogado  no data Catalog.
E os dados transformado no s3 foram utilizado e no data catalog e para analisar os dados  e o athena foi feita a analise em notebook na linguagem Python.


![image](https://github.com/PatriciaSoaresSPereira/mvp/assets/136263539/a1ec4548-725b-4520-9291-7d6ea14e9aaf)

Dados baixados para maquina local e inserido manualmente em bucKet do S3.


** Modelagem**

**Carga** 

O ETL foi realizado utilizando o serviço AWS Glue.Através de sua interface visual foram criadas as seguintes etapas:
![image](https://github.com/PatriciaSoaresSPereira/mvp/assets/136263539/a1d423f7-0da3-488c-bc87-a5147ffc4de5)


Na etapa 1, "Data source - S3 bucket" , foram realizada as configurações para extrair (EXtract) os dados da fonte, no caso "amazon_csv"do bucket "mvppipeline".


![image](https://github.com/PatriciaSoaresSPereira/mvp/assets/136263539/5a4b02fc-f85d-472f-b632-160c491ccc69)



Na etapa 2-Data sourde -S3 Bucket", no data catalog para puxar os dados da tabelas no s3.



![image](https://github.com/PatriciaSoaresSPereira/mvp/assets/136263539/92e5a836-f090-45c9-9f2e-44d8c165b9de)


Na etapa3 -  Left Join dos tabelas do dois Bucket S3 .

![image](https://github.com/PatriciaSoaresSPereira/mvp/assets/136263539/2222868d-3ab7-4e53-94d8-c2cfc570708e)

Etapa 4, drop das tabelas dos produto-link,imag-link para a transformação de dados

![image](https://github.com/PatriciaSoaresSPereira/mvp/assets/136263539/3700dade-48e3-45f1-839e-0601eac59fec)

Etapa 5, a execução dos jobs após a configuração no Athena no notebook .

![Screenshot_4](https://github.com/PatriciaSoaresSPereira/mvp/assets/136263539/adcb53fd-78f8-4c71-b6e1-3e0368323d38)



**Analise**

Solução do problema : Fiz no Aws Athena, em notebook na linguagem em Pyhton a analise de dados que deixei no github, nome chamado Amazon. 

![Screenshot_3](https://github.com/PatriciaSoaresSPereira/mvp/assets/136263539/2e919809-c748-4fe7-8723-d68f6b0d72fe)

Em analise da qualidade de cada atributo do conjunto de dados, percebi que não há  problema algum que afeta a predição de dados.

![image](https://github.com/PatriciaSoaresSPereira/mvp/assets/136263539/006ad415-156c-4510-8f4c-5b92a467a73e)

Percebi que no racking das classificações e produtos e categorias as classificações ficam em torno 4,0 e 4,375, sem nunhum produto abaixo das 
expectativas de vendas da classificação de 2,0,demostra que os produtos são boa qualidade, o preço atuais e com descontos são estratégico para 
aumento de vendas das categorias de computadores e eletrônicos são mais vendidos na faixa 3,6 a 4,6 uma margem ideal paa o site da amazon .

![Screenshot_6](https://github.com/PatriciaSoaresSPereira/mvp/assets/136263539/b87633b0-abf8-4b4f-850d-d2cc0a2d6f90)

As preferências das pessoas eletrônicos , computadores e acessórios e casa e cozinha o mais vendidos após os descontos e são mais caros do site
de vendas da Amazon.

![Screenshot_7](https://github.com/PatriciaSoaresSPereira/mvp/assets/136263539/46f56f57-0bad-43f9-a59b-49bd484cbb79)

Produto mais baratos com descontos .

![Screenshot_8](https://github.com/PatriciaSoaresSPereira/mvp/assets/136263539/4405a366-b710-415d-9d78-8dab7f56b7fa)

Usei a tecnica de Linguagem Natural para analisar os sentimentos das Pessoas que receberam em suas casas e empresas 
os produtos vendidos, descontos e a entrega do feedback após as vendas, uma possível compra novamente no site Amazon. 

Depois da analise feita o resultado foram excelente para uma possível compra novamente, a melhoria no atendimento da pós-vendas e a qualidade 
do produto e desconto faz diferença no resultado de crescimento nas vendas on-line do serviço ao cliente.

![Screenshot_9](https://github.com/PatriciaSoaresSPereira/mvp/assets/136263539/6ef28723-f306-4063-bc3f-fff1ab96fed5)



![Screenshot_10](https://github.com/PatriciaSoaresSPereira/mvp/assets/136263539/15b7f056-abb0-4c11-8961-e1041586d3b2)
























