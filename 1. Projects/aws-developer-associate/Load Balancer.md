#aws #development_career #certification 
Redirecionam as requisições de acordo com a quantidade de utilização de cada máquina destino. Se existem 3 máquinas rodando a mesma aplicação, o _load balancer_ pode garantir que as requisições que ele receber serão dividias entre as três aplicações.

-   Graças ao cabeçalho `X-Forward-For-Header` que mantém o IP de origem, a aplicação sabe para quem deve enviar a resposta.

# Tipos

-   _Application Load Balancer_: lida com as chamadas de protocolo HTTP e HTTPS (camada de aplicação, 7).
-   _Network Load Balancer_: lida com requisições no nível TCP (camada 4).
-   Classic LB (Elastic Load Balancer): está desuso. É uma mistura pois lida com as camadas 7 e 4, aumentado a chance de ocorrerem problemas.