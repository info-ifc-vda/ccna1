## Módulo 11

### Estrutura de endereçamento IPv4

Endereço IPv4 é um endereço hierárquico de 32 bits, composto por uma parte da rede (máscara de sub-rede) e uma parte do host (endereço IPv4 exclusivo).

Os bits na parte de rede do endereço devem ser iguais em todos os dispositivos que residem na mesma rede.

Já os bits na parte de host devem ser exclusivos para identificar um host específico dentro de uma rede.

**Comprimento do prefixo:** É o número de bits definido como 1 na máscara de sub-rede. Ele é escrito em “notação em barra” (/) seguido pelo número de bits em 1\.

Dentro de cada rede há endereços de rede, endereços de host e um endereço de difusão (broadcast).

### Transmissão Unicast, Broadcast e Multicast no IPv4

**Unicast:** Refere-se a um dispositivo que envia uma mensagem para outro dispositivo em comunicação um-para-um, ou seja, este tipo de transmissão possui somente um único destinatário.

**Broadcast ou Difusão:** Refere-se a um dispositivo enviando uma mensagem para todos os dispositivos em uma rede, ou seja, comunicação de um para todos.

**Multicast:** Refere-se a um dispositivo que envia um único pacote para um conjunto de hosts selecionados em uma rede. No IPv4 os endereços 224.0.0.0 a 239.255.255.255 foram adotados como intervalo de multicast.

### Tipos de endereços IPv4

- ***Públicos:*** São endereços globalmente roteáveis entre os roteadores ISP.

- **Privados:** São endereços utilizados pela maioria das organizações para atribuir endereços IPv4 à hosts internos (intranet) e portanto não são globalmente roteáveis.

- ***Loopback:*** É um endereço usado por um host para direcionar tráfego de volta para si mesmo.
- ***Link-Local:*** Também chamados de endereços APIPA ou endereços auto-atribuídos, são usados por um cliente DHCP do Windows para auto-configurar no caso de não existirem servidores DHCP disponíveis.


Em 1981, os endereços IPv4 foram atribuídos usando endereçamento clássico: A, B ou C, conhecido como Classful, no entanto, não é mais utilizado.

Os endereços IPv4 são gerenciados pela IANA, que aloca blocos de endereços IP aos RIRs.

**RIRs \- Registros Regionais de Internet :** São responsáveis por alocar endereços IP aos ISPs que fornecem blocos de endereços IPv4 para organizações e ISPs menores.

### Segmentação de rede

Um grande domínio de broadcast é uma rede que conecta vários hosts, no entanto, os hosts podem gerar broadcasts em excesso e afetar a rede de forma negativa.

A solução é a **divisão em sub-redes**, que se trata de dividir uma rede maior para criar domínios de broadcast menores (sub-redes).

Esta solução reduz o tráfego total da rede e melhora seu desempenho, podendo ser dividida  por local, entre redes ou por tipo de dispositivo.

### Sub-redes de uma rede IPv4

São criadas com um ou mais bits de host, que serão usados como bits de rede para a criação de redes adicionais e para isso, estende-se a máscara de sub-rede.

 Quanto mais bits de host forem emprestados, mais sub-redes poderão ser definidas e por consequência ocorrerá a redução do número de hosts por sub-rede.

É mais fácil dividir redes em sub-redes nos limites dos octetos: /8, /16 e /24.

Somente o primeiro e o último endereço de rede não devem ser emprestados, pois devem ser reservados  respectivamente para endereço de rede e para o endereço de difusão.

### Sub-rede para atender aos requisitos

Considere uma rede empresarial que contém  intranet e DMZ (Zona Desmilitarizada). Ambos têm requisitos e desafios de sub-rede.

A intranet usa espaço de endereçamento IPv4 privado, já os dispositivos DMZ exigem endereços IPv4 públicos que estão se esgotando.

Por conta disso, as organizações devem maximizar a utilização dos seus endereços IPv4 já que em algumas situações, a quantidade de hosts por sub-rede é maior do que o necessário, o que gera desperdício.

Com base nisso, surgiu o **VLSM** , com o objetivo de minimizar a quantidade de endereços de host não utilizados pelas sub-redes.

**VLSM \- Variable Subnet Length Masking**

A ideia do VLSM é evitar o desperdício de endereços não utilizados, para isso permite que uma rede seja subdividida em sub-redes de tamanho diferente conforme os requisitos identificados no planejamento da estruturação da rede e suas respectivas sub-redes IPv4.

## Módulo 12

### Problemas de IPv4

O IPv4 tem um máximo teórico de 4,3 bilhões de endereços e com uma população cada vez maior na Internet, ele está se esgotando e por conta disso é necessário a transição para o IPv6.

Ambos coexistirão no futuro próximo e a transição completa do IPv4 para o IPv6 levará vários anos.

Considerando isso, a IETF criou técnicas de migração que podem ser divididas em três categorias:

1. **Pilha Dupla:** É uma técnica de imigração do IPv4 para o IPv6 que permite que ambos coexistam e executem protocolos em um mesmo segmento de rede.

2. **Tunelamento:** É um método de transporte de pacote IPv6 através de uma rede IPv4. O pacote IPv6 é encapsulado dentro de um pacote IPv4, de forma semelhante a outros tipos de dados.

3. **Conversão:** Permite que os dispositivos habilitados para IPv6 se comuniquem com os dispositivos habilitados para IPv4 usando uma técnica de conversão semelhante à NAT IPv4.

### Representação de Endereço IPv6

Os endereços IPv6 têm 128 bits e são escritos como uma sequência de valores hexadecimais.

Cada conjunto de 4 bits são representados por um único dígito hexadecimal, totalizando 32 valores hexadecimais.

O formato preferencial para escrever um endereço IPv6 é x: x: x: x: x: x: x: x, com cada “x” consistindo de quatro valores hexadecimais.

 Por exemplo: 2001:0 db 8:0000:1111:0000:0000:0000:0000:0200.

Duas regras ajudam a reduzir o número de dígitos necessários para representar um endereço IPv6.

1. A primeira regra é omitir os 0s (zeros) à esquerda de qualquer seção de 16 bits ou hexteto. *Por exemplo:* 2001:db 8:0:1111:0:0:200.

2. A segunda é o uso de dois-pontos duplo (::) para substituir uma única sequência contígua de um ou mais segmentos de 16 bits (hextetos) compostos exclusivamente por 0s. *Por exemplo:* 2001:db 8:0:1111: :200.

 Assim como no Ipv4, o comprimento do prefixo também é representado na notação de barra e é usado para indicar a parte da rede de um endereço IPv6.

### Tipos de endereço IPv6

Há três tipos de endereços IPv6:

**Unicast:** Identifica exclusivamente uma interface em um dispositivo habilitado para IPv6. Normalmente o IPv6 tem dois endereços unicast:

1. **GUA:**  O endereço unicast global (GUA), é globalmente exclusivo e roteável na Internet IPv6 e são equivalentes aos endereços públicos do IPv4. Um GUA tem três partes:
1) Prefixo de roteamento global;
2) ID de sub-rede;
3) ID de interface.

2. **LLA:** Um endereço IPv6 de link-local permite que um dispositivo se comunique com outros dispositivos habilitados para IPv6 no mesmo link e somente nesse link (sub-rede). Os dispositivos podem obter um LLA estaticamente ou dinamicamente.


**Multicast:** É um tipo de endereço IPv6 utilizado para enviar um único pacote IPv6 para vários destinos.

**Anycast:** É um tipo de endereço IPv6, que é definido como qualquer endereço IPv6 unicast que possa ser atribuído a vários dispositivos.

### Configuração Estática \- GUA e LLA

O comando para configurar um GUA IPv6 em uma interface é: **ipv6 address**.

 Assim como ocorre no IPv4, a configuração de endereços estáticos em clientes não escala para ambientes maiores. Por esse motivo, a maioria dos administradores de redes IPv6 permite a atribuição dinâmica de endereços IPv6.

A configuração manual do LLA permite criar um endereço reconhecível e fácil de lembrar. Geralmente, só é necessário criar endereços de link local reconhecíveis nos roteadores.

Os LLAS podem ser configurados manualmente usando o comando: **ipv6 address** **link-local**

### Endereçamento dinâmico para GUAs IPv6

Um dispositivo obtém um GUA dinamicamente através de mensagens ICMPv6.

Os roteadores IPv6 enviam mensagens ICMPv6 de RA (Anúncio de Roteador) a cada 200 segundos para todos os dispositivos habilitados para IPv6 na rede.

Uma mensagem de RA também é enviada em resposta a um host que envie uma mensagem ICMPv6 de RS (Solicitação de Roteador).

A mensagem de RA ICMPv6 inclui:

- Prefixo de rede;
- Comprimento do prefixo;
- Endereço de gateway padrão;
- Endereços DNS;
- Nome de domínio.

As mensagens de RA têm três métodos:

1. **SLAAC:** Neste método o dispositivo cliente usa as informações na mensagem RA para criar seu próprio GUA;

2. **SLAAC com um servidor DHCPv6 sem estado:** Neste método a mensagem RA sugere que os dispositivos usem SLAAC para criar seu próprio IPv6 GUA, usem o roteador LLA como o endereço de gateway padrão e usem um servidor DHCPv6 sem estado para obter outras informações necessárias.

3.  **DHCPv6 com estado (sem SLAAC):**  Neste método o RA sugere que os dispositivos usem o roteador LLA como o endereço de gateway padrão e o servidor DHCPv6 com estado para obter um GUA, um endereço de servidor DNS, nome de domínio e todas as outras informações necessárias.

A ID da interface pode ser criada por meio do processo EUI-64 ou de um número de 64 bits gerado aleatoriamente.

### Endereçamento dinâmico para LLAs IPv6

Todos os dispositivos IPv6 devem ter um LLA. Este pode ser configurado manualmente ou criado dinamicamente.

Os roteadores Cisco criam automaticamente um endereço IPv6 de link local sempre que um endereço unicast global é atribuído à interface.

Por padrão, os roteadores Cisco IOS usam o EUI-64 para gerar a ID da interface de todos os endereços de link local em interfaces IPv6.

Em interfaces seriais, o roteador usará o endereço MAC de uma interface Ethernet.

Para tornar mais fácil reconhecer esses endereços em roteadores e lembrar deles, é comum configurar estaticamente endereços IPv6 de link local nos roteadores.

Para verificar a configuração do endereço IPv6, use os seguintes três comandos: **show ipv6 interface brief, show ipv6 route** e **ping**.

### Endereços de difusão seletiva IPv6

Existem dois tipos de endereços multicast IPv6:

1. **Endereços multicast conhecidos:** São endereços multicast reservados para grupos predefinidos de dispositivos, conhecidos como atribuídos, existem dois grupos comuns:
1)  ff02::1 \- Grupo de multicast de todos os nós
2)  ff02::2 \- Grupo de multicast de todos os roteadores.

2. **Endereços multicast de nós solicitados:** São semelhantes aos endereços multicast all-nodes.  Sua vantagem é que ele é mapeado para um endereço multicast Ethernet especial.

### Sub-rede de uma rede IPv6

O IPv6 foi projetado com a sub-rede em mente e portanto possui um campo de ID de sub-rede separado no GUA IPv6 e este é usado para criar sub-redes.

O campo ID da sub-rede é a área entre o Prefixo de Roteamento Global e o ID da interface.

O benefício de um endereço de 128 bits é que ele pode suportar sub-redes e hosts mais do que suficientes por sub-rede para cada rede.

Por exemplo, se o prefixo de roteamento global for /48, e usando um 64 bits típico para o ID de interface, isso criará um ID de sub-rede de 16 bits:

* ID de sub-rede de 16 bits \- Cria até 65.536 sub-redes.
* 64-bit ID da interface \- Suporta até 18 quintilhões de endereços IPv6 para hosts em cada sub-rede (i.e., 18.000.000.000.000.000.000).

Com mais de 65,536 sub-redes para escolher, a tarefa do administrador de redes é projetar um esquema lógico de endereçamento da rede e a conservação de endereços não é uma preocupação ao usar IPv6.

Similarmente ao IPv4, cada interface de roteador pode ser configurada em uma sub-rede IPv6 diferente.

## Módulo 13

### Mensagens ICMP

O conjunto TCP/IP fornece mensagens de erro e mensagens informativas ao se comunicar com outro dispositivo IP e essas mensagens são enviadas usando o ICMP.

O objetivo dessas mensagens é fornecer feedback sobre problemas relacionados ao processamento de pacotes IP sob certas condições.

As mensagens ICMP comuns ao ICMPv4 e ICMPv6 são:

1. Capacidade de acesso ao host;
2. Destino ou Serviço Inacessível;
3. Tempo excedido.

Uma mensagem de eco ICMP testa a capacidade de acesso de um host em uma rede IP.

O host local envia uma solicitação de eco ICMP (**ICMP Echo Request**) para um host. Se o host estiver disponível, o host de destino enviará uma resposta de eco (**Echo Reply**). Esta é a base do utilitário **ping**.

Quando um host ou gateway recebe um pacote que não pode ser entregue, ele pode usar uma mensagem de Destino Inacessível do ICMP para notificar a fonte. A mensagem por sua vez conterá um código que indica por que não foi possível entregar o pacote.

Ex: Se um roteador recebe um pacote e diminui o campo TTL para zero, ele descarta o pacote e envia uma mensagem de tempo excedido ao host de origem e este tipo de mensagem é utilizada pela ferramenta **traceroute**.

### Teste de Ping e Traceroute

O ping, usado pelo IPv4 e IPv6, usa a solicitação de eco ICMP e as mensagens de resposta de eco para testar a conectividade entre hosts.

**Como o Ping funciona?**

Envia uma requisição de eco ao host usando o comando **ping,** se o host no endereço especificado receber a requisição, ele enviará uma resposta de eco.

À medida que cada resposta de eco é recebida, o ping fornece feedback sobre o tempo entre o envio da requisição e o recebimento da resposta.

Depois que todas as requisições forem enviadas, o ping exibe um resumo que inclui a taxa de sucesso e o tempo médio de ida e volta até o destino.

**Como o Traceroute funciona?**

O traceroute (tracert) gera uma lista de saltos que foram alcançados com sucesso ao longo do caminho.

Esta lista fornece informações de verificação e solução de problemas. Se os dados atingirem o destino, o rastreamento listará a interface de cada roteador no caminho entre os hosts.

Caso ocorra falha nos dados em algum salto ao longo do caminho, o endereço do último roteador que respondeu ao rastreamento poderá fornecer uma indicação de onde está o problema ou das restrições de segurança que foram encontradas.

O tempo de ida e volta é o tempo que um pacote leva para alcançar o host remoto e retornar a resposta do host.