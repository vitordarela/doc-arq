# APIs/Serviços - Padrão de Autenticação e Ciclo de Vida das APIs

Quando falamos de segurança e padronização dos acessos aos nossos serviços (API), devemos sempre levar em conta uma série de fatores. Para isso, sugerimos a implementação de um API Manager integrado ao Identity Server (como Key Manager), garantindo, além da segurança das APIs, a adição de uma camada de governança para a gestão completa do ciclo de vida das APIs.

![API Manager](/images/APIManagement.svg)

* **O Plano de Gerenciamento (Management Plane)** É no Plano de Gerenciamento que ocorre a criação e o gerenciamento da API. Ele consiste em portais (Publisher, Developer Portal e Service Catalog) para os usuários criarem e gerenciarem APIs, implementarem políticas de limitação de taxa, monitorarem, monetizarem, entre outras atividades. O plano também oferece um conjunto de APIs para interação com ferramentas externas, como o API Controller. Além disso, o Plano de Gerenciamento inclui painéis de análise de API, que exibem diversos insights de negócios.

* **Plano de Dados (Data Plane)** O Plano de Dados é onde a API criada é exposta aos consumidores públicos e atua como proxy para chamadas de API. Isso também fornece recursos adicionais, como aplicação de segurança, limitação de taxa, entre outros.
    * O API Gateway atua como o ponto de entrada para solicitações de API feitas a uma API gerenciada pelo API Manager.

* **Plano de Controle (Control Plane)** O Plano de Controle é onde são tomadas as decisões de validação de segurança da API, geração de chaves de API e limitação de taxa. O Key Manager é o provedor de identidade representado pelo Identity Server e atua como um Serviço de Token Seguro (STS). Ele suporta OAuth 2.0, Autenticação Básica, SSL mútua, bem como mecanismos de autenticação baseados em chave de API.

No diagrama abaixo, podemos ver o fluxo de autenticação e consumo dos serviços, utilizando o Identity Service como Key Manager e fazendo a requisição ao microserviço através do Gateway

![API Flow](/images/APIAuth.svg)

Dessa forma, temos uma arquitetura de gestão e autenticação de todas as nossas APIs, garantindo controle de tráfego para chamadas internas e externas, o que proporciona mais confiabilidade e acesso seguro e escalável.

Com essa arquitetura, os microserviços estão protegidos e só podem ser acessados por meio do API Gateway, que realiza toda a verificação e controle das chamadas conforme as políticas de acesso estabelecidas.

Voltar > [Arquitetura Geral - Solução IAM](Arquitetura.md)