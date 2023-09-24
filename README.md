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
%3CmxGraphModel%3E%3Croot%3E%3CmxCell%20id%3D%220%22%2F%3E%3CmxCell%20id%3D%221%22%20parent%3D%220%22%2F%3E%3CmxCell%20id%3D%222%22%20value%3D%22%22%20style%3D%22rounded%3D0%3BwhiteSpace%3Dwrap%3Bhtml%3D1%3BfillColor%3D%23cce5ff%3BstrokeColor%3D%2336393d%3B%22%20vertex%3D%221%22%20parent%3D%221%22%3E%3CmxGeometry%20y%3D%2230%22%20width%3D%22800%22%20height%3D%22440%22%20as%3D%22geometry%22%2F%3E%3C%2FmxCell%3E%3C%2Froot%3E%3C%2FmxGraphModel%3E




   

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

![image](https://github.com/PatriciaSoaresSPereira/mvp/assets/136263539/641ef9ba-f201-44a6-89f9-35831bfb4d49)

Criei um S3 Bucket com o nome mvppipeline, fiz um upload do arquivo da **amazon_csv** os dados brutos antes de ser transformados .







