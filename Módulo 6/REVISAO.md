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
