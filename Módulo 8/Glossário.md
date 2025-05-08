| Sigla / Palavra | Nome Completo em EN | Nome Completo em PT | Conceito |
| :---: | :---: | :---: | ----- |
| Classe de Tráfego | Traffic Class | Classe de Tráfego | É um campo de 8 bits do IPv6, equivalente ao campo Serviços Diferenciados do IPv4. |
| Comprimento da Carga Útil | Payload Length | Comprimento da Carga Útil | Este campo de 16 bits indica o comprimento da parte dos dados ou da carga útil do pacote IPv6.  |
| DS ou DiffServ | Differentiated Services | Serviços Diferenciados | O campo DS é um campo de 8 bits usado para determinar a prioridade de cada pacote. Ademais, este campo está dividido em DSCP e ECN no IPv4. |
| DSCP | Differentiated Services Code Point | Ponto de Código de Serviços Diferenciados | São os seis bits mais significativos do campo DiffServ do IPv4. |
| ECN | Explicit Congestion Notification | Notificação de Congestionamento Explícita | São os dois últimos bits do campo DiffServ do IPv4. |
| EH | Extension Headers | Cabeçalhos de Extensão | Fornecem informações de camada de rede e  ficam posicionados entre o cabeçalho IPv6 e a carga. Além disso, são usados para fragmentação, segurança e suporte à mobilidade. |
| Etiqueta de Fluxo | Flow Label | Etiqueta de Fluxo | Este campo de 20 bits do IPv6 sugere que todos os pacotes com a mesma etiqueta de fluxo recebam o mesmo tipo de manipulação pelos roteadores. |
| Fragmentação de Pacote | Packet Fragmentation | Fragmentação de Pacote | É um processo realizado quando um dispositivo intermediário, geralmente um roteador, deve dividir um pacote IPv4 ao encaminhá-lo de um meio para outro com uma MTU menor. |
| Gateway Padrão  | Default Gateway | Gateway Padrão | É um dispositivo de rede, seja um roteador ou switch de Camada 3 que pode rotear o tráfego para outras redes. |
| ICMP | Internet Control Message Protocol |  Protocolo de Mensagens de Controle da Internet | É um protocolo da camada de rede usado por dispositivos de rede para diagnosticar problemas de comunicação na rede. |
| IHL | Internet Header Length | Comprimento do Cabeçalho da Internet | Este campo descreve o tamanho de um cabeçalho IPv4, este é composto por linhas que possuem 4 bytes de tamanho total. Um cabeçalho padrão contém 5 linhas (20 bytes) e não pode ser menor que isso. |
| Itself | Itself | Si mesmo | Se refere à quando um host pode fazer ping em si mesmo, enviando um pacote para um endereço IPv4 de 127.0.0.1 ou um endereço IPv6 ::1, referido como a interface de loopback que testa a pilha de protocolos do TCP/IP no host. |
| Limite de Salto | Hop Limit | Limite de Salto | Este campo de 8 bits do IPv6 substitui o campo TTL do IPv4, nele o valor limite é subtraído em um por um em cada roteador que encaminha o pacote. |
| MTU | Maximum Transmission Unit | Unidade Máxima de Transmissão | Se refere ao tamanho máximo da PDU que cada meio consegue transportar. |
| Protocolo | Protocol | Protocolo | Este campo é usado para identificar o próximo nível de protocolo e isso é possível através de 8 bits que indicam o tipo de carga de dados que o pacote está carregando, o que permite que a camada de rede transfira os dados para o protocolo apropriado das camadas superiores.  |
| Próximo Cabeçalho | Next Header | Próximo Cabeçalho | Este campo de 8 bits do IPv6 é equivalente ao campo Protocolo do IPv4. Ele exibe o tipo de carga de dados que o pacote está carregando, permitindo que a camada de rede transfira os dados para o protocolo apropriado das camadas superiores. |
| Rota Padrão | Default Route | Rota Padrão | Também chamada de gateway de último recurso, esta é usada quando não há correspondência melhor na tabela de roteamento IP. |
| Salto | Hop | Salto | Como é chamado cada roteador que um pacote atravessa para chegar ao host de destino. |
| TTL |  | Tempo de Vida | É um campo de 8 bits do IPv4 usado para limitar a vida útil de um pacote. Assim, o dispositivo de origem define o valor TTL inicial que é diminuído em um cada vez que o pacote é processado por um roteador e este deve recalcular a soma de verificação do cabeçalho à cada processamento. |
| Versão | Version | Versão | É um campo de 4 bits que identifica se um pacote é IPv4 ou IPv6. |