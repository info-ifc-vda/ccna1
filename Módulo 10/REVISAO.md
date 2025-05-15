## Módulo 8

### Características da Camada de Rede \- Camada 3 do OSI

Fornece serviços para permitir que dispositivos finais troquem dados entre redes. 

Os principais protocolos da camada de rede são: IPv4, IPv6, OSPF e ICMP. 

Esses protocolos executam quatro operações básicas: endereçamento de dispositivos finais, encapsulamento, roteamento e desencapsulamento. 

IPv4 e IPv6 especificam a estrutura de pacotes e o processamento usado para transportar os dados de um host para outro.

Além disso, o IP encapsula o segmento da camada de transporte adicionando um cabeçalho IP, que é examinado por dispositivos da Camada 3, ou seja, roteadores, para entregar o pacote ao host de destino. 

Ademais, o IP é caracterizado como sem conexão, melhor esforço (não confiável) e independente de mídia. 

### Pacote IPv4

Um cabeçalho de pacote IPv4 consiste em campos que contêm informações sobre o pacote. 

Estes campos contêm números binários que identificam várias configurações do pacote IP e são examinados pelo processo da camada 3\.

Os campos do cabeçalho IPv4 incluem:  

* Versão;  
* DS (Serviços Diferenciados);  
* Soma de verificação de cabeçalho;  
* TTL (Tempo de Vida);  
* Protocolo;   
* Endereço IPv4 de origem;  
* Endereço IPV4 de destino.

### Pacote IPv6

Projetado para superar as limitações do IPv4 que incluem: esgotamento de endereços IPv4, falta de conectividade de ponta a ponta e maior complexidade da rede. 

O IPv6 aumenta o espaço de endereço disponível, melhora o manuseio de pacotes e elimina a necessidade de NAT, que é uma forma de vários dispositivos compartilharem um único endereço IPv4 público.

Os campos do cabeçalho IPv6 são: 

* Versão;  
* Classe de tráfego;  
* Rótulo de fluxo;  
* Comprimento da carga útil;  
*  Próximo cabeçalho;  
*  Limite de salto;  
* Endereço IPv6 de origem;  
* Endereço IPv6 de destino.

### Como um host é roteado

Um host pode enviar um pacote para si mesmo, para outro host local e para um host remoto. 

No IPv4, o dispositivo de origem usa sua máscara de sub-rede juntamente com seu endereço IPv4 e o endereço IPv4 de destino para determinar se o host de destino está na mesma rede.

 Já no IPv6, o roteador local anuncia o endereço de rede local (prefixo) para todos os dispositivos na rede, para fazer essa determinação. 

#### Gateway Padrão

É o dispositivo de rede, ou seja, roteador, que pode rotear o tráfego para outras redes.  

Este possui endereço IP local no mesmo intervalo de endereços que outros hosts na rede local. 

O gateway pode aceitar dados na rede local e encaminhar dados para fora desta rede , assim roteando o tráfego para outras redes remotas. 

#### Tabela de Roteamento de um Host

Todos os hosts possuem uma tabela de roteamento que normalmente inclui um gateway padrão. 

No IPv4, o host recebe o endereço IPv4 do gateway padrão dinamicamente via DHCP ou é configurado manualmente. 

Já no IPv6, o roteador anuncia o endereço de gateway padrão ou o host pode ser configurado manualmente. 

Em um host Windows, o comando **route print** ou **netstat \-r** é usado para exibir a tabela de roteamento do host.

### Introdução ao roteamento

Quando um host envia um pacote para outro host, ele consulta sua tabela de roteamento para determinar para onde enviar o pacote. 

Se o host de destino estiver em uma rede remota, o pacote será encaminhado para o gateway padrão, que geralmente é o roteador local. 

#### O que acontece quando um pacote chega na interface do roteador? 

O roteador examina o endereço IP de destino do pacote e pesquisa na sua tabela de roteamento para determinar para onde encaminhar o pacote.

 A tabela de roteamento contém uma lista de todos os endereços de rede conhecidos e para onde encaminhar o pacote. 

Essas entradas são conhecidas como entradas de rota ou rotas. 

O roteador encaminhará o pacote usando a melhor (mais longa) entrada de rota correspondente. 

#### Tipos de Entradas de Rota

A tabela de roteamento de um roteador armazena três tipos, são elas: 

1. Redes conectadas diretamente;  
2. Redes remotas ;  
3. Rota padrão. 

Os roteadores aprendem sobre redes remotas manualmente ou dinamicamente usando um protocolo de roteamento dinâmico, geralmente OSPF ou EIGRP.

Rotas estáticas são entradas de rota configuradas manualmente. As rotas estáticas incluem o endereço de rede remota e o endereço IP do roteador de salto seguinte. 

O comando **show ip route** é usado para exibir a tabela de roteamento IPv4 em um roteador Cisco IOS. 

Fontes comuns de rotas (códigos) incluem:

**L** \- Endereço IP da interface local diretamente conectado;  
**C** \- Rede diretamente conectada;  
**S** \- A rota estática foi configurada manualmente por um administrador;  
**O** \- Abrir caminho mais curto primeiro (OSPF);  
**D** \- Protocolo de roteamento de gateway interno aprimorado (EIGRP).

## Módulo 9

### MAC e IP

Os endereços físicos da camada 2 são usados para entregar o quadro de enlace de dados com o pacote IP encapsulado de uma NIC para outra NIC na mesma rede. 

Se o endereço IP de destino estiver na mesma rede, o endereço MAC de destino será o do dispositivo de destino. 

Quando o endereço IP de destino (IPv4 ou IPv6) estiver em uma rede remota, o endereço MAC de destino será o endereço do gateway padrão do host, ou seja, a interface do roteador.

 Ao longo de cada link em um caminho até o seu destino,  os endereços IP dos pacotes IP são associados aos endereços MAC em um fluxo de dados.

Os responsáveis por esta associação são os protocolos ARP para IPv4 e ND para IPv6.

### ARP

Cada dispositivo IP em uma rede Ethernet tem um endereço MAC exclusivo. 

Quando um dispositivo envia um quadro Ethernet Layer 2, ele contém estes dois endereços: endereço MAC de destino e endereço MAC de origem. 

Um dispositivo usa ARP para determinar o endereço MAC de destino de um dispositivo local quando conhece seu endereço IPv4. 

O ARP fornece duas funções básicas: 

1. Resolver endereços IPv4 para endereços MAC;  
2.  Manter uma tabela de mapeamento de endereços IPv4 para MAC. 

A solicitação ARP é encapsulada em um quadro Ethernet usando essas informações de cabeçalho: 

1. Endereço MAC de origem;  
2. Endereço MAC de destino;  
3. Tipo. 

Somente um dispositivo na LAN terá um endereço IPv4 correspondente ao endereço IPv4 na requisição ARP e portanto, só este dispositivo irá enviar uma resposta que contém os mesmos campos de cabeçalho que a solicitação. 

O dispositivo que enviou originalmente uma requisição ARP receberá a resposta ARP unicast, depois de recebida, o dispositivo adiciona o endereço IPv4 e o endereço MAC correspondente à sua tabela ARP. 

Quando o endereço IPv4 destino não está na mesma rede que o endereço IPv4 origem, o dispositivo de origem precisa enviar o quadro para o gateway padrão. 

Em cada dispositivo, um temporizador da cache ARP remove entradas ARP que não tenham sido usadas durante um determinado período. 

Comandos também podem ser usados para remover manualmente algumas ou todas as entradas na tabela ARP. 

#### Ataque

Como uma solicitação ARP é recebida e processada por todos os dispositivos na rede local podendo causar lentidão na rede, um ator ameaçador pode se aproveitar disso e usar falsificação ARP para realizar um ataque de envenenamento por ARP assim se passando pelo host de destino e conseguindo acessar os dados que estão trafegando na rede.

### Descoberta de vizinhos (ND ou NDP)

O ND fornece serviços de resolução de endereço, descoberta de roteador e redirecionamento para IPv6 usando ICMPv6. 

O ICMPv6 usa cinco mensagens para executar esses serviços, sendo eles: 

1. Solicitação de vizinhos;  
2. Propaganda de vizinhos;  
3. Solicitação de roteador;  
4. Anúncio de roteador;  
5. Redirecionamento.   
   

Assim como ARP para IPv4, os dispositivos IPv6 usam ND para resolver o endereço MAC de um dispositivo para um endereço IPv6 conhecido.

## Módulo 10

### Definir configurações iniciais do roteador

Ao configurar um roteador, devem ser realizadas as seguintes tarefas:

1. Configurar o nome do dispositivo;  
2. Proteger o modo EXEC privilegiado;  
3. Proteger o modo EXEC usuário;  
4. Proteger o acesso remoto Telnet/SSH;  
5. Proteger todas as senhas do arquivo de configuração;  
6. Apresentar a notificação legal;  
7. Salvar a configuração.  
   

### Configurar interfaces

Para que os roteadores estejam acessíveis, as interfaces do roteador também devem estar configuradas. 

O roteador Cisco ISR 4321 está equipado com duas interfaces Gigabit Ethernet: 

1. GigabitEthernet 0/0/0 (G0/0/0);  
2. GigabitEthernet 0/0/1 (G0/0/1). 

Após configurada a interface deve ser ativada através do comando **no shutdown**.

Além disso, a interface também deve ser conectada a outro dispositivo, como switch ou roteador, para que a camada física esteja ativa. 

Para verificar a configuração de uma interface é possível utilizar vários comandos, sendo eles: 

* show ip interface brief;  
* show ipv6 interface brief;  
* show ip route;   
* show ipv6 route;  
* show interfaces;  
* show ip interface;  
* show ipv6 interface.

### Configurar o gateway padrão em um Switch

Para configurar um gateway padrão IPv4 em um switch, use o comando de **ip default-gateway**.

Com esta configuração, é possível gerenciar remotamente o switch de outra rede. 