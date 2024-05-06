# Aplicações Web - Padrão de Autenticação

O padrão de autenticação estabelecido para aplicações web é o **OAuth 2.0 - Authorization Code Flow**.

O Authorization Code Flow é uma escolha popular para aplicações web executadas em um servidor web, pois permite a autenticação segura e confiável do cliente. Esse fluxo exige o uso de um navegador web, uma vez que se baseia em redirecionamentos HTTP.

O processo funciona da seguinte forma:

![Exemplo de imagem](../images/AuthFlow.svg)

1. O cliente inicia o fluxo redirecionando o navegador do usuário para o endpoint de autorização.

2. O usuário é autenticado usando o navegador, e é estabelecido se o usuário concede ou nega a solicitação de acesso do cliente.

3. Se o usuário conceder acesso, o Identity Server redireciona o navegador de volta para o cliente, usando o URI de redirecionamento fornecido anteriormente. O URI de redirecionamento inclui um código de autorização e qualquer estado local fornecido pelo cliente.

4. O cliente solicita um token de acesso ao terminal de token do Identity Server, incluindo o código de autorização recebido na etapa anterior. Se o cliente for confidencial, ele se autentica no Identity Server usando autenticação básica HTTP (com o Client ID como nome de usuário e o Shared Secret como senha). O cliente também inclui o URI de redirecionamento usado para obter o código de autorização para verificação.

5. O Identity Server autentica o cliente, valida o código de autorização e verifica se o URI de redirecionamento corresponde ao URI usado para redirecionar o cliente na etapa 3. Se válido, o Identity Server responde com um token de acesso. O token de acesso pode então ser usado para acessar o recurso desejado.

Após essa autenticação, o token de acesso gerado pode ser usado para chamadas às APIs, garantindo que todas as aplicações possam acessar os recursos necessários dentro de cada domínio responsável.

Esse fluxo também possibilita o recurso de SSO (Single Sign-On), onde, após a autenticação em uma aplicação, o usuário que acessar qualquer outra aplicação conectada ao mesmo Identity Server será autenticado automaticamente com a sessão ativa.

Avançar > [APIs/Serviços - Padrão de Autenticação e Ciclo de Vida das APIs](APIs.md) 