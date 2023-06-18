**Criação de uma presença global:**

A AWS opera em diversas áreas geográficas diferentes pelo mundo, chamadas regiões.

**Regiões AWS:**

Cada região é isolada geograficamente umas das outras no sentido de que nenhum dado entra ou sai do seu ambiente nessa região sem que você permita isso de forma explícita, sem que você permita que seus dados sejam movidos.

A soberania dos dados em uma localidade faz parte das exigências de arquitetura das regiões da AWS e os dados estão sujeitos a leis e regulamentos locais do país onde está localizada essa região. Então, com esse entendimento de que os seus dados, suas informações e a sua aplicação residem e operam em uma região, uma das primeiras decisões que você precisa tomar é qual região você deve escolher. Há quatro pontos relacionados aos negócios que você deve considerar para escolher uma região:

**- Ponto de número 1 (Conformidade com governança de dados e requisitos legais):** Antes de qualquer um dos outros tópicos, você deve olhar primeiro para os seus requisitos de conformidade. Você tem um requisito de que seus dados devem ser armazenados dentro dos limites do Brasil? Então, você deve escolher a região de São Paulo, ponto. Nenhuma das outras opções deve ser considerada. Ou vamos pensar que você deve rodar a sua aplicação dentro do território chinês. Para isso você deve escolher uma das nossas regiões chinesas. A maioria das empresas, no entanto, não estão debaixo de regulamentos tão rigorosos. Então, se você não tiver um controle de conformidade ou regulações que exijam a escolha de uma região específica você pode considerar outros pontos.

**- Ponto número 2: proximidade (Proximidade com os clientes / Latência):** O mais próximo que você está da sua base de clientes é um fato importante, porque a velocidade da luz ainda é uma das leis do universo. Se a maioria dos seus clientes vive em Cingapura, leve isso em consideração para rodar sua aplicação na região de Cingapura. Agora, você pode rodar isso em Virgínia mas o tempo que vai levar até a informação ser enviada recebida, a conhecida latência entre Estados Unidos e Cingapura sempre será um ponto relevante na sua arquitetura. Agora nós já podemos desenvolver a computação quântica mas as redes quânticas ainda estão a alguns passos de distância. O tempo que a luz leva para viajar ao redor do mundo deve ser sempre considerado. Se estabelecer perto da sua base de clientes normalmente é a decisão mais assertiva.

**- Ponto número 3 (Serviços disponíveis em uma Região):** Às vezes, a região mais próxima pode não ter todos os serviços e funcionalidades da AWS que você precisa. Aqui está uma das coisas bem importantes sobre a AWS. Nós estamos constantemente inovando em prol dos nossos clientes. Todos os anos, a AWS lança milhares de novos recursos e serviços especificamente para responder às solicitações e às necessidades dos clientes. Mas, algumas vezes, esses novos serviços exigem novos equipamentos e hardwares que a AWS precisa construir para tornar esse serviço operacional e, algumas vezes, isso significa que a gente precisa construir e disponibilizar o serviço em uma região de cada vez. Vamos supor que os seus desenvolvedores queriam usar o Amazon Braket, a nossa nova plataforma de computação quântica. Eles têm que rodar essa aplicação nas regiões que já possuem um hardware instalado. Será que podemos esperar que o serviço esteja disponível em todas as regiões? Essa é uma boa expectativa. Mas se você quiser usar ele hoje, esse pode ser o seu ponto decisivo.

**- Ponto número 4 (Definição de preços):** Mesmo quando o hardware é igual de uma região para outra, Alguns locais têm um custo maior para operar. Por exemplo, o Brasil. Atualmente, a estrutura tributária do Brasil é tão grande que gera um custo maior para a AWS operar exatamente os mesmos serviços aqui do que em outros países. Exatamente a mesma carga de trabalho em São Paulo pode ter um custo maior, por exemplo, de 50% a mais do que Oregon, nos Estados Unidos. O preço pode ser determinado por muitos fatores. Então, a AWS tem muitos preços granulares e transparentes, que nós vamos discutir nessa aula. Mas é importante lembrar que cada região tem uma tabela de preços diferente. Então, se o orçamento financeiro é a sua principal preocupação, mesmo que os seus clientes estejam no Brasil, você ainda pode pensar em operar num país diferente. Novamente, se o preço for a sua principal motivação, sua principal decisão.

**Exemplos de região:**
```
US East (N. Virginia)     - us-east-1
US East (Ohio)            - us-east-2
US West (N. California)   - us-west-1
US West (Oregon)          - us-west-2
South America (São Paulo) - sa-east-1
```

*"Uma região é composta por pelo menos 3 AZs"*

**Zonas de Disponibilidade (Availability Zones - AZ)**

Uma Zona de Disponibilidade é um único data center ou um grupo de data centers em uma Região. As Zonas de Disponibilidade estão localizadas a dezenas de quilômetros de distância umas das outras. 

A proximidade é suficiente para haver baixa latência (tempo entre o momento em que o conteúdo foi solicitado e recebido) entre as Zonas de Disponibilidade. 

No entanto, se ocorrer um desastre em uma parte da Região, há distância suficiente para reduzir a chance de que várias Zonas de Disponibilidade sejam afetadas.

**Exemplos de AZs:**
```
US West (N. California)   - us-west-1a
US West (N. California)   - us-west-1b
US West (N. California)   - us-west-1c
```

![59daff465893a55d2e219d03adabde2b.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/59daff465893a55d2e219d03adabde2b.png)

![47ab0b7bcde7c9d9e32c6ade9620843c.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/47ab0b7bcde7c9d9e32c6ade9620843c.png)

*Boa pratica: Implantar a infraestrutura em pelo menos duas Zonas de Disponibilidades (AZs)*

**Serviços regionais, ou serviços de ambito regional:**

São executados em todas as AZs da região.

- ELB - Elastic Load Balance
- Amazon Aurora
- AWS Lambda
- AWS Amplify
- Amazon SQS
- Amazon SNS

https://aws.amazon.com/pt/about-aws/global-infrastructure/regional-product-services/

**Edge Locations, Local de Borda ou Pontos de Presença:**

As Edge Locations, são separadas das regiões.

**- Amazon CloudFront  (CDN - Content Delivery Network, ou rede de fornecimento de conteúdo):**

O **Amazon CloudFront** usa o Edge Location ou Local de Borda para armazenar cópias em cache do seu conteúdo mais próximo dos seus clientes para uma entrega mais rápida.

*"Analogo a uma empresa com matriz e filial"*

**- Amazon Route 53 (DNS - Domain Name System):**

Serviço de DNS.

**- AWS Outposts:**

A AWS basicamente vai instalar e configurar uma mini-região totalmente operacional direto do seu próprio datacenter. Toda responsabilidade e propriedade é da AWS. 

Ela que vai operar e administrar tudo, mas de forma isolada, dentro do seu próprio prédio. 

Não é uma solução que a maioria dos clientes precisa. Mas se você tiver necessidades específicas que podem ser resolvidas apenas mantendo as suas aplicações dentro do seu próprio prédio

**Provisionamento de Recursos e Maneiras de interagir com os serviços AWS:**

Como iteragir com todos esses serviços? E a resposta é: **APIs**. Na AWS, tudo é uma chamada de API. Uma API é uma interface de programação de aplicação. Isso significa que há maneiras pré-determinadas de interagir com o serviço da AWS. E você pode invocar ou chamar essas APIs para provisionar, configurar e gerenciar os seus recursos da AWS.

**- AWS Management Console (WEB):**

É uma interface baseada na web para acessar e gerenciar os serviços AWS. Você pode acessar rapidamente os serviços usados recentemente e pesquisar outros serviços por nome, palavra-chave ou acrônimo. O console inclui assistentes e fluxos de trabalho automatizados que podem simplificar o processo de conclusão de tarefas.

Você também pode usar o aplicativo móvel AWS Console para executar tarefas como monitoramento de recursos, visualização de alarmes e acesso a informações de cobrança. Várias identidades podem permanecer em sessão no aplicativo móvel AWS Console ao mesmo tempo

**- AWS Command Line Interface (AWS CLI):**

O AWS CLI permite que você controle vários serviços AWS diretamente a partir da linha de comando em uma ferramenta. O AWS CLI está disponível para usuários no Windows, macOS e Linux.

Usando o AWS CLI, você pode automatizar as ações que seus serviços e aplicativos executam por scripts. Por exemplo, você pode usar comandos para executar uma instância do Amazon EC2, conectar uma instância do Amazon EC2 a um grupo específico de Auto Scaling e muito mais.

**- Kits de desenvolvimento de software (SDKs)**

Os SDKs facilitam o uso dos serviços AWS por uma API projetada para sua linguagem de programação ou plataforma. Os SDKs permitem que você use serviços AWS com seus aplicativos existentes ou crie aplicativos totalmente novos que serão executados na AWS.

Para ajudar você a começar a usar SDKs, a AWS fornece a documentação e um código de exemplo para cada linguagem de programação compatível. As linguagens de programação compatíveis são C++, Java, .NET e muito mais.

**- AWS Elastic Beanstalk (EC2):**

O AWS Elastic Beanstalk é um serviço que ajuda você a **provisionar ambientes baseados no Amazon EC2.** 

Em vez de clicar pela console ou escrever vários comandos para criar sua rede, instâncias EC2, escalabilidade e os load balances, você vai fornecer o seu código da aplicação com as configurações desejadas no Beanstalk e, em seguida, ele cria o seu ambiente e faz o seu deploy. 

O Elastic Beanstalk também permite salvar as configurações do ambiente para que elas possam ser implantadas novamente. 

O AWS Elastic Beanstalk fornece a conveniência de não ter que provisionar e gerenciar todos esses componentes separadamente e ainda te provê a visibilidade e o controle dos recursos que compõem o seu ambiente. Você irá focar, então, na sua aplicação e não na infraestrutura.

**- AWS CloudFormation (Infrastructure as Code (IaC):**

O AWS CloudFormation é uma ferramenta que trata a infraestrutura como código, permitindo que você defina uma ampla variedade de recursos da AWS usando JSON ou Yaml, chamados de Templates do CloudFormation. 

Um **formato declarativo** como esse permite definir o que você deseja criar sem especificar o passo a passo exatamente de como fazer essa criação. Portanto, o CloudFormation te permite definir o que você deseja e o mecanismo dele vai se preocupar com os detalhes sobre como chamar as APIs para fazer essa criação.

**Também não é limitado apenas para soluções básicas que contemplem instâncias EC2.**

O CloudFormation é compatível com diversos recursos diferentes da AWS, como armazenamento, banco de dados, machine learning e muito mais. Depois de definir os seus recursos em um template do CloudFormation, o serviço vai analisar o template e começar a provisionar todos os recursos que você definiu em paralelo. O CloudFormation gerencia todas as chamadas de API para o back end da AWS para você. Você pode executar o mesmo template do CloudFormation em várias contas ou em várias regiões e ele criará ambientes idênticos em todos eles. Há menos espaço para erro humano uma vez que é um processo totalmente automatizado.

*"Similar ao terraform"*

