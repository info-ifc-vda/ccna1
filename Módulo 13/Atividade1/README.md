# Atividade 1: Rede estática.

## Roteiro

Utilize a VM com o GNS3 para a realização desta atividade.

Baixe o arquivo [atividade1.gns3](./atividade1.gns3).

1. Configurar a rede local 1 (PC1, R1, S1) para a rede 192.168.0.32/27 .
    1. O PC1 deve estar configurado com o segundo endereço de host.
    2. O R1 deve ter a interface **fa 0/0** configurada com o segundo endereço de host disponível.
    3. Verifique se os aparelhos se comunicam, use o comando `ping <ip>` a partir do PC.
    **OBS**: o comando para a configuração do ip é `ip IP/MASCARA_DECIMAL IP_GATEWAY`.

2. Configurar a rede local 2 (PC2, R2, S2) para a rede 192.168.1.46/28 .
    1. O PC2 deve estar configurado com o primeiro endereço de host.
    2. O R2 deve ter a interface **fa 0/0** configurada com o segundo endereço de host.
    3. Verifique se os aparelhos se comunicam. Utilize o comando `ping IP` a partir do PC.

3. Configurar a rede (R1, R2) para a rede 11.0.0.16/30, coloque o primeiro IP disponível no R1 e o último IP disponível no R2.
    1. R1 e R2 se conectam pela NIC com o nome de **fa 1/0**, então é essa que você deve configurar nos dois.

4. Configuração do método de roteamento.
    - Entre no modo de configuração global, digite `router rip` e use o comando `network ENDERECO_DE_REDE` para adicionar a rede.
    - Adicione todas as redes a que o roteador tem acesso. Faça isso em todos os roteadores.
    - verifique se a rota que o pacote fara para chegar do PC1 para o PC2. Apartir do PC1 use o comando `trace IP_DO_PC2`.
        -caso não lembre do ip do PC2, vá ao PC2 e use o comando `show ip`

5. Salve todas as configurações.
    - Para os roteadores, use `copy running-config startup-config`.
    - Para os PCs, use `save startup.vpc`.
    - Desligue tudo e ligue novamente.
    - Agora tente novamente o comando `trace IP_DO_PC2` a partir do PC1.
        - Se funcionar novamente, voce completou sua tarefa.
        - Se não funcionou, tente descobrir seu erro e tente até dar certo.



## Referência

### Se você não entendeu alguma parte, esse material talvez te ajude.
- <https://networklessons.com/rip/how-to-configure-rip-on-a-cisco-router>
- <https://www.site24x7.com/pt/tools/ipv4-sub-rede-calculadora.html>
