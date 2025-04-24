## Módulo 4

### Finalidade da Camada Física

É na camada física que é estabelecida uma conexão física, seja ela com fio usando um cabo ou sem fio usando ondas de rádio.

No modelo OSI, esta camada fornece os meios para transportar os bits que formam um quadro da camada de enlace no meio físico de rede.

Além disso, são as NICs que conectam um dispositivo à rede. NICs Ethernet são usadas para uma conexão com fio, já NICs WLAN são usadas para sem fio.

### Características da Camada Física

Seus padrões abordam 3 áreas funcionais: componentes físicos, codificação e sinalização.

**Largura de banda:** É a capacidade na qual um meio pode transportar dados.

**Taxa de transferência:** É a medida da transferência de bits pela mídia durante um determinado período de tempo e geralmente é menor que a largura de banda.

**Latência:** Se refere ao tempo necessário para os dados viajarem de um ponto a outro, incluindo atrasos.

**Goodput:** É a medida de dados usáveis transferidos em um determinado período.

A  representação e os agrupamentos de bits para cada tipo de mídia são divididos da seguinte maneira:

* Cabo de cobre \- Os sinais são padrões de pulsos elétricos.
* Cabo de fibra óptica \- Os sinais são padrões de luz.
* Wireless \- Os sinais são padrões de transmissão por microondas.

#### Cabeamento de Cobre

É barato, fácil de instalar e tem baixa resistência à corrente elétrica, entretanto, é limitado pela distância e interferência de sinal que pode ser de duas fontes: EMI e diafonia.

As características elétricas do cabeamento de cobre são definidas pelo IEEE.

Os principais tipos de cabos que são obtidos usando convenções de fiação específicas são Ethernet Straight-through e Ethernet Crossover.
Existem três tipos de cabeamento de cobre, são eles: UTP, STP e cabo coaxial.

- UTP

Tem uma “jaqueta” externa para proteger os fios de cobre contra danos físicos, os pares de fio são torcidos para proteger o sinal de interferência. Além disso, existe um isolamento plástico codificado por cores que isolam eletricamente os fios uns dos outros e identificam cada par.

A Cisco tem um cabo UTP proprietário chamado rollover que conecta uma estação de trabalho a uma porta de console do roteador.

- STP

Usa quatro pares de fios, cada um enrolado em uma blindagem de alumínio, que é enrolada em uma trança ou folha metálica geral.

- Coaxial

Ou coax para abreviar, recebeu seu nome porque tem dois condutores que compartilham o mesmo eixo. É usado para conectar antenas a dispositivos sem fio.

#### Cabeamento em Fibra Óptica

A fibra óptica é um fio flexível, extremamente fino e transparente de vidro muito puro, não muito maior do que um fio de cabelo humano.

É completamente imune a EMI e RFI e transmite dados por longas distâncias e a larguras de banda mais altas do que qualquer outra mídia de rede.

Os cabos de patch de fibra óptica incluem multimodo e monomodo.

Existem quatro tipos de conectores de fibra óptica: ST, SC, LC e LC multimodo duplex.

É utilizado em quatro tipos de indústria: redes empresariais, FTTH, redes de longo curso e redes de cabos submarinos.

#### Mídia sem Fio

Transporta sinais eletromagnéticos que representam os dígitos binários de comunicações de dados usando frequências de rádio ou de micro-ondas.

A rede sem fio tem algumas limitações, incluindo: área de cobertura, interferência, segurança e os problemas que ocorrem com qualquer mídia compartilhada.

Os padrões sem fio incluem o seguinte: Wi-Fi (IEEE 802.11), Bluetooth (IEEE 802.15), WiMAX (IEEE 802.16) e Zigbee (IEEE 802.15.4).

## Módulo 6

### Finalidade da Camada de Enlace de Dados (Data Link)

No modelo OSI, esta camada prepara dados de rede para a rede física.

Esta camada está dividida nas seguintes duas subcamadas: LLC e MAC.

-  Subcamada LLC

Esta subcamada IEEE 802.2 realiza a comunicação entre o software de rede nas camadas superiores e o hardware do dispositivo nas camadas inferiores. Ela coloca a informação no quadro que identifica qual protocolo de camada de rede está sendo usado para o quadro.

- Subcamada MAC

É implementada (IEEE 802.3, 802.11 ou 802.15) no hardware, sendo responsável pelo encapsulamento de dados por meio de delimitação de quadros, endereçamento da camada de enlace, detecção de erros e controle de acesso à mídia.

### Topologias

Existem dois tipos de topologias usadas em redes LAN e WAN são elas: físicas e lógicas.

A camada de enlace de dados “vê” a topologia lógica da rede quando controla o acesso de dados ao meio físico.

Além disso, a topologia lógica influencia o tipo de enquadramento da rede e controle de acesso à mídia usado.

#### Topologias WAN Físicas

Existem 3 tipos comuns, são elas:

* Ponto à Ponto
* Hub e Spoke
* Malha

#### Topologias LAN Físicas

As topologias de LAN físicas incluem: estrela, estrela estendida, barramento e anel.

### Comunicação entre Interfaces

Duas interfaces interconectadas devem usar o mesmo modo duplex ou haverá uma incompatibilidade duplex criando ineficiência e latência no link.

Comunicações Half-duplex trocam dados em uma direção de cada vez.

Full-duplex enviam e recebem dados simultaneamente.

### Métodos de Controle de Acesso para Mídia Compartilhada

Existem dois métodos básicos são eles: acesso baseado em contenção e acesso controlado.

Exemplos de métodos baseados em contenção incluem: CSMA/CD para LANs Ethernet e CSMA/CA para WLANs.

### Quadro Data Link

A camada de link de dados prepara os dados encapsulados, geralmente um pacote IPv4 ou IPv6 para o transporte pela mídia local, encapsulando-o para criar um quadro.

Existem muitos protocolos diferentes que descrevem os quadros da camada de enlace, cada tipo de quadro possui três partes básicas: cabeçalho, dados e trailer.

Os protocolos da camada de link de dados incluem: Ethernet, 802.11 Wireless, PPP, HDLC e Frame Relay.

## Módulo 7

### Quadro Ethernet

Os campos de quadro Ethernet são: preâmbulo e delimitador de quadro inicial, endereço MAC de destino, endereço MAC de origem, EtherType, dados e FCS.

### Endereço MAC Ethernet

É usado para identificar os dispositivos físicos de origem e destino (NICs) no segmento de rede local.

Além disso, fornece um método para identificação do dispositivo na camada de enlace de dados do modelo OSI.

É um endereço de 48 bits expresso usando 12 dígitos hexadecimais ou 6 bytes.

Na Ethernet, são utilizados diferentes endereços MAC para comunicação unicast, broadcast e multicast da Camada 2\.

### A Tabela de Endereços MAC

O switch cria a tabela de endereços MAC dinamicamente examinando o endereço MAC de origem dos quadros recebidos em uma porta.

O switch encaminha quadros procurando uma correspondência entre o endereço MAC de destino no quadro e uma entrada na sua tabela de endereços.

A medida que o switch recebe quadros de dispositivos diferentes, ele é capaz de preencher sua tabela de endereços MAC examinando o endereço MAC de origem de cada quadro.

Quando a tabela de endereços MAC do switch contém o endereço MAC de destino, ele pode filtrar o quadro e encaminhar em uma única porta.

### Métodos de Encaminhamento

Os switches usam um dos seguintes métodos para alternar dados entre portas de rede: Comutação de armazenamento e encaminhamento ou Comutação de corte (cut-through).

Duas variantes de comutação cut-through são:  Fast-forward e Fragment-free.

### Métodos de Armazenamento em Buffer de Memória

Existem dois métodos, sendo eles: Memória baseada em porta e Memória compartilhada.

### Configuração Duplex Ethernet

Existem dois tipos de configurações duplex usadas para comunicações em uma rede Ethernet: full-duplex e half-duplex.

Além disso, existe uma função opcional (Auto-MDIX) encontrada na maioria dos switches Ethernet e das placas de interface de rede (NICs), esta permite que dois dispositivos negociem automaticamente as melhores capacidades de velocidade e duplex.

Quando ativada, o switch detecta automaticamente o tipo de cabo conectado à porta e configura as interfaces de acordo.