**Modelo de responsabilidade compartilhada:**

Quem é responsável por manter esses recursos seguros: você (o cliente) ou AWS?

A resposta é ambos. Isso é porque você não trata seu ambiente AWS como um único objeto. Em vez disso, você trata o ambiente como uma coleção de partes que se combinam. A AWS é responsável por algumas partes do seu ambiente e você (o cliente) é responsável por outras. Esse conceito é conhecido como modelo de responsabilidade compartilhada.

O modelo de responsabilidade compartilhada divide-se em **responsabilidades do cliente** (comumente chamadas de **“segurança na nuvem”**) e **responsabilidades da AWS** (comumente referidas como **“segurança da nuvem”**).

![739fe757c99898ae1b10c787d98e84fe.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/739fe757c99898ae1b10c787d98e84fe.png)

*Você pode pensar nesse modelo como sendo parecido com a divisão de responsabilidades entre um proprietário e uma construtora. A construtora (AWS) é responsável por edificar sua casa e garantir que ela seja construída com solidez. Como proprietário (o cliente), é sua responsabilidade proteger tudo na casa, garantindo que as portas estejam fechadas e trancadas.*

**Permissões de usuário e acesso:**

**ARN - Amazon Resource Names:**

https://docs.aws.amazon.com/IAM/latest/UserGuide/reference-arns.html

Amazon Resource Names (ARNs) uniquely identify AWS resources. We require an ARN when you need to specify a resource unambiguously across all of AWS, such as in IAM policies, Amazon Relational Database Service (Amazon RDS) tags, and API calls.

**- Usuário-raiz da conta AWS (ROOT):**

Ao criar uma conta AWS pela primeira vez, você começa com uma identidade conhecida como usuário-raiz.

O usuário-raiz é acessado ao entrar com o endereço de e-mail e a senha usados para criar a conta AWS. Pense no usuário-raiz como sendo parecido com o proprietário da cafeteria: ele tem acesso completo a todos os serviços e recursos AWS na conta.

![adec18b91e12d7e45a38be951637d04d.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/adec18b91e12d7e45a38be951637d04d.png)

*Recomendado assim que criar a conta root e configurar o MFA (Multi-factor authentication) e criar um usuário IAM de administração, deste ponto em diante criar os demais.* 

**- IAM - AWS Identity and Access Management:**

O AWS Identity and Access Management (IAM) permite que você gerencie o acesso aos serviços e recursos AWS com segurança.

O IAM oferece a flexibilidade de configurar o acesso com base nas necessidades operacionais e de segurança específicas da sua empresa. Você pode fazer isso usando uma combinação dos recursos do IAM, explorados em detalhes nesta lição:

- Políticas do IAM (Policies and permissions in IAM),
- Usuários IAM (IAM users), 
- Grupos de usuário IAM (IAM user groups),
- Funções do IAM (IAM roles),
- Autenticação multifator (MFA).

*Principio do menor ou minimo privilegio, por padrão um usuário IAM não tem nenhuma permissão de acesso, devendo ser concedido ao mesmo.*

**- Políticas do IAM (Policies and permissions in IAM):**

https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html

Uma políticado IAM é um documento que concede ou nega permissões para serviços e recursos AWS.  

As políticas do IAM permitem que você personalize os níveis de acesso dos usuários aos recursos. Por exemplo, você pode permitir que os usuários acessem todos os buckets do Amazon S3 em sua conta AWS ou apenas um bucket específico.

![f9180445d20a871007efb05ad005e0f3.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/f9180445d20a871007efb05ad005e0f3.png)

*Caso exista conflito de politicas da AWS a mais restritiva (Negativa) será aplicada.*

 **- Usuários IAM (IAM users):**
 
https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users.html
 
 Um usuário do IAM é uma identidade que você cria na AWS. 
 
**Ele representa a pessoa ou o aplicativo** que interage com os serviços e recursos AWS. Consiste em um nome e credenciais.

Por padrão, ao criar um novo usuário do IAM na AWS, não há permissões associadas a ele. Para permitir que o usuário do IAM execute ações específicas na AWS, como iniciar uma instância do Amazon EC2 ou criar um bucket do Amazon S3, você deve conceder ao usuário do IAM as permissões necessárias.

**- Grupos de usuário IAM (IAM user groups):**

https://docs.aws.amazon.com/IAM/latest/UserGuide/id_groups.html

Um grupo do IAM é um conjunto de usuários do IAM. Ao atribuir uma política do IAM a um grupo, todos os usuários do grupo recebem permissões especificadas pela política.

A atribuição de políticas do IAM no nível de grupo também facilita o ajuste de permissões quando um funcionário é transferido para um trabalho diferente.

![aaf8d6ebea36e4387d1e623567cfe7eb.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/aaf8d6ebea36e4387d1e623567cfe7eb.png)

*Um usuário IAM pode estar em mais de um grupo ao mesmo tempo.*

**- Funções do IAM (IAM roles):**

https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html

Uma função do IAM é uma identidade que você pode assumir para obter acesso temporário a permissões.

**Antes que um usuário, aplicativo ou serviço do IAM possa assumir uma função do IAM, ele deve receber permissões para alternar para a função. Quando alguém assume uma função do IAM, ele abandona todas as permissões anteriores que tinha em uma função anterior e assume as permissões da nova função.**

*As funções do IAM são ideais para situações em que o acesso a serviços ou recursos precisa ser concedido **temporariamente**, em vez de a longo prazo.*  

**Autenticação multifator - (MFA - Multi-factor authentication):**

Você já entrou em um site que exigia várias informações para verificar sua identidade? Talvez tenha sido necessário digitar sua senha e, em seguida, uma segunda forma de autenticação, como um código aleatório enviado para o telefone. Esse é um exemplo de autenticação multifator.

No IAM, a autenticação multifator (MFA) fornece uma camada adicional de segurança para sua conta AWS.

**AWS Organizations:**

*Um local central para gestão de multiplas contas AWS.*

Suponha que sua empresa tenha múltiplas contas AWS. Você pode usar o AWS Organizationspara consolidar e gerenciar múltiplas contas AWS em um local central.

Ao criar uma organização, o AWS Organizations cria automaticamente uma raiz, que é o contêiner primário para todas as contas de sua organização. 

**- SCPs - Service Control Policies (OU ou Conta IAM):**

No AWS Organizations, você pode controlar de forma centralizada as permissões para as contas em sua organização usando as políticas de controle de serviço (SCPs). As SCPs permitem que você coloque restrições nos serviços AWS, recursos e ações individuais de API que os usuários e funções em cada conta podem acessar.

**OU - Organizational Units, ou Unidades organizacionais:**

No AWS Organizations, você pode agrupar contas em unidades organizacionais (UO) para facilitar o gerenciamento de contas com requisitos de negócios ou segurança semelhantes. Ao aplicar uma política a uma UO, todas as contas na UO herdam automaticamente as permissões especificadas na política.  

Ao organizar contas separadas em UO, você pode isolar mais facilmente cargas de trabalho ou aplicativos com requisitos de segurança específicos. 

Por exemplo, se sua empresa tiver contas que podem acessar apenas os serviços AWS que atendam a determinados requisitos normativos, você poderá colocar essas contas em uma UO. Em seguida, você pode associar uma política à UO que bloqueia o acesso a todos os outros serviços AWS que não atendam aos requisitos normativos.

![e32c452a264ff8b6c6bcf3e1a4e7eb51.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/e32c452a264ff8b6c6bcf3e1a4e7eb51.png)

**Conformidade:**

https://aws.amazon.com/pt/compliance/customer-center/

O Centro de conformidade para o cliente contém recursos que ajudam você a saber mais sobre a conformidade da AWS.

No Centro de conformidade para o cliente, você pode ler histórias de conformidade dos clientes para descobrir como as empresas de setores regulamentados resolveram vários desafios de conformidade, governança e auditoria.

Você também pode acessar whitepapers e documentação de conformidade sobre tópicos como:

Respostas da AWS aos principais problemas de conformidade
Uma visão geral do risco e da conformidade da AWS.

Uma lista de verificação da segurança de auditoria
Além disso, o Centro de conformidade para o cliente inclui um plano de aprendizagem para auditores. 

Esse plano de aprendizagem foi elaborado para indivíduos em funções jurídicas, de auditoria e de conformidade que desejam saber mais sobre como suas operações internas podem demonstrar conformidade usando a nuvem AWS.

**- AWS Artifact (Segurança da Nuvem AWS):**

O AWS Artifact é sua primeira opção de recurso para informações relacionadas à conformidade que importam para você. Ele fornece acesso sob demanda a relatórios de segurança e conformidade da AWS e ISVs que vendem seus produtos no AWS Marketplace.

Dependendo do setor de sua empresa, talvez seja necessário manter padrões específicos. Uma auditoria ou inspeção assegurará que a empresa cumpriu esses padrões.

O AWS Artifact é um serviço que fornece acesso sob demanda a relatórios de segurança e conformidade da AWS e a contratos on-line selecionados. O AWS Artifact tem duas seções principais: AWS Artifact Agreements e o AWS Artifact Reports.

**- AWS Artifact Agreements:**

Suponha que sua empresa precise assinar um contrato com a AWS em relação ao uso de determinados tipos de informações em todos os serviços AWS. Você pode fazer isso pelo AWS Artifact Agreements.

No **AWS Artifact Agreements, você pode revisar, aceitar e gerenciar contratos para uma conta individual e para todas as suas contas no AWS Organizations.** Diferentes tipos de acordos são oferecidos para atender às necessidades dos clientes sujeitos a regulamentações específicas, como a Lei de Portabilidade e Responsabilidade dos Provedores de Saúde dos EUA (HIPAA).

**- AWS Artifact Reports:**

Suponha que um membro da equipe de desenvolvimento da sua empresa esteja criando um aplicativo e precise de mais informações sobre a responsabilidade em cumprir determinados padrões regulatórios. Você pode recomendar o acesso a essas informações em AWS Artifact Reports.

**O AWS Artifact Reports fornece relatórios de conformidade por auditores terceirizados.** Esses auditores testaram e verificaram se a AWS está em conformidade com diversas normas e regulamentações de segurança globais, regionais e específicas do setor. 

O AWS Artifact Reports se mantém atualizado com os relatórios publicados mais recentes. Você pode fornecer os artefatos de auditoria da AWS aos auditores ou reguladores como evidência dos controles de segurança da AWS.

![7de960b4ddd0b147aa4bccaf437e48db.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/7de960b4ddd0b147aa4bccaf437e48db.png)

**DDoS ou DDoS. Negação de serviço distribuída, Ataques de negação de serviço:**

Um ataque de negação de serviço (DoS) é uma tentativa deliberada de tornar um site ou aplicativo indisponível para os usuários, por meio de sobrecarga.

![85d27bd46009977a78a6bb368ea2d0c6.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/85d27bd46009977a78a6bb368ea2d0c6.png)

**Ataques distribuídos de negação de serviço:**

Em um ataque distribuído de negação de serviço (DDoS), várias fontes são usadas para iniciar um ataque que visa tornar um site ou aplicativo indisponível. O ataque pode ser feito por um grupo de invasores, ou até mesmo um único invasor. O único invasor pode usar vários computadores infectados (também conhecidos como “bots”) para enviar tráfego excessivo a um site ou aplicativo.

Para ajudar a minimizar o efeito de ataques DoS e DDoS em seus aplicativos, você pode usar o **AWS Shield**.

**- AWS Shield:**

**O AWS Shield é um serviço proativo que protege aplicativos contra ataques DDoS.** 

O AWS Shield oferece dois níveis de proteção: 

- AWS Shield Standard:

O AWS Shield Standard protege automaticamente todos os clientes AWS sem nenhum custo. Ele protege seus recursos AWS contra os tipos de ataques DDoS mais comuns e frequentes.

À medida que o tráfego de rede ingressa em seus aplicativos, o AWS Shield Standard usa diversas técnicas de análise para detectar tráfego mal-intencionado em tempo real e mitigá-lo automaticamente.

- AWS Shield Advanced:

O AWS Shield Advanced é um serviço pago que fornece diagnósticos detalhados de ataques e a capacidade de detectar e mitigar ataques elaborados de DDoS.

Ele também se integra a outros serviços, como o Amazon CloudFront, o Amazon Route 53 e o Elastic Load Balancing. Além disso, você pode integrar o AWS Shield ao AWS WAF escrevendo regras personalizadas para mitigar ataques complexos de DDoS.

**- AWS WAF:** 

**O AWS WAF é um firewall de aplicativo web que permite monitorar solicitações de rede que entram em seus aplicativos web.** 

O AWS WAF trabalha em conjunto com o Amazon CloudFront e um balanceador de carga de aplicativo. 

Lembre-se das listas de controle de acesso de 
rede que você aprendeu em um módulo anterior. 

O AWS WAF funciona de forma semelhante para bloquear ou permitir o tráfego. No entanto, ele faz isso usando uma lista de controle de acesso (ACL) da web para proteger seus recursos AWS. 

![13ef3426064a3be40dfb569a68636b10.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/13ef3426064a3be40dfb569a68636b10.png)
![bb1e8e12ad542d85f90737f48176233c.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/bb1e8e12ad542d85f90737f48176233c.png)

***Criptografia em Transito (SSL) vs Criptografica em Descanso (KMS)***

**AWS KMS - AWS Key Management Service:**

O AWS Key Management Service (AWS KMS) permite que você execute operações de criptografia pelo uso de chaves de criptografia. Uma chave de criptografia é uma cadeia aleatória de dígitos usada para bloquear (criptografar) e desbloquear (descriptografar) dados. 

Você pode usar o AWS KMS para criar, gerenciar e usar chaves de criptografia. Você também pode controlar o uso de chaves em uma ampla gama de serviços e em seus aplicativos.

Com o AWS KMS, você pode escolher os níveis específicos de controle de acesso necessários para suas chaves. Por exemplo, você pode especificar quais usuários e funções do IAM podem gerenciar chaves. 

Do mesmo modo, você pode desativar temporariamente as chaves para que não sejam mais usadas. Suas chaves nunca saem do AWS KMS e você está sempre no controle delas.

**Amazon Inspector (Avaliação de vunerabilidades):**

O Amazon Inspector ajuda a melhorar a segurança e a conformidade dos aplicativos executando avaliações de segurança automatizadas. 

Ele verifica os aplicativos quanto a vulnerabilidades de segurança e desvios das práticas recomendadas de segurança, como acesso aberto a instâncias do Amazon EC2 e instalações de versões de software vulneráveis. 

Depois que o Amazon Inspector faz uma avaliação, ele fornece uma lista de descobertas de segurança. 

A lista prioriza por nível de gravidade, com uma descrição detalhada de cada problema de segurança e uma recomendação sobre como corrigi-lo. 

Contudo, a AWS não garante que seguir as recomendações feitas resolverá todos os possíveis problemas de segurança. 

Sob o modelo de responsabilidade compartilhada, os clientes são responsáveis pela segurança de ferramentas, aplicativos e processos executados nos serviços AWS.

**Amazon GuardDuty (Detecção inteligente de ameaças):**

O Amazon GuardDuty é um serviço que fornece detecção inteligente de ameaças para sua infraestrutura e seus recursos AWS. 

Ele identifica ameaças monitorando continuamente a atividade da rede e o comportamento da conta no seu ambiente AWS.

Depois de habilitar o GuardDuty para sua conta AWS, ele começa a monitorar sua atividade de rede e conta. Você não precisa implantar ou gerenciar nenhum outro software de segurança. O GuardDuty analisa continuamente dados de várias fontes da AWS, incluindo logs de fluxo de VPC e logs de DNS. 

Se ele detectar ameaças, você poderá revisar as descobertas detalhadas no AWS Management Console. 

As descobertas incluem etapas recomendadas para a correção. 

![b8c0dd1c791f91c29fa74cd7afe66b69.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/b8c0dd1c791f91c29fa74cd7afe66b69.png)