

| Sigla / Palavra | Nome Completo em EN | Nome Completo em PT | Conceito |
| :---: | :---: | :---: | ----- |
| BIA |  Burned In Address | Endereço Gravado  | É o endereço gravado de fábrica, porque este é codificado na memória ROM na NIC. |
| Comutação Fast-Forward | Fast-Forward Switching | Comutação de Avanço Rápido | Este tipo de comutação oferece o menor nível de latência, pois encaminha imediatamente um pacote depois de ler o endereço de destino, no entanto, alguns pacotes podem ser retransmitidos com erros. |
| Comutação Fragment-Free | Fragment-Free Switching | Comutação sem Fragmentos | Neste tipo de comutação, o switch armazena os primeiros 64 bytes do quadro antes de encaminhar para o destino. O motivo, é que a maioria dos erros e das colisões de rede ocorrem neste espaço e portanto é executada uma pequena verificação para garantir que não ocorra uma colisão antes de encaminhar o quadro.  |
| CSMA/CD | Carrier-Sense Multiple Access with Collision Detection | Acesso Múltiplo com Detecção de Colisão | É um método de acesso baseado em contenção, detecção de múltiplos acessos e detecção de colisão. Ademais, permite que vários dispositivos compartilhem o mesmo meio half-duplex, detectando uma colisão quando mais de um dispositivo tenta transmitir simultaneamente.  |
| Encapsulamento de Dados | Data Encapsulation  | Encapsulamento de Dados | É realizado pela subcamada MAC e inclui: Quadro, Endereçamento e Detecção de Erros. |
| FCS |  Frame Check Sequence | Sequência de Verificação de Quadro | É um campo usado para detectar erros em um quadro e para isso, utiliza uma verificação de redundância cíclica.  |
| MDIX Automático | Automatic Medium-Dependent Interface Crossover | Cruzamento Automático de Interface Dependente do Meio | É um recurso que quando ativado, o switch detecta automaticamente o tipo de cabo conectado à porta e configura as interfaces de acordo.  |
| OUI | Organizationally Unique Identifier | Identificador Exclusivo  Organizacionalmente  | É um código exclusivo de 3 bytes obtido através do registro no IEEE, este é destinado a todos os fornecedores que vendem dispositivos Ethernet. |
| LLDP | Link Layer Discovery Protocol | Protocolo de Descoberta da Camada de Link  | É um protocolo da camada de enlace neutro em relação ao fornecedor, usado para identificar vizinhos em uma LAN IEEE 802, especialmente para a rede Ethernet com fio. |
| ND ou NDP| Neighbour Discovery | Descoberta de Vizinho | É processo que um host de origem usa para determinar o endereço MAC de destino associado a um endereço IPv6. |
| QoS | Quality of Service | Qualidade de Serviço | É um requisito de rede, que tem como premissa priorizar a entrega de conteúdos de vídeo e voz com alta qualidade e confiabilidade, gerenciando congestionamentos que possam vir a acontecer. |
| STP | Spanning Tree Protocol | Spanning Tree Protocol | É um protocolo que impede a formação de loops quando switches ou pontes são interligadas por vários caminhos |
| Switching Cut-Through | Switching Cut-Through | Comutação Direta | Esse método encaminha o quadro antes de ser totalmente recebido, para isso, pelo menos o endereço de destino do quadro deve ser lido. |
| Switching Store-and-Forward | Switching Store-and-Forward | Comutação Armazenar e Encaminhar  | Este método recebe o quadro inteiro e calcula o CRC, se este for válido, o switch procura o endereço de destino e encaminha o quadro para a porta correta. |
| Tabela de Endereços MAC | MAC Address Table | Tabela de Endereços MAC | Também chamada de tabela de memória de conteúdo endereçável (CAM), esta tabela armazena os endereços MAC dos dispositivos conectados a uma rede local. |

