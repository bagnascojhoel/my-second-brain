#aws #development_career #certification
- Sigla para _Identity Access Management_.

# Funcionalidades
-   Controle de acesso a recursos AWS através de usuários, grupos e funções (_roles_). Cada um desses recebe políticas de acesso que definem o que cada um pode utilizar.
-   Habilitar autenticação em múltiplos fatores. Onde, além da senha e nome de usuário, o acesso a conta só é possível com um código aleatório gerado a cada 30s gerado por uma aplicação em outro dispositivo (e.g. _Google Authenticator_). Diminuindo drasticamente o risco de algum invasor malicioso causar problemas com acesso indevido.
-   Acesso a contas AWS através da _Identity Federation_. Pode ser feito um link de contas do Archive Directory da sua empresa ou contas do Facebook, Google. Facilitando o acesso e diminuindo riscos do acesso de usuários a AWS.
-   Permissões extremamente granulares. É possível definir um escopo de permissão onde um usuário pode criar máquinas EC2 apenas do tipo _small_ com até 12G ram e 1TB de armazenamento.
-   _PCI DSS compliance_. Padrão de segurança para compras relacionadas com cartão de crédito.
-   Determinar regras de acesso para serviços ou usuários e grupos através de _Roles_. E.g. o EC2 pode acessar apenas bancos de dados _DynamoDB_.
-   Configuração de regras de senha. Depende muito do segmento em que a conta da AWS irá atuar.

## Criação de usuários

-   Existem dois tipos de acessos:
    -   O acesso programático que gera uma _chave-de-acesso-ID_ e uma _chave-de-acesso-segredo_. Esse tipo de acesso é utilizado para acesso a AWS API, CLI, SDK e outras ferramentas de desenvolvimento — normalmente utilizado para usuários desenvolvedores.
    -   O acesso ao console de gerenciamento AWS gera uma senha de acesso para o painel de controle da conta AWS. Normalmente é utilizada para arquitetos.
    -   Uma mesma conta de usuário pode ter ambos tipos de acesso.
-   Por segurança é ideal que as contas sejam criadas com senhas auto-geradas e, no primeiro acesso, o usuário seja obrigado a trocar de senha.
-   Usuários com acesso programático devem sempre baixar o arquivo de `.csv` para evitar a perda da senha. Se essa senha for perdida o usuário precisará ser removido e recadastrado.

## Criação de grupos

-   Um usuário pode pertencer a múltiplos grupos.
-   É importante documentar a utilização dos grupos para cada função que ele foi concebido. Isso garante que qualquer pessoa possa fazer alterações nos grupos sem depender do criador dos grupos.