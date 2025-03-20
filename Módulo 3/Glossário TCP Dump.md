

| Comando | O que faz? / Utilidade |
| :---: | :---: |
| $ tcpdump \-i eth0 | Captura pacotes em uma interface específica. Neste caso, eth0 é a interface de rede e esta pode ser diferente em dispositivos diferentes.  |
| $ tcpdump \-i eth0 \-w capture.pcap |  Salva os pacotes capturados em um arquivo para análise posterior. Neste caso, capture.cap é o nome do arquivo, que se necessário pode ser alterado.  |
| $ tcpdump \-r capture.pcap | Serve para ler pacotes de um arquivo de captura salvo anteriormente. Neste caso, este arquivo pode ser capturado com o comando acima.  |
| $ tcpdump \-c 100 \-i eth0 | Este comando serve para capturar uma certa quantidade de pacotes, esta quantidade é limitada pela flag \-c, após a quantidade terminar os pacotes param de ser filtrados. |
| $ tcpdump host 192.168.1.1 | Captura pacotes de um host específico com base no IP, que neste caso é 192.168.1.1 |
| $ tcpdump port 80 | Serve para capturar pacotes usando um número de porta específico, neste caso foi utilizado a porta 80\. |
| $ tcpdump \-v \-i eth0 | Serve para aumentar o nível de informações na saída e isto é possível a partir da flag \-v. |
| $ tcpdump ‘tcp and port 22’ | Utiliza a sintaxe BPF (Berkeley Packet Filter) para filtros complexos, além disso, pode ser utilizado ‘or’ outra operação lógica no lugar de ‘and’. |
| $ timeout 60 tcpdump \-i eth0 | Limita o tempo de captura de pacotes a uma duração em segundos, neste caso 60\. |
| $ tcpdump icmp | Filtra pacotes ICMP, normalmente utilizados ​​para solicitações de ping. |
| $ tcpdump udp | Filtra pacotes UDP e é útil para serviços como DNS. |
| $ tcpdump net 192.168.1.0/24 | Serve para capturar pacotes de uma sub-rede específica. |
| $ tcpdump ‘tcp\[tcpflags\] & tcp-syn \!= 0’ | Serve para filtrar pacotes com base em sinalizadores TCP como SYN e ACK. |
| $ tcpdump \-i eth0 \-w \- | gzip \> capture.gz | Salva os pacotes capturados em um formato de arquivo compactado. |
| $ tcpdump \-A \-i eth0 | Exibe o conteúdo dos pacotes conforme eles são capturados. |
| $ tcpdump \-i eth0 \-n \-s 0 \-c 1000 | Exibe um resumo das estatísticas dos pacotes. |

\* Nesta tabela estão listados os comandos principais, para ter acesso ao manual com os demais comandos, clique no link abaixo.

[https://www.ibm.com/docs/en/aix/7.1?topic=t-tcpdump-command](https://www.ibm.com/docs/en/aix/7.1?topic=t-tcpdump-command)

\* Segue link da fonte utilizada para a confecção da tabela.

[https://www.howtouselinux.com/post/10-useful-tcpdump-command-examples](https://www.howtouselinux.com/post/10-useful-tcpdump-command-examples)