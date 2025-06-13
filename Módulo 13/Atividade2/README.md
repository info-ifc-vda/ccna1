# Atividade Sub-redes de tamanho fixo.

### Inicialização

Utilize a VM com o GNS3 para a realização desta atividade.

Baixe o arquivo [atividade2.gns3](./atividade2.gns3).

1. Abra o GNS3 e abra o arquivo que você baixou (abra este github dentro da máquina virtual)

2. Ligue todos os dispositivos clicando no botão de "play" na barra de ferramentas.

3. Para abrir o terminal em cada dispositivo, clique com o botão direito sobre o mesmo e clique em "console".

### Exercícios

1. Divisão de endereços
    1. Foi-lhe dado a rede 192.168.3.0/26.
    2. Voce precisa separar essa rede em ao menos 3 outras sub-redes do mesmo tamanho que aproveitem ao maximo possivel o espaco de endereçamento.
    3. Escreve essas redes em algum lugar para não se esquecer
    4. Lembre-se cada rede tem 6 PCs.

2. Configurar a interface **fa 0/0** de cada roteador.
    1. Voce deve definir os ips das interfaces **fa 0/0**.
    2. Escolha o primeiro ip da rede definida anteriormente.

3. Conectar os roteadores.
    1. Use a rede 10.0.0.0/24 para criar a sub-rede que conecta uma porta a outra de cada roteador.
    2. Deve ser utilizado o /30 nessas redes.
    3. A disposição física fica assim:
        1. R1 **fa 0/1** <--> R2 **fa 0/1**
        2. R2 **fa 1/0** <--> R3 **fa 1/0**

4. Configurar o RIP
    1. Entre no modo de configuração global, digite router rip e use o comando `network IP_DA_REDE` para adicionar a rede.
    2. Adicione todas as redes a que os roteadores tem acesso direto. Faça isso em todos os roteadores.

5. configurar o DHCP
    1. Em cada roteador para a rede criada na interface **fa 0/0**.
    2. No modo de configuração global, voce precisa digitar o comando `ip dhcp pool NOME_DA_POOL`.
    3. No modo de configuracao do DHCP, voce precisa denifir sua rede, use o comando `network IP_DA_REDE MASCARA`.
    4. Tambem precisa configurar o gateway, use o comando `default-router IP_DO_GATEWAY`.
    5. agora volte para o modo de configuração global e exclua o ip da interface do router, use o comando `ip dhcp excluded-address IP_A_SER_REMOVIDO`.

6. Va em cada um dos PCs e use o comando `dhcp`.
    1. se tudo estiver correto esse comando irá ligar o dhcp do PC.
    2. verifique se o ip que chegou, está correto e dentro do esperado.
    3. Teste se é possível a cominicação entre as sub-redes

## Gabarito

[link](./gabarito.md)