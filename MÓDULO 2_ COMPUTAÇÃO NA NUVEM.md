**EC2 - Amazon Elastic Compute Cloud**

Instâncias de EC2 fornecem poder computacional altamente flexível, econômico e rápido.

As instâncias EC2 são executadas em hosts físicos, gerenciados pela AWS, usando tecnologia de virtualização. Quando você lança uma instância EC2, não está necessariamente tomando o host inteiro para si. Em vez disso, você está compartilhando o host com várias outras instâncias, também conhecidos como máquinas virtuais.

E o Hypervisor que está em execução na máquina host é responsável por compartilhar e isolar os recursos físicos subjacentes entre as máquinas virtuais. Essa ideia de compartilhar hardware subjacente é chamada de **Alocação Múltipla**.

Podemos iniciar com um instância pequena, monitorar e entender se essa instância é o suficiente para atender a aplicação que você está executando e, caso seja necessário, você pode aumentar a quantidade de memória e CPU dessa instância. Isso é o que chamamos de Escalabilidade vertical de uma instância.

*"Poder computacional como serviço"*

**Estados**
- STOP : Parado
- TERMINATE : Finalizado/Excluido/Eliminado

**Sistemas Operacionais:**
- WINDOWS
- LINUX

**1 - Tipos ou Familias de Instância EC2 (ESCOPO DE ZONA DE DISPONIBILIDADE - AZ:**

**- Instâncias de uso geral (EQUILIBRADA):** 

Equilibram os recursos de computação, memória e rede. Você pode usá-las para diversas cargas de trabalho, como: servidores de aplicativos, servidores de jogos,
servidores de back-end para aplicativos empresariais e
bancos de dados pequenos e médios.

**- Instâncias otimizadas para computação (CPU):**

São ideais para aplicativos vinculados à computação que se beneficiam de processadores de alto desempenho. Assim como instâncias de uso geral, você pode usar instâncias otimizadas para computação para cargas de trabalho, como: servidores web e aplicativos e de jogos.

**- Instâncias otimizadas para memória (RAM):**

Projetadas para fornecer desempenho rápido para cargas de trabalho que processam grandes conjuntos de dados na memória. Na computação, a memória é uma área de armazenamento temporário, Você pode usá-las para diversas cargas de trabalho, como: bancos de dados de alto desempenho, machine learn.

**- Instâncias de computação acelerada (GPU):**

Usam aceleradores de hardware, ou coprocessadores, para executar algumas funções de forma mais eficiente do que é possível em um software executado em CPUs. Exemplos dessas funções são cálculos de números com vírgula flutuante, processamento de gráficos e correspondência de padrões de dados.

**- instâncias otimizadas para armazenamento (IOPS):**

São projetadas para cargas de trabalho que exigem alto acesso sequencial de leitura e gravação a grandes conjuntos de dados no armazenamento local. Exemplos de cargas de trabalho adequadas para instâncias otimizadas para armazenamento são sistemas de arquivos distribuídos, aplicativos de data warehouse e sistemas de processamento de transações on-line de alta frequência (OLTP).
Você pode usá-las para diversas cargas de trabalho, como: BI.

**2 - Definição de preço do Amazon EC2:**

**- Instâncias sob demanda (HORA ou SEGUNDO) (Sem compromisso):**

São ideais para cargas de trabalho irregulares de curto prazo que não podem ser interrompidas. Custos antecipados ou contratos mínimos não se aplicam. As instâncias são executadas continuamente até que sejam interrompidas e você paga apenas pelo tempo de computação que usar.

**- Savings Plans do Amazon EC2 / Lambda / Fargate (Até 72% desconto) (Compromisso 1 ou 3 anos):**

Savings Plans do Amazon EC2 são ideais para cargas de trabalho que envolvem uma quantidade consistente de uso de computação em um período de um ou três anos.

Com o Savings Plans do Amazon EC2, você pode reduzir seus custos de computação em até 72% em relação aos custos de instâncias sob demanda.

A AWS oferece Savings Plans para vários serviços computacionais, incluindo o Amazon EC2. O Savings Plans do Amazon EC2 permite reduzir os custos de computação ao haver o compromisso com uma quantidade consistente de uso de computação por um período de um ou três anos. Esse compromisso resulta em economias de até 72% em relação aos custos de instâncias sob demanda.

*"Parque de maquinas"*

*Savings Plans são comprados em um compromisso de dólar por hora, com o menor compromisso possível de US $ 8,760 por ano (isso equivale a 1/10 de um centavo por hora). Anteriormente, as reservas eram compradas com base no custo da instância.*

**- Instâncias reservadas (Até 75% desconto) (Compromisso 1 ou 3 anos):**

Instâncias reservadas são um desconto de cobrança aplicado ao uso de instâncias sob demanda em sua conta. Você pode adquirir instâncias reservadas comuns e instâncias reservadas conversíveis por um período de um ou três anos, e instâncias reservadas agendadas por um período de um ano. Você tem mais economia com a opção de três anos.

***Instâncias reservadas são um desconto aplicado ao uso de instâncias sob demanda em sua conta.** 

Você pode adquirir instâncias reservadas comuns e instâncias reservadas conversíveis por um período de um ou três anos, e instâncias reservadas agendadas por um período de um ano. 

Ao contrário do Savings Plans, as instâncias reservadas não exigem que você se comprometa com uma quantidade consistente de uso de computação pela duração do contrato.*

**- Instâncias spot (Até 90% desconto):**

As instâncias spot são ideais para cargas de trabalho com horários de início e término flexíveis ou que toleram interrupções. Com as instâncias spot, você pode reduzir seus custos de computação em até 90% em relação aos custos de instâncias sob demanda.

Diferentemente do Savings Plans do Amazon EC2, as instâncias spot não exigem contratos ou o compromisso com uma quantidade consistente de uso de computação. 

As instâncias spot são ideais para cargas de trabalho com horários de início e término flexíveis ou que toleram interrupções. As instâncias spot usam a capacidade de computação não utilizada do Amazon EC2 e têm uma economia de até 90% de desconto em relação aos preços das instâncias sob demanda.

"Aviso antes de parada de 2 minutos"

**"- Hosts dedicados (+CAROS):"**

Hosts dedicados são servidores físicos com capacidade de instância do Amazon EC2 totalmente dedicada ao uso do cliente.

Você pode usar suas licenças de software por soquete, por núcleo ou por VM existentes para manter a conformidade da licença. Você pode adquirir hosts dedicados sob demanda e reservas de hosts dedicados. De todas as opções do Amazon EC2 que foram abordadas, os hosts dedicados são os mais caros.

"Usados geralmente por conta de compliances e requisitos legais"

**3 - Scaling do Amazon EC2 (CAPACIDADE COMPUTACIONAL):**

**Escalabilidade:** Envolve começar apenas com os recursos de que você precisa e projetar sua arquitetura para responder automaticamente às alterações de demanda, fazendo aumentos ou reduções.

Podendo ser:

**Vertical:** Adicionando maior capacidade as instâncias.
**Horizontal:** Adicionando mais instâncias para suprir as demandas.

**- Amazon EC2 Auto Scaling (Dinâmico ou Preditivo) (Escalabilidade horizontal automatizada):**

O Amazon EC2 Auto Scaling permite que você adicione ou remova automaticamente instâncias do Amazon EC2 em resposta à alteração da demanda do aplicativo. Ao fazer auto scaling de suas instâncias, aumentando ou reduzindo conforme a necessidade.

**- Scaling dinâmico:**  Responde às alterações na demanda. 
**- Scaling preditivo:** Programa automaticamente o número correto de instância do Amazon EC2 com base na demanda prevista.

**Grupo do Auto Scaling (Instâncias: Mínimo / Desejado / Máximo):**

O Amazon EC2 Auto Scaling usa instâncias do Amazon EC2, você paga apenas pelas instâncias que usar, e somente quando elas forem usadas. Você agora tem uma arquitetura econômica que fornece a melhor experiência do cliente e ao mesmo tempo reduz custos.

**4 - Direcionamento de tráfego com o ELB - Elastic Load Balancing (ESCOPO REGIONAL) (DISTRIBUIÇÃO COMPUTACIONAL):**

Um balanceador de carga é uma aplicação que recebe requisições e faz o encaminhamento para processamento nas respectivas instâncias. 

O Elastic Load Balancing é o serviço AWS que distribui automaticamente o tráfego de entrada de aplicativos entre vários recursos, como instâncias do Amazon EC2.

Um balanceador de carga atua como um ponto único de contato para todo o tráfego da web de entrada no seu grupo do Auto Scaling. Isso significa que, à medida que você adiciona ou remove instâncias do Amazon EC2 em resposta à quantidade de tráfego de entrada, essas solicitações são direcionadas para o balanceador de carga primeiro.

O ELB é escalavel automaticamente, por possuir escopo regional.

*"Como um  anfritrião, ele é um ponto único de entrada, e direciona o trafego para o recurso computacional adequado (EC2, LAMBDA, GRUPO DE AUTO SCALING, etc)"*

![fd3dc98cba5c58948f243a2816681f7c.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/fd3dc98cba5c58948f243a2816681f7c.png)
![018878e6ac8a51b4e0763586ed90701c.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/018878e6ac8a51b4e0763586ed90701c.png)

**5 - Sistema de mensagens e enfileiramento (SNS e SQS):**

**Arquitetura acoplada:** Um traço característico de uma Arquitetura de alto acoplamento é onde, se um único componente falhar ou mdar, ele causa problemas para todos os outros componentes.

**Arquitetura de acoplamento flexível:** Esta é uma arquitetura em que, um componente falhar ele é isolado, e portanto não causará falha em cascata em todo o sistema.

**- SQS - Simple Queue Service (FILA):**

O Amazon Simple Queue Service (Amazon SQS) é um serviço de **enfileiramento de mensagens**. 

Use o Amazon SQS para enviar, armazenar e receber mensagens entre componentes de software, sem perder mensagens ou precisar que outros serviços estejam disponíveis. No Amazon SQS, um aplicativo envia mensagens para uma fila. Um usuário ou serviço recupera uma mensagem da fila, processa-a e a exclui da fila.

**- SNS - Simple Notification Service (PUB / SUB e TOPICOS):**

O Amazon Simple Notification Service (Amazon SNS) é um serviço de **publicação (PUB) e assinatura (SUB)**. Usando **tópicos** do Amazon SNS, um editor publica mensagens para assinantes. Isso se parece com a cafeteria: o operador de caixa entrega os pedidos ao barista que, por sua vez, prepara as bebidas.

No Amazon SNS, os assinantes podem ser servidores web, endereços de e-mail, funções do AWS Lambda ou várias outras opções.

**6 - Outros serviços de computação (LAMBDA):**

**- Computação sem servidor:**

O termo “sem servidor” significa que o código é executado em servidores, sem que você precise provisionar ou gerenciar esses servidores. Com a computação sem servidor, você pode se concentrar na inovação de novos produtos e recursos em vez de manter servidores.

Outro benefício da computação sem servidor é a flexibilidade de dimensionar aplicativos sem servidor automaticamente. A computação sem servidor pode ajustar a capacidade de aplicativos modificando as unidades de consumo, como taxa de transferência e memória.

**AWS Lambda (Min: 3 segundos, Max: 15 minutos):** Acionado a partir de um trigger, gatilho, ou evento, execução para códigos de até 15 minutos, ou seja processamentos de curta duração.

**- Contêineres:**

Os contêineres são uma maneira comum de empacotar códigos, configurações e dependências do aplicativo em um único objeto. Você também pode usar contêineres para processos e fluxos de trabalho nos quais há requisitos essenciais de segurança, confiabilidade e escalabilidade.

Ferramentas de orquestração de contêineres, que ainda precisam de instâncias EC2 para serem executados.

**Amazon ECS - Amazon Elastic Container Service (EC2 / DOCKER):**

O Amazon Elastic Container Service (Amazon ECS) é um sistema de gerenciamento de contêineres altamente dimensionável e de alto desempenho que permite executar e dimensionar aplicativos em contêineres na AWS.

O Amazon ECS é compatível com contêineres Docker. O Docker é uma plataforma de software que permite criar, testar e implantar aplicativos rapidamente. A AWS é compatível com c Docker Community Edition de código aberto e do Docker Enterprise Edition baseado em assinatura. Com o Amazon ECS, você pode usar chamadas de API para iniciar e interromper aplicativos ativados pelo Docker.

**Amazon EKS - Amazon Elastic Kubernetes Service (EC2 / KUBERNETS):**

O Amazon Elastic Kubernetes Service (Amazon EKS) é um serviço totalmente gerenciado que você pode usar para executar o Kubernetes na AWS.

O Kubernetes é um software de código aberto que permite implantar e gerenciar aplicativos em contêineres em grande escala. Uma grande comunidade de voluntários mantém o Kubernetes, e a AWS trabalha ativamente em conjunto com essa comunidade Kubernetes. Conforme novos recursos e funcionalidades são lançados para aplicativos Kubernetes, você pode facilmente aplicar essas atualizações aos aplicativos gerenciados pelo Amazon EKS.

**AWS Fargate (Serverless):**

O AWS Fargate é um mecanismo de computação sem servidor para contêineres. Ele funciona com o Amazon ECS e o Amazon EKS.

Com o AWS Fargate, você não precisa provisionar ou gerenciar servidores. O AWS Fargate gerencia sua infraestrutura de servidor para você. Você pode se concentrar em inovar e desenvolver seus aplicativos, pagando apenas pelos recursos necessários para executar os contêineres.

Pode ser usado para ECS e EKS, porém sem a necessidade de alocar instâncias EC2.


