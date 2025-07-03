# Atividade HTTP

Nesta atividade, exploraremos vários aspectos do protocolo HTTP: a interação básica GET/resposta, formatos de mensagens HTTP, recuperação de arquivos HTML grandes, recuperação de arquivos HTML com objetos incorporados e autenticação e segurança HTTP. Tudo isso usando o site do CNRG (Computer Network Research Group) da universidade de Massachusetts, cada interação terá o seu próprio site, porém caso não consiga rastrear os pacotes é possível usar pacotes pré-gravados disponíveis em <http://gaia.cs.umass.edu/wireshark-labs/wireshark-traces-8.1.zip>. \
Para exemplificar as respostas, será utilizado o pacote pré-gravado, portanto, quaisquer dúvidas em relação à análise dos pacotes, você mesmo pode analisá-los. \
Caso você tenha já acessado o site e não estava monitorando a rede, então é necessário limpar o cache do seu navegador. Este tutorial pode lhe ajudar <https://www.howtogeek.com/304218/how-to-clear-your-history-in-any-browser/>, com a exceção da interação básica, necessário esperar apenas 1 minuto.

## Interação básica GET/resposta
Em um servidor, há um arquivo html que, a cada 1 minuto, é modificado e salvo, sendo recomendado que se espere 1 minuto antes de iniciar a captura de pacotes \
O nome do arquivo de leituras pré-gravadas é **http-wireshark-trace1-1.pcapng**
- Vamos começar iniciando o wireshark e selecionando a interface desejada. Como filtro, utilize "http" para mostrar apenas os pacotes que usam o protocolo HTTP
- No seu navegador web, abra o seguinte site <http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file1.html>
- Pare a captura de pacotes.

Sua janela será algo semelhante à imagem seguinte:

![Imagem inicial do wireshark](img/http_wireshark_sample.png)

O campo que nos interessa é **Hypertext Transfer Protocol**. \
Agora vamos ambos os pacotes, tanto o GET (requisição) quanto o HTTP (resposta) e responder algumas questões: 

1. O seu navegador está executando o HTTP versão 1.0, 1.1 ou 2? 

2. Qual versão do HTTP o servidor está executando?

3. Quais idiomas (se houver) seu navegador indica que pode aceitar o servidor?

4. Qual é o endereço IP do seu computador? 

5. Qual é o endereço IP do servidor gaia.cs.umass.edu?

6. Qual é o código de status retornado do servidor para o seu navegador?

7. Quando o arquivo HTML que você está recuperando foi modificado pela última vez no servidor?

8.  Quantos bytes de conteúdo estão sendo retornados ao seu navegador?

9. Ao inspecionar os dados brutos na janela de conteúdo do pacote, você vê algum cabeçalho nos dados que não são exibidos na janela de listagem de pacotes? Se sim, cite um.

## Interação HTTP condicional 
A maioria dos navegadores web realiza cache de objetos, e, portanto realiza o GET condicional ao recuperar um objeto HTTP. Usando este conhecimento, vamos requisitar um arquivo que já está em cache e então analisaremos essa comunicação. \
O nome do arquivo de leituras pré-gravadas é **http-wireshark-trace2-1.pcapng**

- Limpe o seu cache
- Inicie o wireshark e use o filtro "http"
- Abra o seguinte site <http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file2.html>, e após carregar por completo atualize a página
- Pare a captura de pacotes

Agora, analise os 4 pacotes, separados em GET (requisição) e HTTP (resposta) para as duas solicitações, e responda às seguintes perguntas:

1. Inspecione o conteúdo da primeira solicitação HTTP GET do seu navegador para o servidor. Você vê uma linha “IF-MODIFIED-SINCE” no HTTP GET?

2. Inspecione o conteúdo da resposta do servidor. O servidor retornou explicitamente o conteúdo do arquivo? Como você pode saber?

3. Agora, inspecione o conteúdo da segunda solicitação HTTP GET do seu navegador para o servidor. Você vê uma linha “IF-MODIFIED-SINCE:” no HTTP GET? Em caso afirmativo, quais informações seguem o cabeçalho “IF-MODIFIED-SINCE:”? Fique atento, pois a depender do seu navegador ou da resposta do servidor na primeira requisição, pode ser que o navegador decida realizar uma solicitação nova sem levar em consideração o seu cache.

4. Qual é o código de status HTTP e a frase retornada do servidor em resposta a este segundo HTTP GET? O servidor retornou explicitamente o conteúdo do arquivo? Explique.

## Recuperando documentos longos
Quando o arquivo HTML é muito grande para ser transferido em um pacote, então ele é dividido, nesta atividade você verá como são esses pacotes. O nome do arquivo nas leituras pré-gravadas é **http-wireshark-trace3-1.pcapng**

- Limpe o seu cache 
- Inicie o wireshark e use o filtro "http || tcp"
- Abra o seguinte site <http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file3.html>
- Pare a captura de pacotes

Procure a sua requisição HTML GET, ela deve ser algo parecido com: 
```bash
26	3.813230	10.0.0.44	128.119.245.12	HTTP	547	GET /wireshark-labs/HTTP-wireshark-file3.html HTTP/1.1
```
Logo após haverá algumas respostas e requisições TCP que é o envio do HTML, logo após uma última resposta usando o protocolo HTTP que será parecida com esta:
```bash
32	3.842202	128.119.245.12	10.0.0.44	HTTP	583	HTTP/1.1 200 OK  (text/html)
```
Ela marca o último pacote com o último pedaço de html enviado do servidor para o seu computador. Levando tudo isso em consideração responda às seguintes perguntas:

1. Quantas mensagens de solicitação HTTP GET seu navegador enviou?

2. Qual número de pacote no rastreamento contém a mensagem GET para a Declaração de Direitos?

3. Qual número de pacote no rastreamento contém o código de status e a frase associada à resposta à solicitação HTTP GET?

4. Qual é o código de status e a frase na resposta?

5. Quantos segmentos TCP contendo dados foram necessários para transportar a resposta HTTP única e o texto da Declaração de Direitos?


## Documentos HTML com objetos incorporados
Documentos HTML podem utilizar outros elementos em sua composição, como, por exemplo, um arquivo css para estilizar o html, e até mesmo imagens, nesta atividade você verá como funciona a requisição de outros arquivos dentro do HTML. O nome da leitura pré-gravada é **http-wireshark-trace4-1**.

- Limpe o cache do seu navegador
- Inicie o wireshark com o filtro "http || tcp"
- Abra o seguinte site <http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file4.html>
- Pare a captura de pacotes

Procure a sua requisição HTML GET inicial, ela deve ser algo parecido com: 
```bash
95	3.018199	10.0.0.44	128.119.245.12	HTTP	547	GET /wireshark-labs/HTTP-wireshark-file4.html HTTP/1.1 
```

1. Quantas mensagens de solicitação HTTP GET seu navegador enviou? Para quais endereços da Internet foram enviadas essas solicitações GET?

2.  Você consegue dizer se o seu navegador baixou as duas imagens em série ou se elas foram baixadas dos dois sites em paralelo? Explique

## Autenticação HTTP
Agora vamos acessar um site HTTP protegido por usuário e senha e veremos como é feita a troca de pacotes. Para acessar o site, será utilizado o usuário "wireshark-students" e a senha "network" ambas sem as aspas duplas. O nome da leitura pré-gravada é <b>http-wireshark-trace5-1</b>.

- Limpe o cache do seu navegador
- Inicie o wireshark com o filtro "http"
 Abra o seguinte site <http://gaia.cs.umass.edu/wireshark-labs/protected_pages/HTTP-wireshark-file5.html> e utilize as credenciais ditas anteriormente
- Pare a captura de pacotes

1. Qual é a resposta do servidor (código de status e frase) em resposta à mensagem HTTP GET inicial do seu navegador?

2.  Quando o seu navegador envia a mensagem HTTP GET pela segunda vez, que novo campo é incluído na mensagem HTTP GET?