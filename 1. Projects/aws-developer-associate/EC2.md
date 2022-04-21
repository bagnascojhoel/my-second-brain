#aws #development_career #certification
-   _Elastic Compute Cloud_ (EC2)
-   Criação de máquinas virtuais customizadas. Essas máquinas podem ter diversos tipos de sistemas operacionais, capacidade de memória ram e processamento. Máquinas de uma mesma conta podem ficar em diferentes servidores, já que isso é tudo gerenciado pela AWS.

# Cobrança

A precificação é feita em **segundos usados**. Ela depende muito dos impostos do local físico onde a máquina está.

-   _On Demand_
    -   Valor cobrado na relação configuração da máquina por tempo utilizado. Quanto mais potente for a máquina virtual, mais caro será o preço por minuto ou segundo.
    -   Ela pode ser criada, iniciada ou parada a qualquer momento.
-   _Reserved_
    -   Uma máquina é contratada por um certo período de tempo. Graças a esse compromisso do contratante com a AWS, o preço diminui bastante em comparação com _On Demand_. Esse preço, porém deve ser pago adiantado.
    -   Não possibilita configuração. Assim, aplicações que precisam de capacidade maior em determinadas etapas do ano, não são recomendadas.
-   _Spot_
    -   Você define uma configuração que precisa e faz um lance (como em um leilão). Se a AWS aceitar esse lance, você paga a máquina de acordo com o preço e recorrência acordados.
-   _Dedicated Hosts_
    -   Você contrata um servidor específico.
    -   Ideal para empresas que precisam de uma segurança extrema.

# Tipos

-   As máquinas EC2 são agrupadas por **objetivo**. Esses grupos são **geral, computação otimizada, memória otimizada, computação acelerada, armazenamento otimizada.**
    -   Instâncias para computação otimizada possuem foco em processadores de alto desempenho.
    -   Instâncias para computação acelerada utilizam também GPUs para processamentos que se beneficiem desses processadores.
-   Elas ainda são classificadas por capacidade de processamento. Essas [classificações](https://aws.amazon.com/ec2/instance-types/) mudam frequentemente.
-   O tipo de instância _Burstable Performance Instance_ possibilita um aumento temporário na capacidade da máquina. Ideal para aplicações que em algumas horas do dia recebem um fluxo maior de requisições; evitando contratar uma máquina maior do que o necessário apenas por algumas horas de alto fluxo.
-   Armazenamento _EBS-Only_ significa que o armazenamento pode ser feito fora da máquina (mas relativamente próximo), com HDD ou SSD. Essa sigla significa _Elastic Block Store_.

# [EBS](https://www.udemy.com/course/certificacao-amazon-aws-certified-developer-associate-2020/learn/lecture/17741452#overview)

-   É o sistema de armazenamento padrão de máquinas EC2.
-   Possui um sistema de redundância de dados em um servidor de outra localidade. Diminuindo as chances de perder dados.

## HDD

-   SC1 (_Cold_): seu design é para massas de trabalho com acesso pouco frequente e é barato. (IOPS/Volume = 250.)
-   ST1 (_Throughtput Optimized_): seu design é para leitura e escrita frequente de dados e é um pouco mais caro que SC1. (IOPS/Volume = 500.)

## SSD

-   GP2 (_General Purpose_): tem boa performance para diversos tamanhos de massas de dados e um preço elevado, porém inferior ao IO1. (IOPS/Volume = 16.000.)
-   IO1 armazenamento acessível em alta performance, com preço elevado. (IOPS/Volume = 64.000).