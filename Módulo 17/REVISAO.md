## Módulo 16

### Ameaças e vulnerabilidades de segurança


**Atores de Ameaças:** São invasores que obtêm acesso modificando o software ou explorando vulnerabilidades.

Depois que o agente da ameaça obtém acesso à rede, quatro tipos de ameaças podem surgir: 

1. Roubo de Informações;  
2. Perda e Manipulação de Dados;  
3. Roubo de Identidade;  
4. Interrupção do Serviço. 

Existem três principais vulnerabilidades ou fraquezas: 

1. Vulnerabilidade de Política; 
2. Vulnerabilidade Tecnológica;
3. Vulnerabilidade de Configuração.

As quatro classes de ameaças físicas são: 

1. Ameaças de Hardware;   
2. Ameaças Ambientais;  
3. Ameaças Elétricas;  
4. Ameaças à Manutenção.  
   

### Ataques de rede

**Malware:** É a abreviação de software malicioso, sendo este projetado especificamente para danificar, interromper, roubar ou infligir ações “ruins” ou ilegítimas em dados, hosts ou redes.

**Tipos de Malware:**

1.  Vírus;  
2. Worms;  
3. Cavalos de Troia.

Os ataques à rede podem ser classificados em três categorias principais: 

1. Ataques de Reconhecimento;

   Os três tipos de ataque de reconhecimento são: 

   **1.1** Consultas na Internet;

   **1.2** Varreduras de ping;

   **1.3** Varreduras de portas.   

 <br/> 

2. Ataques de Acesso;

   Os quatro tipos de ataques de acesso são:  

   **2.1 Ataques de senha**

      Podem ser implementados de diferentes maneiras, sendo elas: 

       2.1.1 Ataques de Força Bruta;  
       2.1.2 Ataques de Cavalo de Troia;  
       2.1.3 Sniffers de Pacotes;  

   **2.2** Ataques de Exploração de Confiança;

   **2.3** Ataques de Redirecionamento de Porta;

   **2.4** Ataques Intermediários (Man-in-the-middle)

</br>
     
3. Ataques de Negação de Serviço. 

   Os dois tipos deste ataque são: 

   **3.1** Dos;  
   **3.2** DDos;

### Mitigação de Ataques à Rede

Para mitigar ataques de rede é necessário proteger dispositivos de rede e utilizar abordagens de defesa. 

A maioria das organizações atualmente emprega a abordagem de defesa em profundidade e esta requer uma combinação de dispositivos e serviços de rede trabalhando juntos.

Para proteger usuários de uma organização contra ameaças TCP / IP, podem ser utilizados: 

**1.** VPN;  
**2.**  Firewall ASA;  
**3.** IPS;  
**4.** ESA / WSA;   
**5.** Servidor AAA;

Servidores acessíveis a usuários externos geralmente estão localizados em uma rede especial chamada DMZ.

Ademais, dispositivos de infraestrutura devem ter backups de arquivos de configuração e imagens IOS em um servidor de arquivos FTP ou similar.

Além disso, é necessário que os sistemas operacionais do fornecedor estejam sempre com as atualizações de segurança em dia,  para corrigir todos os sistemas vulneráveis e prevenir ataques de worm. 

**AAA**

É uma forma de controlar quem acessa uma rede ***(autenticar)***, o que pode fazer enquanto permanece nela ***(autorizar)*** e quais ações pode realizar ao acessar a rede ***(auditar)***.

**Firewalls de Rede**

Estão localizados entre duas ou mais redes e controlam o tráfego entre elas, além de ajudar a evitar o acesso não autorizado. 

Eles utilizam várias técnicas para determinar o que é permitido ou negado acesso a uma rede, incluindo: 

1. Filtragem de pacotes;  
2. Filtragem de aplicativos;  
3.  Filtragem de URL e SPI.

Por fim, uma empresa deve ter políticas bem documentadas em vigor, que podem incluir o uso de software antivírus e prevenção contra intrusões no host. 

### Segurança do dispositivo

Quando um novo sistema operacional é instalado em um dispositivo, por padrão são definidas configurações de segurança que devem ser alteradas imediatamente para proporcionar um maior nível de segurança. 

Além disso, o acesso ao sistema deve ser restrito apenas aos indivíduos autorizados a usar esses recursos, e quaisquer serviços e aplicativos desnecessários devem ser desativados e desinstalados quando possível. 

Ademais, é de extrema importância utilizar senhas fortes e criptografadas para proteger e dificultar o acesso aos dispositivos de rede.

Para roteadores Cisco, o recurso Cisco AutoSecure pode ser usado para ajudar a proteger o sistema. 

## Módulo 17

### Dispositivos em uma rede pequena

Redes pequenas geralmente têm uma única conexão WAN fornecida por DSL, cabo ou conexão Ethernet e são gerenciadas por um técnico de TI local ou por um profissional contratado. 

Os fatores a serem considerados ao selecionar dispositivos de rede para uma rede pequena são:

**1.** Custo;  
**2.** Velocidade;  
**3.** Tipos de Portas / Interfaces;  
**4.** Capacidade de Expansão;  
**5.** Recursos e Serviços do SO.

 Ao implementar este tipo de rede, crie um esquema de endereçamento IP e use-o em dispositivos finais, servidores, periféricos e dispositivos intermediários. 

A redundância desta rede pode ser conseguida instalando equipamentos duplicados ou fornecendo links de rede duplicados para áreas críticas. 

Roteadores e switches devem ser configurados para rastrear o tráfego em tempo real, como voz e vídeo. 

Ademais, um bom design de rede implementará qualidade de serviço (QoS) para classificar o tráfego cuidadosamente de acordo com a prioridade. 

### Protocolos e aplicativos de rede pequena

Há duas formas de programas de software ou processos que fornecem acesso à rede: 

1. Aplicações de Rede;  
2. Serviços da Camada de Aplicação.

</br>


**Aplicações de Rede**

São aplicativos de usuário final que implementam protocolos da camada de aplicação e a partir disso, podem se comunicar diretamente com as camadas inferiores da pilha de protocolos. 

Clientes de e-mail e navegadores Web são exemplos desse tipo de aplicação. 

**Serviços da Camada de Aplicação**

São programas que fazem interface com a rede e preparam os dados para transferência e para realizar isso podem precisar da assistência dos serviços da camada de aplicação.

As duas soluções de acesso remoto mais comuns são:

**1.** Telnet;  
**2.** Secure Shell (SSH) \- Uma alternativa segura ao Telnet.  
   

Administradores de rede também devem oferecer suporte a servidores de rede comuns e seus protocolos de rede relacionados, como:

**1.** Servidor Web;  
**2.** Servidor de E-mail;  
**3.** Servidor FTP;  
**4.** Servidor DHCP;  
**5.** Servidor DNS.

Por conta das empresas utilizarem cada vez mais telefonia IP e streaming de mídia para se comunicar com os clientes e parceiros de negócios, a infraestrutura de rede deve suportar estes e outros aplicativos em tempo real.

### Escalar para redes maiores

Para dimensionar uma rede, vários elementos são necessários: 

1. **Documentação de rede** \- Topologia física e lógica;  
     
2. **Inventário de dispositivos** \- Lista de dispositivos que usam ou compreendem a rede;  
     
3. **Orçamento** \- Orçamento de TI detalhado, incluindo orçamento de compra de equipamentos do ano fiscal;  
     
4. **Análise de tráfego** \- Protocolos, aplicativos, serviços e seus respectivos requisitos de tráfego devem ser documentados, podendo ser utilizados ferramentas como o Wireshark, Gerenciador de Tarefas, Visualizador de Eventos e Uso de Dados.

### Verifique a conectividade

Para verificar a conectividade de uma rede, podem ser utilizados os comandos **Ping** e **Traceroute (Tracert)**.

**Comando Ping**

É a maneira mais eficaz de testar a conectividade da Camada 3 entre um endereço IP de origem e de destino, este comando também exibe várias estatísticas de tempo de ida e volta. 

O Cisco IOS oferece um modo “estendido” do comando ping que permite ao usuário criar tipos especiais de pings ajustando parâmetros relacionados à operação do comando. 

**Comando Traceroute (Tracert)** 

Pode ajudar a localizar áreas problemáticas da Camada 3 em uma rede, este retorna uma lista dos saltos no roteamento de um pacote pela rede, sendo usado para identificar o ponto ao longo do caminho onde o problema pode ser encontrado. 

No Windows, o comando é tracert. No Cisco IOS, o comando é traceroute.

Há também um comando traceroute estendido, ele permite que o administrador ajuste parâmetros relacionados à operação de comando. 

**Linha de Base:** É uma das ferramentas mais eficazes para o monitoramento e a solução de problemas de desempenho de rede. Um método para iniciá-la é copiar e colar os resultados de um ping, trace, ou outro comando relevante executado em um arquivo texto.


### 

### Comandos de host e IOS

<br>

1. **Ipconfig \- ip address \- ifconfig**

   Serve para exibir as informações de endereçamento IP (endereço, máscara, roteador e DNS) em um host Windows, Linux e Mac respectivamente.

   <br>

2. **Arp** 

   Lista todos os dispositivos atualmente no cache ARP do host, que inclui o endereço IPv4, endereço físico e o tipo de endereçamento (estático / dinâmico) para cada dispositivo, podendo ser executado a partir do prompt de comando do Windows, Linux ou Mac.

<br>

3. **Comandos Show**

      Os comandos **show** comuns são:

| Comando | Usado para… |
| :---: | :---: |
| **show running-config** | Verificar a configuração atual e ajustes. |
| **show interfaces** | Verificar o estado da interface e observar se há alguma mensagem de erro. |
| **show ip interface** | Verificar informações da camada 3 na interface. |
| **show arp** | Verificar a lista de nós conhecidos na rede local. |
| **show ip route** | Verificar a tabela de rota e suas informações, na camada 3\. |
| **show protocols** | Verificar quais protocolos estão operacionais.|
| **show version** | Verificar memória, interfaces e à licença do dispositivo. |
| **show cdp neighbor** | Fornecer informações sobre cada nó CDP. |
| **show cdp neighbors detail** | Determinar se um dos vizinhos CDP possui erro de configuração IP. |
| **show ip interface brief** | Exibir todas as interfaces do roteador |

<br>

### Metodologias de solução de problemas

<br>

**Etapa 1\.** Identificar o problema.

**Etapa 2\.** Estabelecer uma teoria das causas prováveis.

**Etapa 3\.** Testar a teoria para determinar a causa.

**Etapa 4\.** Estabelecer um plano de ação e implementar a solução.

**Etapa 5\.** Verificar a solução e implementar medidas preventivas.

**Etapa 6\.** Documentar as descobertas, as ações e os resultados.

**Etapa 7\.** Escalar o problema, se necessário, para um gerente, especialmente quando for exigido um conhecimento técnico mais especializado ou quando o nível de acesso à rede não estiver disponível para o técnico responsável pela solução.

<br>

**Comando IOS Debug**

Permite que o administrador exiba mensagens geradas a partir de processos, protocolos, mecanismos e eventos do SO em tempo real para análise. 

Para exibir mensagens de log em um terminal (console virtual), utilize o comando: **terminal monitor.**

<br>

### Cenários de Solução de Problemas

<br>

**Modos de Comunicação Distintos**

Em uma comunicação, se um dos dois dispositivos estiver operando no modo full-duplex e o outro no modo half-duplex, ocorrerá uma incompatibilidade de duplex, que irá gerar um desempenho muito ruim ao longo do link físico em que está ocorrendo a comunicação.

<br>

**Endereços IP Atribuídos Erroneamente**

Se forem atribuídos erroneamente, os endereços IP podem gerar diversos problemas, inclusive conflitos de endereços IP e problemas de roteamento. 

Duas causas comuns de atribuição de IPv4 incorreta são: 

**1.** Erros de atribuição manual (IP Estático);  
**2.** Problemas relacionados a DHCP (IP Dinâmico).

A maioria dos dispositivos finais são configurados de forma que dependam de um servidor DHCP para a atribuição automática de endereço IPv4.

Se o dispositivo não puder comunicar-se com o servidor DHCP, o servidor não conseguirá atribuir um endereço IPv4 para a rede específica e o dispositivo não será capaz de comunicar-se.

<br>

**Gateway Padrão Errado ou Inexistente**

O gateway é o dispositivo de rede mais próximo que pode encaminhar o tráfego para outras redes. Se um dispositivo tiver um endereço de gateway padrão errado ou inexistente, ele não conseguirá comunicar-se com os dispositivos em redes remotas. 

Por ser caminho para as redes remotas, o endereço do Gateway Padrão precisa pertencer à mesma rede que o dispositivo final.

<br>

**Falhas de DNS**

Geralmente levam o usuário a concluir que a rede está desligada.

Se o usuário digitar um domínio, como [www.cisco.com](http://www.cisco.com), em um navegador da Web e o servidor DNS estiver inalcançável, o nome não será convertido em um endereço IP e o site não será exibido.