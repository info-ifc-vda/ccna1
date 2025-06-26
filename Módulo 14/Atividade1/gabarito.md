# Gabarito Atividade 1


1.
    1. Só olhar no campo No. ou procurar no pacote logo no começo, chamado de **Frame Number**
        ```
        Frame 29: 81 bytes on wire (648 bits), 81 bytes captured (648 bits) on interface enp7s0, id 0
        Frame Number: 29
        ```
    Neste caso é **Frame 29**

    2. É possível usar a porta destino para identificar
        ```
        User Datagram Protocol, Src Port: 57194, Dst Port: 53
        ```
    Usando o campo **Dst Port: 53** que indica o tipo **DNS**

    3. É possível identificar eles olhando os campos no datagrama, tome cuidado, pois o wireshark mostra mais campos do que realmente existem no pacote
        ```
        User Datagram Protocol, Src Port: 57194, Dst Port: 53
        Source Port: 57194
        Destination Port: 53
        Length: 47
        Checksum: 0xb2fc [unverified]
        [Checksum Status: Unverified]
        [Stream index: 0]
        [Timestamps]
        UDP payload (39 bytes)
        ```
    Os campos são **Source Port**, **Destination Port**, **Lenght** e **Checksum** totalizando **4**.

    4. É possível identificar eles olhando os campos no datagrama, tome cuidade, pois o wireshark mostra mais campos do que realmente existem no pacote
        ```
        User Datagram Protocol, Src Port: 57194, Dst Port: 53
        Source Port: 57194
        Destination Port: 53
        Length: 47
        Checksum: 0xb2fc [unverified]
        [Checksum Status: Unverified]
        [Stream index: 0]
        [Timestamps]
        UDP payload (39 bytes)
        ```
    Os campos são **Source Port**, **Destination Port**, **Length** e **Checksum**

2. É possível contar os bytes pelos hexadecimais
    ```
    df 6a 00 35 00 2f b2 fc
    ```
    **8** bytes

3. Verifique o tamanho do payload e lembre-se do tamanho do cabeçalho do datagrama UDP
    ```
    Length: 47
    UDP payload (39 bytes)
    ```
    O comprimento (length) se refere ao tamanho do payload + tamanho do cabeçalho, portanto, o tamanho do datagrama

4. Verifique o comprimento no cabeçalho do datagrama e também o tamanho do cabeçalho do pacote, verifique qual é o tamanho máximo que ambos podem comportar
    ```
    Pacote: Total Length: 67 em HEX 00 43
    Datagrama: Length: 47 em HEX 00 2f
    ```
    O tamanho máximo é variado dependendo de qual protocolo IPv4 ou IPv6 está sendo usado
    IPv4: 2^16 - 1 - 8 - 20 = 65507 bytes
    IPv6: 2^16 - 1 - 8 - 40 = 65487 bytes

5. Verifique o tamanho máximo do campo **Dst Port**:
    ```
    Dst Port: 53 em HEX 00 35
    ```
    O tamanho máximo é 2^16 - 1 = 65535

6. Para responder a essa pergunta, você precisará olhar o campo protocolo (protocol) do datagrama IP que contém esse segmento UDP
    ```
    Protocol: UDP (17)
    ```
    O número é **17**
7.
    1. Siga o mesmo procedimento da questão 1, usando desta vez os dois pacotes
        ```
        Frame Number: 29
        ```
    **29**

    2. Verifique no cabeçalho do datagrama
        ```
        Source Port: 57194
        ```
    **57194**

    3. Verifique no cabeçalho do datagrama
        ```
        Destination Port: 53
        ```
    **53**

    4. Verifique no cabeçalho do datagrama
        ```
        Frame Number: 30
        ```
    **30**

    5. Verifique no cabeçalho do datagrama
        ```
        Source Port: 53
        ```
    **53**

    6. Verifique no cabeçalho do datagrama
        ```
        Destination Port: 57194
        ```
    **57194**

    7. Pense em quem está enviando e quem está recebendo cada pacote.
    No pacote 1, o seu computador está enviando para um servidor DNS cujo serviço é oferecido pela porta 53 e, por isso, a porta destino é a porta 53.
    No pacote 2, o servidor DNS está enviando uma resposta para o seu computador, usando a porta do seu computador como porta destino e a sua porta do serviço DNS como porta origem.