# Gabarito Atividade 1

## Interação básica GET/resposta

1. É preciso olhar o pacote GET (requisição) no campo **Hypertext Transfer Protocol** no sub-campo **GET /wireshark-labs/HTTP-wireshark-file1.html HTTP/1.1** ja é possível identificar no final dele
Hypertext Transfer Protocol
    ```bash
    GET /wireshark-labs/HTTP-wireshark-file1.html HTTP/1.1
    ```
    Neste caso é **1.1**.

2. É preciso olhar o pacote HTTP (resposta) no campo **Hypertext Transfer Protocol** no sub-campo **HTTP/1.1 200 OK** ja é possível identificar no final dele
    ```bash
    Hypertext Transfer Protocol
    HTTP/1.1 200 OK
    ```
    Neste caso é **1.1**

3. É preciso olhar o pacote GET (requisição) no campo **Hypertext Transfer Protocol** no sub-campo Accept-Language: en-US,en;q=0.9 lendo o seu conteúdo é possível identificar
    ```bash
    Hypertext Transfer Protocol
    Accept-Language: en-US,en;q=0.9
    ```
    Neste caso é **en-US** ou **inglês estadunidense**

4. É preciso olhar o pacote GET (requisição) no campo **Internet Protocol Version 4, Src: 10.0.0.44, Dst: 128.119.245.12** no final na parte **Src:**
ou no sub-campo **Source Address: 10.0.0.44** lendo o seu conteúdo é possível identificar, é possível também identificar usando o pacote HTTP (resposta) usando o sub-campo **Destination Address: 10.0.0.44**
    Pacote GET (requisição)
    ```bash
    Internet Protocol Version 4, Src: 10.0.0.44, Dst: 128.119.245.12
    Source Address: 10.0.0.44

    ```
    Pacote HTTP (resposta)
    ```bash
    Internet Protocol Version 4, Src: 128.119.245.12, Dst: 10.0.0.44
    Destination Address: 10.0.0.44
    ```
    Neste caso é **10.0.0.44**

5. É preciso olhar o pacote GET (requisição) no campo **Internet Protocol Version 4, Src: 10.0.0.44, Dst: 128.119.245.12** no final na parte **Dst: ** ou no sub-campo **Destination Address: 128.119.245.12** lendo o seu conteúdo é possível identificar, é possível também identificar usando o pacote HTTP (resposta) usando o sub-campo **Source Address: 128.119.245.12**
    Pacote GET (requisição)
    ```bash
    Internet Protocol Version 4, Src: 10.0.0.44, Dst: 128.119.245.12
    Destination Address: 128.119.245.12

    ```
    Pacote HTTP (resposta)
    ```bash
    Internet Protocol Version 4, Src: 128.119.245.12, Dst: 10.0.0.44
    Source Address: 128.119.245.12
    ```
    Neste caso é **128.119.245.12**

6. É preciso olhar o pacote HTTP (resposta) no campo **Hypertext Transfer Protocol** no sub-campo **HTTP/1.1 200 OK** lendo o seu conteúdo é possível identificar, mas ainda é possível ir mais fundo em um sub-campo **Status Code: 200**
    ```bash
    Hypertext Transfer Protocol
    HTTP/1.1 200 OK
    Status Code: 200

    ```
    Neste caso é **200**

7. É preciso olhar o pacote HTTP (resposta) no campo **Hypertext Transfer Protocol** no sub-campo **Last-Modified: Sat, 30 Jan 2021 06:59:02 GMT** lendo o seu conteúdo, é possível identificar
    ```bash
    Hypertext Transfer Protocol
    Last-Modified: Sat, 30 Jan 2021 06:59:02 GMT
    ```
    Neste caso é **Sábado, 30 de janeiro de 2021 as 06:59:02 GMT**

8. É preciso olhar o pacote HTTP (resposta) no campo **Hypertext Transfer Protocol** no sub-campo **File Data: 128 bytes** lendo o seu conteúdo é possível identificar
    ```bash
    Hypertext Transfer Protocol
    File Data: 128 bytes
    ```
    Neste caso é **128 bytes**

9. Não vejo nenhum

## Interação HTTP condicional

1. Não vejo nenhuma

2. Olhando o sub-campo **Status Code: 200** podemos ver que a solicitação foi atendida com sucesso, portanto o conteúdo deve estar no final do pacote. O campo **Line-based text data: text/html (10 lines)** nos mostra o conteúdo do arquivo
    ```bash
    Hypertext Transfer Protocol
    HTTP/1.1 200 OK
    Status Code: 200
    Line-based text data: text/html (10 lines)
    ```

3. Sim, nela contém a data da última modificação do arquivo que estamos guardando em cache, é possível verificar que esta informação está correta vendo o pacote de resposta da solicitação 2 e procurando o campo **Last-Modified: Sat, 30 Jan 2021 06:59:02 GMT** e comparar os dois
    ```bash
    Hypertext Transfer Protocol
    If-Modified-Since: Sat, 30 Jan 2021 06:59:02 GMT
    ```

4. No sub-campo **Status Code: 304** mostra que o código é 304, a frase fica no sub-campo **Response Phrase: Not Modified**
    ```bash
    Hypertext Transfer Protocol
    HTTP/1.1 304 Not Modified
    Status Code: 304
    Response Phrase: Not Modified
    ```
    O servidor não retornou o conteúdo, pois não havia nenhuma nova modificação, portanto o cliente iria usar o arquivo que está em seu cache

## Recuperando documentos longos

1. 1 solicitação
    ```bash
    26	3.813230	10.0.0.44	128.119.245.12	HTTP	547	GET /wireshark-labs/ HTTP-wireshark-file3.html HTTP/1.1
    ```

2. Número 26
    ```bash
    26	3.813230	10.0.0.44	128.119.245.12	HTTP	547	GET /wireshark-labs/HTTP-wireshark-file3.html HTTP/1.1
    ```

3. Número 32
    ```bash
    32	3.842202	128.119.245.12	10.0.0.44	HTTP	583	HTTP/1.1 200 OK  (text/html)
    ```

4. É preciso olhar o sub-campo **Status Code** e o **Response Phrase**
    ```bash
    Hypertext Transfer Protocol
    HTTP/1.1 200 OK
    Status Code: 200
    Response Phrase: OK

    ```
    Neste caso o código é **200** e a frase **OK**

5. É preciso identificar os pacotes que são de dados e contá-los, lembre-se de que o seu computador pode mandar um pacote ACK sinalizando que ele recebeu os pacotes já enviados e este não será contado. Como exemplo das leituras pré-gravadas, temos:
    ```bash
    28	3.841957	128.119.245.12	10.0.0.44	TCP	1514	80 → 54985 [ACK] Seq=1 Ack=482 Win=30080 Len=1448 TSval=3636786980 TSecr=492255584 [TCP segment of a reassembled PDU]
    29	3.841961	128.119.245.12	10.0.0.44	TCP	1514	80 → 54985 [ACK] Seq=1449 Ack=482 Win=30080 Len=1448 TSval=3636786980 TSecr=492255584 [TCP segment of a reassembled PDU]
    31	3.842198	128.119.245.12	10.0.0.44	TCP	1514	80 → 54985 [ACK] Seq=2897 Ack=482 Win=30080 Len=1448 TSval=3636786980 TSecr=492255584 [TCP segment of a reassembled PDU]
    32	3.842202	128.119.245.12	10.0.0.44	HTTP	583	HTTP/1.1 200 OK  (text/html)

    ```
    Neste caso temos 4 segmentos TCP, no último mostra o protocolo HTTP, porém vale mencionar que este é o protocolo da aplicação, na camada de trasporte (modelo OSI) é usado o protocolo TCP, é possível verificar-se isto lendo o conteúdo do pacote, ou até mesmo, remover o "http" do filtro e então verifica-se que este pacote ainda continua sendo mostrado

## Documentos HTML com objetos incorporados

1. Foram realizadas ao todo 3 requisições HTTP GET, os destinos são 128.119.245.12 e 178.79.137.164; Como exemplo das leituras pré-gravadas temos:
    ```bash
    95	3.018199	10.0.0.44	128.119.245.12	HTTP	547	GET /wireshark-labs/HTTP-wireshark-file4.html HTTP/1.1
    99	3.072335	10.0.0.44	128.119.245.12	HTTP	493	GET /pearson.png HTTP/1.1
    118	3.309908	10.0.0.44	178.79.137.164	HTTP	500	GET /8E_cover_small.jpg HTTP/1.1
    ```
    Neste caso a primeira requisição é do arquivo **HTTP-wireshark-file4.html**
    A segunda é da imagem **pearson.png** ao mesmo servidor do arquivo .html
    A terceira é de outra imagem **8E_cover_small.jpg** que está em outro servidor por isso o ip é diferente

2. Foi realizado o download de ambas as imagens uma depois da outra, como se o navegador fosse ler o arquivo html de cima para baixo e enviando as requisições conforme elas fossem aparecendo, podemos perceber que a imagem **pearson.png** que foi baixada antes da 8E_cover_small.jpg pois aparece antes
    ```bash
    99	3.072335	10.0.0.44	128.119.245.12	HTTP	493	GET /pearson.png HTTP/1.1
    118	3.309908	10.0.0.44	178.79.137.164	HTTP	500	GET /8E_cover_small.jpg HTTP/1.1
    ```

## Autenticação HTTP

1. Resposta
    ```bash
    Hypertext Transfer Protocol
    HTTP/1.1 401 Unauthorized
    Status Code: 401
    Response Phrase: Unauthorized
    ```

2. O campo **Authorization**
    ```bash
    Hypertext Transfer Protocol
    Authorization: Basic d2lyZXNoYXJrLXN0dWRlbnRzOm5ldHdvcms=
    ```
    Nele contém as credenciais utilizadas para fazer o login codificadas em Base64, se você abrir esta seção pelo wireshark ele já a decodifica para você, caso você queira decodificar por conta própria você pode utilizar o site [https://www.base64decode.org/](https://www.base64decode.org/)
    ``` bash
    Hypertext Transfer Protocol
    Authorization: Basic d2lyZXNoYXJrLXN0dWRlbnRzOm5ldHdvcms=
    Credentials: wireshark-students:network
    ```