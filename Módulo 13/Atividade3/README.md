# Atividade Sub-redes com VLSM.

### Inicialização

Utilize a VM com o GNS3 para a realização desta atividade.

Baixe o arquivo [atividade3.gns3](./atividade3.gns3).

1. Abra o GNS3 e abra o arquivo que você baixou (abra este github dentro da máquina virtual)

2. Ligue todos os dispositivos clicando no botão de "play" na barra de ferramentas.

3. Para abrir o terminal em cada dispositivo, clique com o botão direito sobre o mesmo e clique em "console".

### Exercícios

1. Divisão de endereços
    - Foi-lhe dado a rede 192.168.3.0/26.
    - Voce precisa separar essa rede em ao menos 3 outras sub-redes de tamanho variado, de forma que aproveitem ao máximo possivel o espaço de endereçamento.
    - Escreva essas redes em algum lugar para não se esquecer
    - A quantidade de host que cada rede tem está escrito em baixo do roteador (27, 3, 12).

2. Configurar a interface **fa 0/0** de cada roteador.
    - Voce deve definir os ips das interfaces **fa 0/0**.
    - Escolha o primeiro ip da rede definida anteriormente.

3. Conectar os roteadores.
    - Use a rede 10.0.0.0/24 para criar a sub-rede que conecta uma porta a outra de cada roteador.
    - Deve ser utilizado o /30 nessas redes.
    - A disposição física fica assim:
        - R1 <fa 0/1> <--> R2 <fa 0/1>
        - R2 <fa 1/0> <--> R3 <fa 1/0>

4. Configurar o RIP
    - Entre no modo de configuração global, digite router rip e use o comando `network IP_DA_REDE` para adicionar a rede.
    - Adicione todas as redes a que os roteadores tem acesso direto. Faça isso em todos os roteadores.

5. configurar o DHCP
    - Em cada roteador para a rede criada na interface **fa 0/0**.
    - No modo de configuração global, voce precisa digitar o comando `ip dhcp pool NOME_DA_POOL`.
    - No modo de configuração do DHCP, voce precisa denifir sua rede, use o comando `network IP_DA_REDE MASCARA`.
    - Também precisa configurar o gateway, use o comando `default-router IP_DO_GATEWAY`.
    - agora volte para o modo de configuração global e exclua o ip da interface do router, use o comando `ip dhcp excluded-address IP_A_SER_EXCLUIDO`.

6. Va em cada um dos PCs e use o comando `dhcp`.
    - se tudo estiver correto esse comando irá ligar o dhcp do PC.
    - verifique se o ip que chegou, está correto e dentro do esperado.
    - teste se é possivel a cominicação entre as sub-redes

## Gabarito

[link](./gabarito.md)