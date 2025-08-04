## Configurar o roteador R2

1.  Você precisa rodar o comando:
    ```bash
    enable
    configure terminal
    interface fastEthernet 0/0
    ip address 192.168.1.2 255.255.255.0
    no shutdown
    exit
    copy running-config startup-config
    ```

## Configurar o roteador R1

1.  Você precisa rodar o comando:
    ```bash
    enable
    configure terminal
    no ip domain-lookup
    ```

2.  Você precisa rodar o comando (Obs: não use copiar e colar para esse comando):
    ```bash
    banner motd #ACESSO NAO AUTORIZADO E PROIBIDO#
    ```

3.  Você precisa rodar o comando:
    ```bash
    interface fastEthernet 0/0
    ip address 192.168.1.1 255.255.255.0
    no shutdown
    end
    ```

4.  Você precisa rodar o comando:
    ```bash
    copy running-config startup-config
    ```

## Configurar o Roteador R1 para o Acesso SSH

1.  Você precisa rodar o comando:
    ```bash
    enable
    configure terminal
    hostname R1
    ```

2.  Você precisa rodar o comando:
    ```bash
    ip domain-name lab.local
    ```

3.  Você precisa gerar as chaves RSA com o comando:
    ```bash
    crypto key generate rsa
    ```
    Quando solicitado, digite o tamanho das chaves — recomenda-se pelo menos 1024 bits:
    ```bash
    How many bits in the modulus [512]: 1024
    ```

4.  Você precisa rodar o comando:
    ```bash
    username admin password @Dmin123
    ```

5.
    1.  Você precisa rodar os comandos:
        ```bash
        line vty 0 4
        transport input ssh telnet
        ```

    2.  Você precisa rodar o comando:
        ```bash
        login local
        ```
        E então sair do modo de linha:
        ```bash
        end
        ```

6.  Você precisa rodar o comando:
    ```bash
    copy running-config startup-config
    ```

7.  Para conectar você precisa rodar o comando:
    ```bash
    ssh -l admin 192.168.1.1
    ```
    Depois, insira a senha:
    ```bash
    @Dmin123
    ```

## Implementar as Medidas de Segurança no Roteador

1.  Você precisa rodar o comando:
    ```bash
    enable
    configure terminal
    service password-encryption
    ```

2.  Você precisa rodar o comando:
    ```bash
    security passwords min-length 12
    ```

3.
    1.  Você precisa rodar o comando:
        ```bash
        enable secret $cisco!PRIVA*
        ```

    2.  Você precisa rodar o comando:
        ```bash
        line console 0
        password $cisco!!CON*
        login
        exit
        ```

    3.  Comando:
        ```bash
        line vty 0 4
        password $cisco!!VTY*
        login
        exit
        ```

4.  Comando:
    ```bash
    line vty 0 4
    transport input ssh
    no username admin
    username SSHAdmin secret 55Hadm!n2020
    crypto key generate rsa
    1024
    ```

5.  Comando:
    ```bash
    line console 0
    exec-timeout 5 0
    exit
    ```

    ```bash
    line vty 0 4
    exec-timeout 5 0
    login local
    exit
    ```

    ```bash
    login block-for 120 attempts 3 within 60
    exit
    ```

## Configure medidas de segurança avançada

1.
    1.  Comando:
        ```bash
        show ip interface brief
        ```

    2.  Comando:
        ```bash
        configure terminal
        interface fastEthernet 1/0
        shutdown
        exit
        interface fastEthernet 1/1
        shutdown
        end
        ```
2.  Va no R2 e rode o seguinte comando:
    ```bash
    telnet 192.168.1.1
    ```
    R1 deve blockear o acesso.

3.  Va no R2 e rode o seguinte comando:
    ```bash
    ssh -l SSHAdmin 192.168.1.1
    ```
    insira a senha:
    ```bash
    55Hadm!n2020
    ```

4.  Não permitira o acesso por 120s

5.  Comando:
    ```bash
    show login
    ```
6.  Comando:
    ```bash
    show running-config
    ```

## Implementar configurações básicas no switch

1.  Você precisa rodar o comando:
    ```bash
    enable
    configure terminal
    no ip domain-lookup
    ```

2.  Você precisa rodar o comando:
    ```bash
    banner motd #ACESSO NAO AUTORIZADO E PROIBIDO#
    ```

3.  Você precisa rodar o comando:
    ```bash
    write memory
    ```

## Implementar as Medidas de Segurança no no Switch

1.  Você precisa rodar o comando:
    ```bash
    service password-encryption
    ```

2.  Você precisa rodar o comando:
    ```bash
    security passwords min-length 12
    ```

3.  Você precisa rodar o comando:
    ```bash
    enable secret $cisco!PRIVA*
    ```

4.  Você precisa rodar os comandos:
    ```bash
    line console 0
    password $cisco!!CON*
    login
    ```

5.  Você precisa rodar os comandos:
    ```bash
    line console 0
    exec-timeout 5 0
    line vty 0 4
    exec-timeout 5 0
    ```

6.  Você precisa rodar o comando:
    ```bash
    login block-for 120 attempts 3 within 60
    ```

7.  Você pode usar os comandos:
    ```bash
    interface range Ethernet 0/2- 3
    shutdown
    exit
    interface range Ethernet 1/0 - 3
    shutdown
    exit
    interface range Ethernet 2/0 - 3
    shutdown
    exit
    interface range Ethernet 3/0 - 3
    shutdown
    exit
    ```

## Verificar se as medidas de segurança foram implementadas corretamente

1.  Comando:
    ```bash
    show ip interface brief
    ```

2.  Senha: $cisco!PRIVA*

3.  Comando:
    ```bash
    show running-config
    ```