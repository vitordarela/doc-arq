# Arquitetura Geral - Solução IAM
Uma arquitetura de integração para autenticação de aplicações internas e externas e gestão de contas de usuários deve atender a uma série de requisitos, como centralização da autenticação, segurança aprimorada, interoperabilidade e flexibilidade para integração com diferentes tipos de aplicações.

No diagrama abaixo, é possível evidenciar essas funcionalidades e como o Identity Server (IAM) é responsável por gerir todos os fluxos relacionados à garantia de acesso e segurança das aplicações.

![Exemplo de imagem](../images/ArqGeral.svg)

* **Unifique logins** - Facilitar o logon único (SSO) elimina a necessidade de manter múltiplas credenciais para cada aplicativo, simplificando a vida dos usuários. Isso pode ser realizado utilizando OpenID Connect, OAuth 2.0 e SAML.

* **Dê o acesso certo às pessoas certas** – Controlar o acesso aos aplicativos com base nos níveis de permissão de usuários ou grupos.

* **Aplicar autenticação forte** - Fornecer recursos multifatoriais, como OTP por e-mail, SMS OTP, chaves de acesso FIDO, entre outros. Permitir autenticação adaptativa, o que significa definir o nível de autenticação com base no dispositivo do usuário, localização e contexto de uso.

* **Capacite os usuários a gerenciar suas próprias contas** - Possibilidade de permitir o auto-registro em aplicativos e permitir que os usuários visualizem e gerenciem seus próprios perfis.

* **Gerencie usuários e suas contas** – Controlar todo o gerenciamento do ciclo de vida da identidade da organização. Fornecer usuários para provedores de identidade confiáveis e integrar repositórios de usuários heterogêneos, como LDAP, Active Directory e JDBC.

* **APIs seguras** - Desempenhar um papel fundamental como servidor de autorização que suporta diversos padrões ou perfis relacionados ao OAuth. Oferece suporte a padrões abertos como OAuth, OpenID Connect e SAML 2.0. Garante alta disponibilidade, failover e desempenho para uma operação tranquila.

* **Para proteger os dados do usuário e dar-lhes controle sobre eles** - Permitir registrar, revisar e revogar consentimentos do usuário, aderindo aos princípios de privacidade desde a concepção e aos padrões da indústria impostos pelo GDPR e leis de privacidade semelhantes, como CCPA e LGPD.

Como podemos ver, o Identity Server tem um papel estratégico dentro da organização, o que nos possibilita manter e expandir com segurança todo o nosso parque aplicacional tanto interno como externos garantindo uma exposição para a internet de forma segura e utilizando os principais protocolos de segurança utilizados atualmente. 

O Identity Service ainda nos prove uma flexibilidade de utilizar diferentes padrões e autenticações conforme o cenário aplicacional que tivermos, garantindo assim um crescimento controlado e robustez no nosso controle de utilizadores. 


Avançar > [Aplicações Web - Padrão de Autenticação](WebApps.md)