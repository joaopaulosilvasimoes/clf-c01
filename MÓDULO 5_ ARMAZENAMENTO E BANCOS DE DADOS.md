**Armazenamento de Blocos:**

![d4d56ceee4572dd85af5a9e7b843dbe9.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/d4d56ceee4572dd85af5a9e7b843dbe9.png)

**- Armazenamento de instâncias (BLOCOS / EFÊMERO):**

Os volumes de armazenamento a nível de bloco se comportam como discos rígidos físicos.

Um armazenamento de instâncias fornece armazenamento temporário a nível de bloco para uma instância do Amazon EC2. 

**Um armazenamento de instância é o armazenamento em disco fisicamente anexo ao computador host para uma instância do EC2 e, portanto, tem a mesma vida útil da instância.** 

Quando a instância é encerrada, todos os dados no armazenamento de instâncias são perdidos.

![57233c0e2c23997188af954d734700be.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/57233c0e2c23997188af954d734700be.png)
![7ea17183e7d7c1b12e51d967585c7ac2.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/7ea17183e7d7c1b12e51d967585c7ac2.png)
![f51a9fc057f50e2f9cc5b61a480e6188.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/f51a9fc057f50e2f9cc5b61a480e6188.png)

**Amazon EBS - Amazon Elastic Block Store (BLOCOS / NÃO EFÊMERO):**

O Amazon Elastic Block Store (Amazon EBS) é um serviço que fornece volumes de armazenamento a nível de bloco que você pode usar com instâncias do Amazon EC2. **Se você interromper ou encerrar uma instância do Amazon EC2, todos os dados no volume do EBS anexo permanecerão disponíveis.**

Para criar um volume do EBS, defina a configuração (como tamanho e tipo do volume) e a provisão. Depois de criar um volume do EBS, ele pode ser anexado a uma instância do Amazon EC2.

Como os volumes do EBS são para dados que precisam perdurar, é importante fazer backup dos dados. Você pode fazer backups complementares de volumes do EBS criando snapshots do Amazon EBS.

![c29777bbe58ecd980288c4c3204e1fda.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/c29777bbe58ecd980288c4c3204e1fda.png)

**- Snapshots do Amazon EBS:**

Um snapshot do EBS é um backup incremental. Isso significa que o primeiro backup de um volume copia todos os dados. Nos backups subsequentes, somente os blocos de dados que foram alterados desde o snapshot mais recente são salvos. 

Os backups complementares são diferentes dos backups completos, nos quais todos os dados em um volume de armazenamento são copiados cada vez que ocorre um backup. O backup completo inclui dados que não foram alterados desde o backup mais recente.

![f0d20d86b046f8cca611312ab897ec0a.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/f0d20d86b046f8cca611312ab897ec0a.png)

**Armazenamento de objetos**

No armazenamento de objetos, cada objeto consiste em dados, metadados e uma chave.

Os dados podem ser uma imagem, vídeo, documento de texto ou qualquer outro tipo de arquivo. Os metadados contêm informações sobre o que são os dados, como eles são usados, o tamanho do objeto e assim por diante. A chave de um objeto é seu identificador exclusivo.

![dbc0f75eb91af8fd622dcbbe36917c21.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/dbc0f75eb91af8fd622dcbbe36917c21.png)

*Lembre-se de que, quando modificar um arquivo no armazenamento de blocos, somente as partes alteradas são atualizadas. Quando um arquivo no armazenamento de objetos é modificado, todo o objeto é atualizado.*

**Amazon S3 - Amazon Simple Storage Service (OBJETOS, Tamanho máximo 5TB):**

O Amazon Simple Storage Service (Amazon S3) é um serviço que fornece armazenamento a nível do objeto. O Amazon S3 armazena dados como objetos em buckets.

É possível fazer upload de qualquer tipo de arquivo para o Amazon S3, como imagens, vídeos, arquivos de texto e assim por diante. Por exemplo, você pode usar o Amazon S3 para armazenar arquivos de backup, arquivos de mídia para um site ou documentos arquivados. O Amazon S3 oferece espaço de armazenamento ilimitado. O tamanho máximo de arquivo para um objeto no Amazon S3 é de 5 TB.

Ao fazer upload de um arquivo para o Amazon S3, é possível definir permissões para controlar a visibilidade e o acesso a ele. Você também pode usar o recurso de versionamento do Amazon S3 para rastrear alterações em seus objetos ao longo do tempo.

**Classes de armazenamento do Amazon S3:**

https://aws.amazon.com/pt/s3/storage-classes/

**- S3 Standard (Min 3 AZs):**

- Projetado para dados acessados com frequência,
- Armazena dados em um mínimo de três Zonas de Disponibilidade.

O S3 Standard fornece alta disponibilidade para objetos. Isso o torna uma boa escolha para diversos casos de uso, como sites, distribuição de conteúdo e análise de dados. O S3 Standard tem um custo mais alto do que outras categorias de armazenamento para dados acessados com pouca frequência e armazenamento de arquivamento.

**- S3 Standard-IA (Infrequent Access) (Min 3 AZs):**

- Ideal para dados com pouca frequência de acesso,
- Semelhante ao S3 Standard, mas com um preço de armazenamento mais baixo e um preço de recuperação mais alto.

O S3 Standard-IA é ideal para dados acessados com pouca frequência, mas que precisam ter alta disponibilidade para quando necessário. 

O S3 Standard e o S3 Standard – IA armazenam dados em um mínimo de três Zonas de Disponibilidade. O S3 Standard – IA fornece o mesmo nível de disponibilidade do S3 Standard, mas com um preço de armazenamento mais baixo e um preço de recuperação mais alto.

**- S3 One Zone - IA (Infrequent Access) (1 AZs):**

- Armazena dados em uma única Zona de Disponibilidade,
- Tem um preço de armazenamento menor do que o S3 Standard – IA.
- 
Comparado com o S3 Standard e o S3 Standard – IA, que armazenam dados em um mínimo de três Zonas de Disponibilidade, o S3 One Zone – IA armazena em uma única Zona de Disponibilidade. 

Isso o torna uma boa categoria de armazenamento nas seguintes condições:

- Você quer economizar custos com armazenamento,
- Você pode reproduzir facilmente seus dados em caso de falha na Zona de Disponibilidade.

**- S3 Intelligent-Tiering:**

- Ideal para dados com padrões de acesso desconhecidos ou em alteração,
**- Requer uma pequena taxa mensal de monitoramento e automação por objeto.**

Na categoria de armazenamento S3 Intelligent-Tiering, o Amazon S3 monitora os padrões de acesso dos objetos. Se você não acessou um objeto por 30 dias consecutivos, o Amazon S3 o move automaticamente para o nível de acesso pouco frequente S3 Standard – IA. 

Se você acessar um objeto no nível de acesso pouco frequente, o Amazon S3 o move automaticamente para o nível de acesso frequente S3 Standard.

`S3 Standard -> (30 Dias sem acesso) -> S3 Standard – IA`

`S3 Standard – IA -> (Acessou objeto) -> S3 Standard`

**- S3 Glacier Flexible Retrieval (Anteriormente S3 Glacier) (Recuperação em minutos ou horas, podendo ser acelerado):**

- Armazenamento de baixo custo projetado para arquivamento de dados,
- Capaz de recuperar objetos em poucos minutos a horas,
- Tempos de recuperação configuráveis, de minutos a horas, com recuperações em massa gratuitas.

O S3 Glacier é uma categoria de armazenamento de baixo custo, ideal para o arquivamento de dados. 

Por exemplo, você pode usar essa categoria para armazenar registros de clientes arquivados ou arquivos de fotos e vídeos mais antigos.

**- S3 Glacier Instant Retrieval (Recuperação imediata):**

A Amazon S3 Glacier Instant Retrieval é uma classe de armazenamento de arquivos que oferece o armazenamento de custo mais baixo para dados de longa duração, que raramente são acessados e exigem recuperação em milissegundos. 

Com a S3 Glacier Instant Retrieval, você pode economizar até 68% nos custos de armazenamento em comparação com o uso da classe de armazenamento S3 Standard-Infrequent Access (S3 Standard-IA), quando seus dados são acessados uma vez por trimestre. A S3 Glacier Instant Retrieval oferece o acesso mais rápido ao armazenamento de arquivo, com a mesma taxa de transferência e acesso em milissegundos que as classes de armazenamento S3 Standard e S3 Standard – IA. 

**- S3 Glacier Deep Archive (Recuperação em até 12 horas, sem aceleração):**

- Categoria de armazenamento de objetos com menor custo, ideal para arquivamento,
- Capaz de recuperar objetos em 12 horas.

A S3 Glacier Deep Archive é a classe de armazenamento mais acessível do Amazon S3 e oferece suporte à retenção e preservação digital de longo prazo para dados que podem ser acessados uma ou duas vezes por ano. 

Essa classe é projetada para clientes que mantêm conjuntos de dados por 7 a 10 anos ou mais para cumprir requisitos de conformidade regulatória, especialmente em setores altamente regulados como serviços financeiros, saúde e setores públicos.

**- S3 no Outposts:**

O Amazon S3 on Outposts oferece armazenamento de objetos para seu ambiente de AWS Outposts on-premises. 

Usando as APIs S3 e os recursos disponíveis nas regiões da AWS hoje, o S3 on Outposts torna mais fácil armazenar e recuperar dados em seu Outpost, bem como proteger os dados, controlar o acesso, marcar e gerar relatórios sobre eles. 

O S3 on Outposts fornece uma única classe de armazenamento Amazon S3, chamada “OUTPOSTS”, que usa as APIs S3 e é projetada para armazenar dados de forma duradoura e redundante em vários dispositivos e servidores em seus Outposts. 

A classe de armazenamento S3 Outposts é ideal para workloads com requisitos de residência de dados locais e para satisfazer as necessidades de desempenho exigentes, mantendo os dados próximos às aplicações on-premises.

**S3 Lifecycle rules:**

https://docs.aws.amazon.com/AmazonS3/latest/userguide/object-lifecycle-mgmt.html

An S3 Lifecycle configuration is an XML file that consists of a set of rules with predefined actions that you want Amazon S3 to perform on objects during their lifetime.

**AWS Backup Vault Lock:**

https://docs.aws.amazon.com/aws-backup/latest/devguide/vault-lock.html

AWS Backup Vault Lock is an optional feature of a backup vault, which can be helpful in giving you additional security and control over your backup vaults.

**WORM (write-once, read-many)** configuration for all the backups you store and create in a backup vault.

*Amazon EBS (BLOCOS) VS Amazon S3 (OBJETOs):*

**Amazon EFS - Amazon Elastic File System (Instâncias Linux):**

O **Amazon Elastic File System (Amazon EFS) é um sistema de arquivos escalável** usado com os serviços de nuvem AWS e recursos locais. À medida que você adiciona e remove arquivos, o Amazon EFS expande e retrai automaticamente. Ele pode dimensionar sob demanda para petabytes sem interromper os aplicativos. 

O Amazon EFS é um serviço regional. **Ele armazena dados em várias Zonas de Disponibilidade e entre elas.** 

O armazenamento duplicado permite que você acesse dados simultaneamente de todas as Zonas de Disponibilidade na Região em que um sistema de arquivos está localizado. 

Além disso, os servidores locais podem acessar o Amazon EFS usando o AWS Direct Connect.

**Bancos de dados relacionais:**

**- Amazon RDS - Amazon Relational Database Service:**

O Amazon Relational Database Service (Amazon RDS) é um serviço que permite executar bancos de dados relacionais na nuvem AWS.

O Amazon RDS é um serviço gerenciado que automatiza tarefas como provisionamento de hardware, configuração de banco de dados, patch e backups. Com esses recursos, você pode passar menos tempo concluindo tarefas administrativas e mais tempo usando dados para inovar seus aplicativos. Você pode integrar o Amazon RDS a outros serviços para atender às suas necessidades de negócios e operacionais, como usar o AWS Lambda para consultar seu banco de dados a partir de um aplicativo sem servidor.

O Amazon RDS fornece inúmeras opções de segurança diferentes. Muitos mecanismos de banco de dados do Amazon RDS oferecem criptografia em repouso (protegendo os dados enquanto estão armazenados) e criptografia em trânsito (protegendo os dados enquanto estão sendo enviados e recebidos).

**- Mecanismos de banco de dados do Amazon RDS:**

O Amazon RDS está disponível em seis mecanismos de banco de dados, que otimizam memória, desempenho ou entrada/saída (E/S). Os mecanismos de banco de dados compatíveis são:

- Amazon Aurora (PostgreSQL e MySQL)
- PostgreSQL
- MySQL
- MariaDB
- Oracle Database
- Microsoft SQL Server

**- Amazon Aurora (6 Copias dos dados em 3 AZs, Serverless):**

O Amazon Aurora é um banco de dados relacional de nível empresarial. É compatível com os bancos de dados relacionais MySQL e PostgreSQL. É até cinco vezes mais rápido do que os bancos de dados MySQL comuns e até três vezes mais rápido do que os bancos de dados PostgreSQL comuns.

O Amazon Aurora ajuda a reduzir os custos do banco de dados reduzindo operações desnecessárias de entrada/saída (E/S), garantindo que os recursos do banco de dados permaneçam confiáveis e disponíveis.

Considere o Amazon Aurora se suas cargas de trabalho exigem alta disponibilidade. **Ele replica seis cópias de seus dados em três Zonas de Disponibilidade e faz backup contínuo de seus dados para o Amazon S3.**

**Bancos de dados não relacional (NoSQL):**

**- Amazon DynamoDB (Serverless):**

- Retundante,
- Escalavel,
- Disponivel,
- Schemaless,
- Chave / Valor,
- Tempo de resposta em milisegundos.

O Amazon DynamoDB é um serviço de banco de dados de chave-valor. 

Ele oferece um desempenho de um dígito de milissegundo em qualquer scaling.

**Serverless:**

O DynamoDB é sem servidor, o que significa que você não precisa provisionar, aplicar patches ou gerenciar servidores. 

Você também não precisa instalar, manter ou operar o software.

**Auto scaling:**

À medida que o tamanho do banco de dados expande ou retrai, o DynamoDB é dimensionado automaticamente para ajustar as alterações na capacidade e, ao mesmo tempo, manter o desempenho consistente. 

Isso o torna uma escolha adequada para casos de uso que exigem alto desempenho durante o scaling.

![8d80f82cda7ca392fa69ec93d958f0e9.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/8d80f82cda7ca392fa69ec93d958f0e9.png)

**Amazon Redshift (Data Warehouse):**

O Amazon Redshift é serviço de data warehouse que você pode usar para análise de big data. 

Ele oferece a capacidade de coletar dados de muitas fontes além de ajudar a entender relações e tendências em todos os seus dados.

**AWS DMS - AWS Database Migration Service:**

O AWS Database Migration Service (AWS DMS) permite migrar bancos de dados relacionais e não relacionais e outros tipos de armazenamentos de dados.

Com o AWS DMS, você move dados entre bancos de dados de origem e de destino. 

Os bancos de dados de origem e de destino podem ser do mesmo tipo ou de tipos diferentes. Durante a migração, o banco de dados de origem permanece operacional, reduzindo o tempo de inatividade em qualquer aplicativo que dependa do banco de dados. 

*O banco de dados de origem permanece totalmente operacional durante a migração, minimizando o tempo de inatividade das aplicações que dependem desse banco de dados.* 

**Migrações homogêneas (Mesmos bancos: Origem = Destino):**

Migrações homogêneas e podem ser do MySQL para o Amazon RDS for MySQL, do Microsoft SQL Server para o Amazon RDS for SQL Server ou até mesmo do Oracle para o Amazon RDS para Oracle. 
 
 O processo é bastante simples porque as estruturas do schema, os tipos de dados e o código de banco de dados é compatível entre a origem e o destino.

**Migrações heterogêneas (Diferentes bancos: Origem <> Destino):**

Migrações heterogêneas e é um processo de **duas etapas**. 

Como as estruturas de schema, o tipo de dados e o código do banco de dados são diferentes entre a origem e o destino, primeiro, precisamos convertê-los usando o **AWS Schema Conversion Tools**. 

Isso converterá o schema de origem e o código para corresponder ao banco de dados de destino. O próximo passo é usar o DNS para migrar os dados do banco de dados de origem para o banco de dados de destino.

*Mas esses não são os únicos casos de uso do AWS DMS.* 

Outros incluem:

**- Migrações de banco de dados de desenvolvimento e teste:** 

Migração de desenvolvimento e teste é quando você deseja desenvolver isso para testar os dados de produção, sem afetar os usuários de produção. Nesse caso, você usa o DMS para migrar uma cópia do banco de dados de produção para seus ambientes de desenvolvimento ou de teste, seja uma única vez ou continuamente.

**- Consolidação de banco de dados:** 

A consolidação de banco de dados é quando você tem vários bancos de dados e quer consolidá-los em um único banco de dados central.

**- Replicação contínua de banco de dados:**

A replicação contínua é quando você usa o DMS para executar a replicação contínua de dados. Pode ser para recuperação de desastre ou por causa da separação geográfica

**Outros serviços de banco de dados:**

**-Amazon DocumentDB (MongoDB):**:

O Amazon DocumentDB é um serviço de banco de dados de documentos compatível com cargas de trabalho do MongoDB. (MongoDB é um programa de banco de dados de documentos.)

**- Amazon Neptune (Grafos):**

O Amazon Neptune é um serviço de banco de dados de grafo.

Você pode usar o Amazon Neptune para criar e executar aplicativos que funcionam com conjuntos de dados altamente conectados, como mecanismos de recomendação, detecção de fraudes e gráficos de conhecimento.

**- Amazon Quantum Ledger Database (Amazon QLDB) (Livro Razão, Imutavel):**

O Amazon Quantum Ledger Database (Amazon QLDB) é um serviço de banco de dados ledger.

Você pode usar o Amazon QLDB para revisar um histórico completo de todas as alterações feitas nos dados do aplicativo.

**- Amazon Managed Blockchain:**

O Amazon Managed Blockchain é um serviço para criar e gerenciar redes de blockchain com estruturas de código aberto.

O Blockchain é um sistema de registro distribuído que permite que várias partes executem transações e compartilhem dados sem uma autoridade central.

**Soluções de Cache e Aceleradores de Bancos de Dados:**

**- Amazon ElastiCache (Redis e Memcached):** 

O Amazon ElastiCache é um serviço que adiciona camadas de cache sobre seus bancos de dados para ajudar a melhorar os tempos de leitura de solicitações comuns.

Ele é compatível com dois tipos de armazenamentos de dados: Redis e Memcached.

**-Amazon DynamoDB Accelerator (DAX):** 

O Amazon DynamoDB Accelerator (DAX) é um cache em memória para o DynamoDB.

Ele ajuda a melhorar os tempos de resposta de milissegundos para microssegundos.