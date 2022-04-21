#aws #development_career #certification
### Máquinas Hands On
-   sa-east-1 (São Paulo)
    -   15.228.35.117
    -   29ms
-   us-east-1 (Norte da Virgínia)
    -   54.209.251.97
    -   156ms
-   ap-northeast-1 (Tóquio)
    -   18.176.55.46
    -   307ms

## DNS Records

São registros armazenados dentro do servidor de DNS e atrelados ao domínio.

-   Host A (ou AAAA): indica o endereço de IP ao qual o domínio se refere. Host A é para IPV4 e Host AAAA é para IPV6. É possível definir um para cada prefixo do domínio. E.g. _this-is-jhoel.click_ pode ser diferente de _hi.this-is-jhoel.click_.
-   Alias (CNAME ou Canonical Name): aponta um subdomínio para outro subdomínio. Por exemplo, _ele-e-bom.this-is-jhoel.click_ → _www.this-is-jhoel.click_. Diferente do Host A, o Alias aponta para outro nome, não o IP de um servidor.
-   Mail Exchange (MX): aponta onde está o servidor de e-mail. Aceita múltiplos valores ordenados por prioridades customizadas (o primeiro valor a ser utilizado é o com menor prioridade, seguindo a ordem crescente).
-   Service (SRV): utilizado para disponibilizar informações sobre um serviço. Seguindo um padrão, o subdomínio é utilizado para identificar qual o serviço e o registro possuí informações sobre IP e porta dele. Outras aplicações podem consultar esse registro para descobrir como conectar ao dado serviço.
-   Start Of Authority (SOA): contém informações sobre o registro do domínio. Dentre essas informações está qual é o Name Server a quem o domínio está submetido, email do administrador (se não estiver privado), serial number que indica a versão atual dos registros da zona e intervalo de tempo no qual as informações da zona devem ser atualizadas.
-   ? Name Server (NS): armazena o SOA.
-   Pointer (PTR): oposto do Host A, aponta um nome para dado endereço IP. Utilizado para o reverse lookup.

<aside> 📌 _priority_ é utilizada em um registro com múltiplos apontamentos para que o cliente saiba qual deve tentar chamar primeiro; caso esse servidor falhe em responder, o próximo recebe requisição. A ordem de tentativa é crescente, ou seja, o primeiro apontamento a ser chamado é o que tiver prioridade 0.

</aside>

<aside> 📌 _weight_ é utilizado por Load Balancers para saber como distribuir sua carga.

</aside>

## Routing Policies

### Simple

Dada uma lista de IPs, um item dessa lista é selecionado e enviado para o cliente de forma randômica. Exemplo: se temos um registro de Host A com os IPs `1.1.1.1`, `111.111.111.111` e `222.222.222.222` as requisições para o domínio poderiam ser resolvidas da seguinte maneira:

1.  retornado `111.111.111.111`
2.  retornado `1.1.1.1`
3.  retornado `1.1.1.1`
4.  retornado `222.222.222.222`

### Weighted

Dada uma lista de IPs, o tráfego recebido pelo subdomínio é dividido entre os servidores de acordo com o _weight_ definido para cada um. A proporção de tráfego é calculada utilizando $p = server weight/total weight$.

### Latency

Dada uma lista de IPs. O NS faz um calculo de quanto tempo o cliente levaria para fazer uma requisição até cada um dos servidores listados. Assim, retorna o IP cujo tempo de latência é menor.

### Failover

Definimos dois registros com a Failover Routing Policy para o mesmo subdomínio. Ambas devem ter uma verificação de integridade. Uma será o primário e outra o secundário. O registro secundário será utilizado caso a verificação de integridade do primário dê "Não íntegro".

### Geolocation

Definimos um registro para cada localidade que quisermos. Por exemplo, se queremos que os usuários que estão no Brasil acessem o servidor em São Paulo, criamos um registro com essa regra de roteamento e apontamento. Se não houver uma regra para a sua localização específica, a AWS utiliza o registro com localidade mais próxima a você.

### Geoproximity

Utilizamos outro recurso do Route 53, as Políticas de Tráfego. Com essas políticas de tráfego conseguimos criar regras extremamente complexas de roteamento, mas o custo é elevado. Podemos definir encadeamento de políticas de roteamento utilizado uma ferramenta gráfica.
![[Pasted image 20220215064311.png]]

### Multivalue

Soluciona um problema da Simple Routing. A Simple Routing Policy divide o fluxo de forma randômica. Porém, ela não utiliza por padrão uma verificação de integridade. Se uma das aplicações para a qual ela roteia cai, o Route 53 continua levando tráfego para essa aplicação. A solução para isso é adicionar uma verificação de integridade. Para isso, precisamos substituir o Simple Routing pelo Multivalue Answer Routing; já que o Simple Routing não suporta verificações de integridade.