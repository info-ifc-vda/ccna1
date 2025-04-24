# Prática tabela ARP no host
Esta tarefa consiste em verificar e configurar estaticamente a tabela ARP no host. 

## Linux

Este roteiro segue os comandos foram utilizados em um sistema Linux mint 22

### Visualização inicial

Para visualizar a tabela arp é utilizado o comando

```bash
arp -a
```

que resulta em algo como: \
![Resultado do comando "arp -a"](./imgs/arp%20-a.png)

explicando:
| Comando | Explicação |
|-------------------|-----------------------------------------------------|
| \_gateway | É o nome de domínio associado a esse endereço MAC |
| (192.168.0.1) | É o endereço ipv4 associado a esse endereço MAC |
| d4:ca:6d:1a:aa:66 | É o endereço MAC do dispositivo com o ipv4 anterior |
| enp1s0 | É a interface de rede |

### Ping para teste

Vamos realizar um teste para mostrar como a tabela é preenchida, para tal vamos rodar o comando

```bash
ping {ip de algum outro host na LAN}
```

algo como assim: \
![Imagem para mostrar como rodar o comando "ping" para testar a tabela ARP](./imgs/ping%20then%20arp.png)

É possível ver que uma nova entrada na tabela ARP foi adicionada, isso aconteceu pois ao "pingar" para o endereço 192.168.0.50 foi pesquisado na tabela se esse endereço ja tinha uma entrada e não havia, ai então foi enviado um pacote ARP para descobrir o MAC do dispositivo correspondente à esse endereço, caso deseje pode executar wireshark ou tcpdump filtrando por pacotes ARP para visualizar esse pacote pela rede, caso tenha dúvidas quanto a como fazer então verifique a atividade \
Se quiser verificar o endereço MAC é necessário verificar o endereço no host do ip 192.168.0.50, é preciso rodar o comando:

```bash
ifconfig
```

e então procurar na área da interface que foi utilizada na tabela ARP, o resultado será algo parecido com isso, procure na área contornada em vermelho: \
![Imagem para mostrar qual é o endereço do ip](./imgs/MAC%20do%20vizinho.png)

### Deletar uma entrada

Para deletar uma entrada de maneira manual é necessário usar o comando:

```bash
arp -d {ip da entrada que deseja apagar}
```

Como exemplo: \
![Imagem para mostrar um exemplo de como deletar uma entrada](./imgs/arp%20delete.png)

### Inserir uma entrada manualmente

Para inserir uma nova entrada de forma manual utiliza-se o comando:

```bash
arp -s {ip a entrada a ser inserida} {endereço MAC do dispositivo}
```

![Imagem para mostrar um exemplo de como inserir uma entrada manualmente](./imgs/arp%20insert.png)
