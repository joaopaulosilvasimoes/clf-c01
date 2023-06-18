**VPC - Amazon Virtual Private Cloud:**

Uma VPC, Virtual Private Cloud, é o serviço que você utiliza para criar a sua própria rede privada na AWS.

O Amazon VPC permite que você provisione uma seção isolada da nuvem AWS. Nessa seção isolada, você pode executar os recursos em uma rede virtual que definir. Em uma Virtual Private Cloud (VPC), você pode organizar seus recursos em sub-redes. **Uma sub-rede é uma seção de uma VPC** que pode conter recursos como instâncias do Amazon EC2.

Normalmente, para serviços de back end, como banco de dados ou serviços de aplicação. Os agrupamentos **públicos** e **privados** são recursos conhecidos como **sub-redes** e são intervalos de endereços IPs em sua VPC.

*"Uma subnet está em uma VPC, e uma VPC é composta por subnets"*

"Limite regional em 5."

**Internet Gateway (IGW) (Públicos, usa internet, Não é um Firewall):**

Para permitir a comunicação de tráfego que vem da internet para sua VPC, você deve associar um recurso que chamamos de internet Gateway, ou GW, a sua VPC

Sem ele, ninguém poderia alcançar os recursos que estão dentro da sua VPC.

![1a942e187b0035d45d527a2ce2573e86.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/1a942e187b0035d45d527a2ce2573e86.png)

**Virtual Private Gateway (Privados, conexão via VPN, porém ainda usa internet):**

Gateway privado, que vai permitir somente a entrada de pessoas que estiverem vindo de uma rede privada, não da Internet pública. 

Esse Gateway privado é chamado de Virtual Private Gateway, que é um recurso que permite que você crie uma conexão **VPN (Virtual Private Network)** entre uma rede privada que pode ser, por exemplo, seu data center ou uma rede corporativa interna com sua VPC.

![855b2c74fc0741188747fec3ea7ca768.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/855b2c74fc0741188747fec3ea7ca768.png)

**AWS Direct Connect (Privados, conexão direta, sem usar a internet):**

O Direct Connect permite estabelecer uma conexão utilizando fibra dedicada completamente privada entre o seu datacenter e a AWS. 

Você pode trabalhar com um parceiro do Direct Connect em sua área para estabelecer essa conexão.

Isso pode ajudar você a atender às necessidades regulamentares e de conformidade bem como contornar potenciais problemas de largura de banda. 

![4c51856fc4afe76714a02ac545f1a58e.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/4c51856fc4afe76714a02ac545f1a58e.png)

*É importante observar que o meu VPC pode ter vários tipos de gateways associados a vários tipos de recursos, todos residentes na mesma VPC, mas em **subnets diferentes***

**Subnet ou Sub-redes:**

Uma sub-rede é uma seção de uma VPC na qual você pode agrupar recursos com base em necessidades operacionais ou de segurança. As sub-redes podem ser públicas ou privadas.

**- Sub-redes públicas:** Contêm recursos que precisam ser acessíveis ao público, como o site de uma loja on-line.

**- Sub-redes privadas:** Contêm recursos que devem ser acessíveis apenas pela sua rede privada, como um banco de dados contendo informações pessoais dos clientes e históricos de pedidos.

Em uma VPC, as sub-redes podem se comunicar entre si. Por exemplo, um aplicativo que envolve instâncias do Amazon EC2 em uma sub-rede pública que se comunicam com bancos de dados localizados em uma sub-rede privada.

**Tráfego de rede em uma VPC**

Quando um cliente solicita dados de um aplicativo hospedado na nuvem AWS, essa solicitação é enviada como um pacote. Um pacote é uma unidade de dados enviada pela internet ou por uma rede.

**Ele entra em uma VPC por um gateway da internet. Antes de um pacote poder entrar em uma sub-rede ou sair de uma sub-rede, ele verifica se há permissões.** Essas permissões indicam quem enviou o pacote e como ele tenta se comunicar com os recursos em uma sub-rede.

O componente da VPC que verifica as permissões de pacotes para sub-redes é uma lista de controle de acesso (ACL) de rede.

**- Network Access control List (ACL) ou Lista de Controle de Acesso de Rede:**

Uma lista de controle de acesso (ACL) de rede é um **firewall virtual** que controla o tráfego de entrada e saída no nível de sub-rede.

![1d141073a6d2e0c3c1a4e20f24b670f7.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/1d141073a6d2e0c3c1a4e20f24b670f7.png)

**Por padrão, a ACL de rede comum da conta permite todo o tráfego de entrada e saída**, mas você pode modificá-la adicionando suas próprias regras. 

Para ACLs de rede personalizadas, todo o tráfego de entrada e saída é negado até que você adicione regras para especificar qual tráfego permitir. Além disso, todas as ACLs de rede têm uma regra de negação explícita. Essa regra garante que, se um pacote não corresponder a nenhuma das outras regras na lista, ele será negado. 

**Filtragem de pacotes stateless**

As ACLs de rede executam a filtragem de pacotes stateless. Elas não se lembram de nada e verificam os pacotes que atravessam a fronteira da sub-rede em todos os sentidos: entrada e saída.

![3ad02def1a1dfb10a40146bdb3b13db1.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/3ad02def1a1dfb10a40146bdb3b13db1.png)

**-Security Group ou Grupos de segurança:**

Um grupo de segurança é um firewall virtual que controla o tráfego de entrada e saída de uma instância do Amazon EC2 ou recurso.

**Por padrão, um grupo de segurança nega todo o tráfego de entrada e permite todo o tráfego de saída**, mas você pode adicionar regras personalizadas para configurar o tráfego a ser permitido ou negado.

**Filtragem de pacotes stateful**

Os grupos de segurança fazem a filtragem de pacotes stateful. Eles se lembram de decisões anteriores tomadas para pacotes recebidos.

![e0dfd045b1ce2fd8b1fbe798381018aa.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/e0dfd045b1ce2fd8b1fbe798381018aa.png)

**As ACLs de rede e os grupos de segurança permitem que você configure regras personalizadas para o tráfego em sua VPC. Conforme você aprende mais sobre a segurança e a rede da AWS, verifique se entendeu as diferenças entre ACLs de rede e grupos de segurança.**

![6577df72f569b1261112dde0ad22e2be.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/6577df72f569b1261112dde0ad22e2be.png)

**Redes globais**

**Domain Name System (DNS):**

Os clientes digitam o endereço da web no navegador e podem acessar o site. Isso acontece devido à resolução Domain Name System (DNS). A resolução de DNS envolve um servidor DNS que se comunica com um servidor web.

Você pode pensar no DNS como sendo a lista telefônica da internet. A resolução de DNS é o processo de conversão de um nome de domínio para um endereço IP. 

![e2f5471ae9e0aef71000b386d53c1a4c.png](https://joaopaulosilvasimoes-clf-c01.s3.amazonaws.com/_resources/e2f5471ae9e0aef71000b386d53c1a4c.png)

**Amazon Route 53 (DNS - Domain Name System):**

O Amazon Route 53 é um serviço web de DNS. Oferece aos desenvolvedores e empresas uma maneira confiável de rotear os usuários finais para aplicativos da internet hospedados na AWS.

O Amazon Route 53 conecta solicitações de usuários à infraestrutura em execução na AWS (como instâncias do Amazon EC2 e balanceadores de carga). Ele pode direcionar os usuários para a infraestrutura fora da AWS.

Outro recurso do Route 53 é a capacidade de gerenciar os registros DNS para nomes de domínio. Você pode registrar novos nomes de domínio diretamente no Route 53. Você também pode transferir registros DNS para nomes de domínio existentes gerenciados por outras empresas de registro de domínio. Isso permite que você gerencie todos os seus nomes de domínio em um único local.

O Route 53 pode direcionar tráfego a diferentes endpoints, usando várias políticas de roteamento diferentes como:
	- Roteamento baseado em latência, 
	- DNS de geolocalização, 
	- Geoproximidade,
	- Weighted round robin.

**Amazon CloudFront  (CDN - Content Delivery Network, ou rede de fornecimento de conteúdo):**
	
CDN é uma rede que ajuda a fornecer conteúdo de borda para usuários com base na sua localização geográfica