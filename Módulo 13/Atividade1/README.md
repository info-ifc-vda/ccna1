# Atividade 1: Rede estática.

## Roteiro

### Inicialização

Utilize a VM com o GNS3 para a realização desta atividade.

Baixe o arquivo [atividade1.gns3](./atividade1.gns3).

1. Abra o GNS3 e abra o arquivo que você baixou (abra este github dentro da máquina virtual)

2. Ligue todos os dispositivos clicando no botão de "play" na barra de ferramentas.

3. Para abrir o terminal em cada dispositivo, clique com o botão direito sobre o mesmo e clique em "console".

### Exercícios

1. Configurar a rede local 1 (PC1, R1, S1) para a rede 192.168.0.32/27 .
    1. O PC1 deve estar configurado com o segundo endereço de host disponível.
    2. O R1 deve ter a interface **fa 0/0** configurada com o primeiro endereço de host disponível.
    3. Verifique se os aparelhos se comunicam, use o comando `ping IP` a partir do PC.
    **OBS**: o comando para a configuração do ip é `ip IP/MASCARA_DECIMAL IP_GATEWAY`.

2. Configurar a rede local 2 (PC2, R2, S2) para a rede 192.168.1.32/28 .
    1. O PC2 deve estar configurado com o primeiro endereço de host.
    2. O R2 deve ter a interface **fa 0/0** configurada com o último endereço de host.
    3. Verifique se os aparelhos se comunicam. Utilize o comando `ping IP` a partir do PC.

3. Configurar a rede (R1, R2) para a rede 11.0.0.16/30, coloque o primeiro IP disponível no R1 e o último IP disponível no R2.
    1. R1 e R2 se conectam entre si pela NIC com o nome de **fa 1/0** em ambos os roteadores.

4. Configuração do método de roteamento.
    1. Entre no modo de configuração global, digite `router rip` e use o comando `network ENDERECO_DE_REDE` para adicionar a rede.
    2. Adicione todas as redes a que o roteador tem acesso. Faça isso em todos os roteadores.
    3. Verifique a rota que o pacote efetuará para chegar do PC1 para o PC2. Apartir do PC1 use o comando `trace IP_DO_PC2`.
        1. caso não lembre do ip do PC2, vá ao PC2 e use o comando `show ip`

5. Salve todas as configurações.
    1. Para os roteadores, use `copy running-config startup-config`.
    2. Para os PCs, use `save startup.vpc`.
    3. Desligue tudo e ligue novamente.
    4. Agora tente novamente o comando `trace IP_DO_PC2` a partir do PC1.



## Referência

### Se você não entendeu alguma parte, esse material talvez te ajude.
- <https://networklessons.com/rip/how-to-configure-rip-on-a-cisco-router>
- <https://www.site24x7.com/pt/tools/ipv4-sub-rede-calculadora.html>
