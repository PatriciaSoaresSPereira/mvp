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
Eu rodei o Crawler Mvp2 ele detectou o esquema da duas tabelas que criei , que foi catalogado data Catalog.E deixar dados transformado no s3 para ser utlizado 










