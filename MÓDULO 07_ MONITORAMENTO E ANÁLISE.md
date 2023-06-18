**Monitoramento:**

Coletar métricas, avaliar essas métricas ao longo do tempo e, em seguida, usá-las para tomar decisões.

**Amazon CloudWatch (Monitoramento de Consumo):**

O Amazon CloudWatch é um serviço web que permite monitorar e gerenciar várias métricas e configurar ações de alarme de acordo com os dados dessas métricas.

O CloudWatch usa métricas para representar os pontos de dados para seus recursos. 

Os serviços AWS enviam as métricas ao CloudWatch. Em seguida, o CloudWatch usa essas métricas para criar automaticamente gráficos que mostram como o desempenho mudou ao longo do tempo. 

**- Alarmes do CloudWatch:**

Com o CloudWatch, você pode criar alarmes que executam ações automaticamente se o valor da métrica ultrapassar ou for inferior a um limite predefinido. 

Pode disparar eventos e alarmes, por exemplo SNS.

**- Painel do CloudWatch:**

O recurso de painel do CloudWatch permite que você acesse todas as métricas de seus recursos em um único local. 

Por exemplo, você pode usar um painel do CloudWatch para monitorar a utilização da CPU de uma instância do Amazon EC2, o número total de solicitações feitas para um bucket do Amazon S3 e muito mais. 

Você pode até personalizar painéis separados para diferentes fins comerciais, aplicativos ou recursos.

![ea35e4b3418f05872ea4b605a7caece8.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/ea35e4b3418f05872ea4b605a7caece8.png)

Isso por, sua vez, significa que você pode reduzir o tempo médio de resolução, ou MTTR, e melhorar o custo total de propriedade, ou TCO. Em nossa cafeteria, se o MTTR do horário de limpeza das máquinas do restaurante for mais curto, podemos economizar no TCO com eles.

Você também pode gerar insights para otimizar aplicações e recursos operacionais. Por exemplo, o uso agregado em toda uma frota de instâncias EC2 para derivar em sites operacionais e de utilização.

**AWS CloudTrail (Monitoramento de chamadas API AWS):**

- Serviço de auditoria da API AWS,
- Registros salvos por tempo inderminadado junto ao S3.

O AWS CloudTrail registra as chamadas de API realizadas na sua conta. As informações gravadas são identidade do chamador da API, hora da chamada da API, endereço IP de origem do chamador da API e muito mais. Você pode pensar no CloudTrail como uma “trilha” de migalhas de pão (ou um log de ações) que alguém deixou para trás.

Lembre-se de que você pode usar chamadas de API para provisionar, gerenciar e configurar seus recursos AWS. Com o CloudTrail, você pode visualizar um histórico completo de atividades do usuário e chamadas de API de seus aplicativos e recursos. 

Normalmente, os eventos são atualizados no CloudTrail dentro de 15 minutos após uma chamada de API. Você pode filtrar eventos especificando a hora e a data em que uma chamada de API ocorreu, o usuário que solicitou a ação, o tipo de recurso envolvido na chamada de API e muito mais.

![4b6eb0d27e45d28745fdedcdc476362b.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/4b6eb0d27e45d28745fdedcdc476362b.png)

**- CloudTrail Insights:**

No CloudTrail, você também pode ativar o CloudTrail Insights. 

Esse recurso opcional permite que o CloudTrail detecte automaticamente atividades de API incomuns em sua conta AWS. 

**AWS Trusted Advisor (Monitoramento, consultoria automatizada e recomendações):**

A AWS tem um consultor automatizado chamado AWS Trusted Advisor. 

Esse é um serviço que você pode usar em sua conta da AWS e ele avalia seus recursos em relação a cinco pilares. 

Os pilares são: otimização de custo, performance, segurança tolerância a falhas e limites de serviço. 

O Trusted Advisor executa, em tempo real, uma série de verificações para cada pilar em sua conta, com base nas melhores práticas da AWS. 

Ele compila itens categorizados para você analisar e é possível visualizar diretamente na consola da AWS.
 
Algumas verificações são gratuitas e estão inclusas em sua conta da AWS. Outras estão disponíveis dependendo do seu nível de plano de suporte.

**Pilares/Categorias de avaliação:**

- Otimização de custo (Cost optimization),
- Performance (Performance),
- Segurança (Security),
- Tolerância a falhas (Fault tolerance),
- Limites de serviços (Service limites geralmente são flexiveis e podem ser alterados, ex. conta AWS padrão pode ter até 80 instâncias EC2).

