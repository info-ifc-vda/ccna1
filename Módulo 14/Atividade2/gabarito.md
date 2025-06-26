# Gabarito Atividade 2

1. Voce precisa olhar no pacote HTTP:
    ```
    Internet Protocol Version 4, Src: 192.168.x.x, Dst: 128.119.245.12
    Transmission Control Protocol, Src Port: 59472, Dst Port: 80, Seq: 152797, Ack: 1, Len: 90
    ```
    No meu caso, o ip é 192.168.x.x e a porta é 59472.
2. Voce precisa olhar no pacote HTTP:
    ```
    Internet Protocol Version 4, Src: 192.168.x.x, Dst: 128.119.245.12
    Transmission Control Protocol, Src Port: 59472, Dst Port: 80, Seq: 152797, Ack: 1, Len: 90
    ```
    Resposta é: 128.119.245.12 e porta 80.

3. Você precisa olhar no primeiro segmento TCP:
    ```
    229	30.471140764	192.168.44.194	128.119.245.12	TCP	74	48158 → 80 [SYN] Seq=0 Win=64240 Len=0 MSS=1460 SACK_PERM TSval=1932030794 TSecr=0 WS=128
    ```
    O campo **Sequence Number: 0    (relative sequence number)** ou **Seq=0**.

4. Voce precisa olhar no segundo segmento TCP:
    ```
    230	30.690881488	128.119.245.12	192.168.44.194	TCP	74	80 → 48158 [SYN, ACK] Seq=0 Ack=1 Win=28960 Len=0 MSS=1250 SACK_PERM TSval=3819579583 TSecr=1932030794 WS=128
    ```
    Número de sequência do segmento: 0.
    O que identifica este segmento como um segmento SYNACK: A presença das flags [SYN, ACK].
    Qual é o valor do campo de reconhecimento no segmento SYNACK: O campo Ack tem o valor 1.
    Como <https://gaia.cs.umass.edu/> determinou esse valor: O valor do campo Ack no segmento SYNACK é 1 porque o cliente enviou um SYN com um número de sequência X, e a resposta SYNACK do servidor deve ter Ack = X + 1.
5. Voce precisa olhar no quarto segmento TCP:
    ```
    232	30.692342131	192.168.x.x	128.119.245.12	TCP	1304	48158 → 80 [ACK] Seq=1 Ack=1 Win=64256 Len=1238 TSval=1932031015 TSecr=3819579583 [TCP segment of a reassembled PDU]
    ```
    No caso o segmento vem logo depois do three-way handshake, **Seq=1**.
6.
    1. Voce precisa olhar para o campo time:
        ```
        232	30.692342131	192.168.x.x	128.119.245.12	TCP	1304	48158 → 80 [ACK] Seq=1 Ack=1 Win=64256 Len=1238 TSval=1932031015 TSecr=3819579583 [TCP segment of a reassembled PDU]
        ```
        No caso é **30.692342131**.
    2. Voce precisa olhar para o campo time da resposta do servidor:
        ```
        242	30.913951227	128.119.245.12	192.168.x.x	TCP	66	80 → 48158 [ACK] Seq=1 Ack=1239 Win=31872 Len=0 TSval=3819579810 TSecr=1932031015
        ```
        No caso é **30.913951227**.
    3. Voce precisa calcular a diferença de tempo:
        ```
        232	30.692342131	192.168.x.x	128.119.245.12	TCP	1304	48158 → 80 [ACK] Seq=1 Ack=1 Win=64256 Len=1238 TSval=1932031015 TSecr=3819579583 [TCP segment of a reassembled PDU]
        242	30.913951227	128.119.245.12	192.168.x.x	TCP	66	80 → 48158 [ACK] Seq=1 Ack=1239 Win=31872 Len=0 TSval=3819579810 TSecr=1932031015
        ```
        No caso é RTT = 30.913951227 - 30.692342131. **RTT=  0.221609096s**.
    4. Voce precisa calcular a diferença de tempo:
        ```
        233	30.692371619	192.168.44.194	128.119.245.12	TCP	1304	48158 → 80 [PSH, ACK] Seq=1239 Ack=1 Win=64256 Len=1238 TSval=1932031015 TSecr=3819579583 [TCP segment of a reassembled PDU]
        242	30.913951227	128.119.245.12	192.168.x.x	TCP	66	80 → 48158 [ACK] Seq=1 Ack=1239 Win=31872 Len=0 TSval=3819579810 TSecr=1932031015
        ```
        No caso é RTT = 30.913951227 - 30.692371619 **RTT=  0.221579608s**.
    5. Voce precisa calcular a diferença de TSval:
        ```
        233	30.692371619	192.168.44.194	128.119.245.12	TCP	1304	48158 → 80 [PSH, ACK] Seq=1239 Ack=1 Win=64256 Len=1238 TSval=1932031015 TSecr=3819579583 [TCP segment of a reassembled PDU]
        242	30.913951227	128.119.245.12	192.168.x.x	TCP	66	80 → 48158 [ACK] Seq=1 Ack=1239 Win=31872 Len=0 TSval=3819579810 TSecr=1932031015
        ```
        No caso RTT estimado = 3819579810 - 1932031015 **RTT estimado= 1887548795**.
7. (OBS: a atividade foi feita com outro computador apartir daqui.)
Voce precisa olhar o campo length dos primeiros 4 pacotes depois do three-way handshake:
    ```
    279881	320.628863804	192.168.2.13	128.119.245.12	TCP	1494	59472 → 80 [ACK] Seq=1 Ack=1 Win=64256 Len=1428 TSval=761915297 TSecr=3766186961 [TCP segment of a reassembled PDU]
    279882	320.628867491	192.168.2.13	128.119.245.12	TCP	1494	59472 → 80 [PSH, ACK] Seq=1429 Ack=1 Win=64256 Len=1428 TSval=761915297 TSecr=3766186961 [TCP segment of a reassembled PDU]
    279884	320.631438071	192.168.2.13	128.119.245.12	TCP	1494	59472 → 80 [ACK] Seq=2857 Ack=1 Win=64256 Len=1428 TSval=761915297 TSecr=3766186961 [TCP segment of a reassembled PDU]
    279885	320.631447856	192.168.2.13	128.119.245.12	TCP	1494	59472 → 80 [PSH, ACK] Seq=4285 Ack=1 Win=64256 Len=1428 TSval=761915297 TSecr=3766186961 [TCP segment of a reassembled PDU]
    ```
    No caso todos tem 1494 bytes.

8. Voce precisa olhar o campo Win da primeira mensagem do servidor:
    ```
    279879	320.628613303	128.119.245.12	192.168.2.13	TCP	74	80 → 59472 [SYN, ACK] Seq=0 Ack=1 Win=28960 Len=0 MSS=1440 SACK_PERM TSval=3766186961 TSecr=761915152 WS=128

    ```
    Nesse caso foi de **Window: 28960** ou **Win=28960** bytes. E como vimos, não houve restricao por causa do buffer e podemos calcular isso tambem, as 4 primeira mensagens de dados pesam 5976 bytes.
9. Provavelmente tera uma retrasmissão. O pedido de retrasmissao ocorre quando o destinatario envia um ACK duplicado,tera uma flag [TCP Dup ACK 280825#1] no wireshark. A resposta tera uma flag [TCP Fast Retransmission] ou [TCP Retransmission] no wireshark , exemplo:
    ```
    280825	321.278325004	128.119.245.12	192.168.2.13	TCP	78	80 → 59472 [ACK] Seq=1 Ack=101389 Win=182400 Len=0 TSval=3766187607 TSecr=761915787 SLE=102817 SRE=104245
    280826	321.278325272	128.119.245.12	192.168.2.13	TCP	86	[TCP Dup ACK 280825#1] 80 → 59472 [ACK] Seq=1 Ack=101389 Win=182400 Len=0 TSval=3766187607 TSecr=761915787 SLE=107101 SRE=108529 SLE=102817 SRE=104245
    280831	321.278453881	192.168.2.13	128.119.245.12	TCP	1494	[TCP Fast Retransmission] 59472 → 80 [ACK] Seq=101389 Ack=1 Win=64256 Len=1428 TSval=761915946 TSecr=3766187607 [TCP segment of a reassembled PDU]
    ```

10. O receptor normalmente reconhece 2 segmentos por vez, ele faz isso para reduzir o trafego na rede. Sim, voce precisa analizar onde esta faltando uma reconhecimento de chegada, se o recptor nao pedir posteriormente quer dizer que ele reconheceu os dois segmentos

11. Podemos calcular isso sabendo, o tamanho do arquivo, quando a transmissão de dados iniciou e quando terminou.
    ```
        279881	320.628863804	192.168.2.13	128.119.245.12	TCP	1494	59472 → 80 [ACK] Seq=1 Ack=1 Win=64256 Len=1428 TSval=761915297 TSecr=3766186961 [TCP segment of a reassembled PDU]
        280833	321.278461037	192.168.2.13	128.119.245.12	TCP	1494	[TCP Retransmission] 59472 → 80 [ACK] Seq=105673 Ack=1 Win=64256 Len=1428 TSval=761915946 TSecr=3766187607 [TCP segment of a reassembled PDU]
    ```
    Olhando na mensagem HTTP final descobrimos o tamanho do arquivo (File Data: 152351 bytes), e no codigo assima temos o primeiro segmento e a ultima retrasmissao, fazendo o calculo (Throughput = Total de bytes transferidos / Tempo total da transferência​) teremos o resultado que no caso foi de aproximadamente (234531 =~ 152351 / (321.278461037−320.628863804))