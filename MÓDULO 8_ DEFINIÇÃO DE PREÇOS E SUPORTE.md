**Nível gratuito da AWS:**

Com o nível gratuito da AWS, você começa a usar determinados serviços sem ter que se preocupar em incorrer em custos durante o período especificado. 

Três tipos de ofertas estão disponíveis: 

- Sempre gratuito:

Essas ofertas não expiram e estão disponíveis para todos os clientes AWS.

Por exemplo, o AWS Lambda permite um milhão de solicitações gratuitas e até 3,2 milhões de segundos de tempo de computação por mês. O Amazon DynamoDB libera 25 GB de armazenamento gratuito por mês.

- 12 meses gratuitos:

Essas ofertas são gratuitas por 12 meses após sua data de inscrição inicial na AWS.

Quantidades específicas de armazenamento comum do Amazon S3, limites para horas mensais de tempo de computação do Amazon EC2 e quantidades de transferência de dados do Amazon CloudFront para fora são alguns exemplos.

- Versão de teste:

As versões de teste gratuitas de curto prazo começam na data em que você ativa determinado serviço. A duração de cada teste pode variar de acordo com o número de dias ou a quantidade de uso do serviço.

Por exemplo, o Amazon Inspector oferece uma versão gratuita de 90 dias. O Amazon Lightsail (um serviço que permite que você execute servidores virtuais privados) oferece 750 horas de uso gratuitas em um período de 30 dias.

**Como funciona a definição de preço da AWS:**

- Pague somente pelo que usar:

Para cada serviço, você paga exatamente a quantidade de recursos que realmente usa, sem exigir contratos de longo prazo ou licenciamento complexo. 

**- Pague menos ao fazer reserva:**

Alguns serviços oferecem opções de reserva com desconto significativo em comparação com as definições de preços da instância sob demanda.

Por exemplo, suponha que sua empresa use instâncias do Amazon EC2 para uma carga de trabalho que precisa ser executada continuamente. Você pode optar por executar essa carga de trabalho no Amazon EC2 Instance Savings Plans, pois o plano permite uma economia de até 72% em relação à capacidade equivalente da instância sob demanda.

**- Pague menos com descontos baseados em volume, quando usar mais (Economia em escala):**

Alguns serviços oferecem definição de preço em camadas, portanto, o custo por unidade é incrementalmente menor com o aumento do uso.

Por exemplo, quanto mais espaço de armazenamento do Amazon S3 você usar, menos pagará por GB.

**Calculadora de preços AWS:**

A calculadora de preços AWS permite explorar os serviços AWS e gerar uma estimativa de custo de seus casos de uso na AWS. Você pode organizar as suas estimativas da AWS por grupos que definir. Um grupo pode refletir como sua empresa está organizada, por exemplo, fornecer estimativas por centro de custo.

Depois de criar uma estimativa, você pode salvá-la e gerar um link para compartilhá-la com outras pessoas.

**Exemplos de definição de preços AWS:**

**- AWS Lambda:**

Para o **AWS Lambda, a cobrança é feita com base no número de solicitações das funções e no tempo necessário para serem executadas.**

O AWS Lambda permite um milhão de solicitações gratuitas e até 3,2 milhões de segundos de tempo de computação por mês.

Você pode economizar nos custos do AWS Lambda inscrevendo-se em um Compute Savings Plan. Um Compute Savings Plan oferece custos de computação mais baixos em troca do compromisso com uma quantidade consistente de uso durante um período de um ou três anos. Este é um exemplo de pagar menos quando há reserva. 

**- Amazon EC2:**

Com o **Amazon EC2, você paga apenas pelo tempo de computação que usar enquanto suas instâncias estão em execução.**

Para algumas cargas de trabalho, você pode reduzir significativamente os custos do Amazon EC2 usando instâncias spot. Por exemplo, suponha que você esteja executando um trabalho de processamento em lote que pode ser interrompido. 

O uso de uma instância spot economizaria até 90% dos custos e, ao mesmo tempo, atenderia aos requisitos de disponibilidade de sua carga de trabalho.

Você pode economizar ainda mais para o Amazon EC2 considerando o Savings Plans e as instâncias reservadas.

**- Amazon S3:**

Para definição de preço do Amazon S3, considere os seguintes componentes de custo:

**- Armazenamento:** 

Você paga apenas pelo armazenamento usado. A taxa de armazenamento de objetos em seus buckets do Amazon S3 é cobrada com base nos tamanhos, classes de armazenamento e quanto tempo você armazenou cada objeto durante o mês.

**- Solicitações e recuperações de dados:** 

Você paga por solicitações feitas aos seus objetos e buckets do Amazon S3. Por exemplo, suponha que você esteja armazenando arquivos de fotos em buckets do Amazon S3 e hospedando-os em um site. Toda vez que um visitante solicita o site que contém esses arquivos de fotos, isso conta para solicitações que você deve pagar.

**- Transferência de dados:** 

Não há custo para transferir dados entre diferentes buckets do Amazon S3 ou do Amazon S3 para outros serviços dentro da mesma Região AWS. No entanto, você paga pelos dados que transfere para dentro e para fora do Amazon S3, com algumas exceções. Não há custo para os dados transferidos para o Amazon S3 a partir da internet ou para o Amazon CloudFront. Também não há custo para os dados transferidos para uma instância do Amazon EC2 na mesma Região AWS que o bucket do Amazon S3.

**- Gerenciamento e replicação:** 

Você paga pelos recursos de gerenciamento de armazenamento que habilitou nos buckets do Amazon S3 da sua conta. Esses recursos incluem inventário, análise e marcação de objetos do Amazon S3.

**- Billing & Cost Management Dashboard ou Painel de cobrança:**

**Consolidated billing ou Faturamento consolidado (AWS Organizations e OU) (Limite máximo de contas e 4):**

Em um módulo anterior, você aprendeu sobre o AWS Organizations, um serviço que permite gerenciar múltiplas contas AWS em um local central. O AWS Organizations também oferece a opção de cobrança consolidada. 

**O recurso de cobrança consolidada do AWS Organizations permite que você receba uma única fatura para todas as contas AWS de sua organização. Ao consolidar, você pode rastrear facilmente os custos combinados de todas as contas vinculadas em sua organização. O número máximo de contas permitido para uma organização é quatro,** mas você pode entrar em contato com o AWS Support para aumentar sua cota, se necessário.

Na sua fatura mensal, você pode revisar os encargos discriminados incorridos por cada conta. Isso permite que você tenha maior transparência nas contas da sua organização, mantendo a conveniência de receber uma única fatura mensal.

**Outro benefício da cobrança consolidada é a capacidade de compartilhar preços de desconto por volume, Savings Plans e instâncias reservadas nas contas da sua organização.** Por exemplo, uma conta pode não ter uso mensal suficiente para se qualificar para preços com desconto. No entanto, quando várias contas são combinadas, o uso agregado pode resultar em um benefício que se aplica a todas as contas na organização.

*Como se fossem contas centralizadas na matriz das filiais.*

*Ganhar em economia do uso em escala, comprar mais e mais barato.*

**Etapa 1:**
![00081cb1ef613fb02905a90e4bf6836b.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/00081cb1ef613fb02905a90e4bf6836b.png)
**Etapa 2:**
![e18e519152a383f0769ca5fd86ba671a.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/e18e519152a383f0769ca5fd86ba671a.png)
**Etapa 3:**
![664e35071bc1a8c9e08ffa236f278f18.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/664e35071bc1a8c9e08ffa236f278f18.png)

**AWS Budgets (Definição de orçamentos personalizados):**

No AWS Budgets, você pode criar orçamentos para planejar o uso do serviço, os custos de serviço e as reservas de instâncias.

As informações do AWS Budgets são atualizadas três vezes por dia. Isso ajuda você a definir com precisão a proximidade entre seu uso e os valores orçados ou limites de nível gratuito da AWS.

No AWS Budgets, você também pode definir alertas personalizados para quando seu uso exceder (ou estiver prestes a exceder) o valor orçado.

![96511c498262978b13a0dfc32f61e18d.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/96511c498262978b13a0dfc32f61e18d.png)

**AWS Cost Explorer:**

O AWS Cost Explorer é uma ferramenta que permite visualizar, interpretar e gerenciar seus custos e uso da AWS ao longo do tempo.

**O AWS Cost Explorer inclui um relatório básico dos custos e do uso dos cinco principais serviços da AWS de acúmulo de custos.** Você pode aplicar filtros e grupos personalizados para analisar seus dados. Por exemplo, você pode exibir o uso de recursos no nível por hora.

![e9dccca72192ce010d43fe2905cf2eb9.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/e9dccca72192ce010d43fe2905cf2eb9.png)

*Uso interessante é usar filtro por TAG,que é usado pelo usuário junto aos recursos, podendo assim filtrar por exemplo por projeto.*

**Planos do AWS Support:**

A AWS oferece quatro planos de suporte diferentes para ajudar você a solucionar problemas, reduzir custos e usar os serviços AWS de forma eficiente. 

Você pode escolher entre os seguintes planos de suporte para atender às necessidades de sua empresa: 

**- Basic, ou Suporte básico:**

- Atendimento ao cliente 24/7,
- Documentação,
- Whitepappers,
- Fóruns de suporte,
- AWS Trusted Advisor (Limitado)
- AWS Pesonal Health Dashboard.

O suporte Basic é gratuito para todos os clientes AWS. Inclui acesso a whitepapers, documentação e comunidades de suporte. Com o suporte Basic, você também pode entrar em contato com a AWS para tratar de questões de cobrança e aumento do limite de serviço

Com ele, você tem acesso a uma seleção limitada de verificações do AWS Trusted Advisor. Além disso, você pode usar o AWS Personal Health Dashboard, uma ferramenta com alertas e orientações de correção quando a AWS enfrenta eventos que podem afetar você. 

Se a sua empresa precisar de suporte além do nível Basic, é possível adquirir os suportes Developer, Business ou Enterprise.

**- Developer, ou Desenvolvedor (Pagamento mensal e não exigem contratos de longo prazo):**

- Acesso por email ao suporte ao cliente (SLA 24 horas),
- Resposta sobre falhas no ambiente (SLA 12 horas).

Os clientes com um plano de suporte Developer têm acesso a recursos como:

- Orientação de práticas recomendadas
- Ferramentas de diagnóstico do lado do cliente
- Suporte à arquitetura de componentes fundamentais, que consiste em orientações sobre como usar as ofertas, recursos e serviços AWS combinados

Por exemplo, suponha que sua empresa esteja explorando os serviços AWS. 

Você já ouviu falar sobre alguns serviços diferentes da AWS. 

No entanto, você não tem certeza de como usá-los combinados para criar aplicativos que possam atender às necessidades de sua empresa. Nesse cenário, o suporte à arquitetura de componentes fundamentais incluído no plano de suporte Developer pode ajudar você a identificar oportunidades para combinar serviços e recursos específicos.

**- Business (Pagamento mensal e não exigem contratos de longo prazo):**

- AWS Trusted Advisor fornece conjunto completo de verificações e boas práticas,
- Acesso direto tefonico ao suporte da equipe técnica AWS (SLA 4 e SLA 1 hora para sistemas parados),
- Gerenciamento de eventos de infraestrutura (Lançamentos de produtos: Tecnicamente e publicidade).

Os clientes com um plano de suporte Business têm acesso a recursos adicionais, incluindo: 

- Orientação de caso de uso para identificar ofertas, recursos e serviços AWS que podem atender melhor às suas necessidades específicas,
- Todas as verificações do AWS Trusted Advisor
- Suporte limitado para software de terceiros, como sistemas operacionais comuns e componentes de pilha de aplicativos.

Suponha que sua empresa tenha o plano de suporte Business e queira instalar um sistema operacional de terceiros comum em suas instâncias do Amazon EC2. 

Você pode entrar em contato com o AWS Support para obter assistência com a instalação, configuração e solução de problemas do sistema operacional. Para tópicos avançados, como otimizar o desempenho, usar scripts personalizados ou resolver problemas de segurança, pode ser necessário entrar em contato diretamente com o provedor de software de terceiros.

**- Enterprise (Pagamento mensal e não exigem contratos de longo prazo):**

- Recomendado para sistemas de missão critica,
- SLA 15 minutos para cargas de trabalho criticas,
- TAM - Technical Account Management dedicado.

Além de todos os recursos incluídos nos planos de suporte Basic, Developer e Business, os clientes com um plano de suporte Enterprise têm acesso a recursos como:

- Orientação de arquitetura de aplicativos, que é um relacionamento consultivo para apoiar casos de uso e aplicativos específicos da sua empresa,
- Gerenciamento de eventos de infraestrutura: engajamento de curto prazo com o AWS Support que ajuda sua empresa a compreender melhor seus casos de uso. Também fornece à sua empresa orientação de arquitetura e scaling.
- Um technical account manager (TAM)

**Technical Account Manager (TAM):**

- Trabalham junto com os clientes tendo como premissa o Well-Architected Framework e seus 5 pilares.

O plano de suporte Enterprise inclui acesso a um technical account manager (TAM).

Se a sua empresa tiver um plano de suporte Enterprise, o TAM será seu principal ponto de contato com a AWS. Ele oferece orientação, revisões de arquitetura e comunicação contínua com sua empresa enquanto você planeja, implanta e otimiza seus aplicativos. 

Seu TAM oferece o conhecimento especializado em toda a gama de serviços AWS. Ele ajuda você a projetar soluções que usam vários serviços combinados de forma eficiente por uma abordagem integrada.

Por exemplo, suponha que você tenha interesse em desenvolver um aplicativo que use vários serviços AWS combinados. O TAM pode fornecer informações sobre como usar melhor os serviços em conjunto. Ele consegue isso ao mesmo tempo em que se alinha com as necessidades específicas que sua empresa espera atender com o novo aplicativo.

**AWS Marketplace:**

O AWS Marketplace é um catálogo digital com milhares de ofertas de fornecedores independentes de software. Você pode usar o AWS Marketplace para encontrar, testar e comprar software que pode ser executado na AWS. 

Para cada oferta no AWS Marketplace, você pode acessar informações detalhadas sobre opções de definição de preço, suporte disponível e avaliações de outros clientes AWS.

Você também pode explorar soluções de software por setor e caso de uso. Por exemplo, suponha que sua empresa atue no setor de saúde. No AWS Marketplace, você pode analisar casos de uso que o software ajuda a resolver, como implementar soluções para proteger prontuários de pacientes, ou usar modelos de machine learning para analisar o histórico médico de um paciente e prever possíveis riscos para a saúde.

![dee9a1c544bfbfddaf45e2802d7d9edb.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/dee9a1c544bfbfddaf45e2802d7d9edb.png)

O AWS Marketplace oferece produtos em várias categorias, como produtos de infraestrutura, aplicativos de negócios, produtos de dados e DevOps.

Em cada categoria, você pode restringir sua pesquisa navegando pelas ofertas de produtos em subcategorias. Por exemplo, as subcategorias na categoria DevOps incluem áreas como Desenvolvimento de aplicativos, Monitoramento e Teste.