# Gabarito:

## 1. Configurar a rede local 1.

- R1

    ```shell
    enable
    configure terminal
    interface fastEthernet 0/0
    ip address 192.168.0.33 255.255.255.224
    no shutdown
    end
    ```

- PC1

    ```shell
    ip 192.168.0.34/27 192.168.0.33
    ```

## 2. Configurar a rede local 2.

- R2

    ```shell
    enable
    configure terminal
    interface fastEthernet 0/0
    ip address 192.168.1.46 255.255.255.240
    no shutdown
    end
    ```

- PC2

    ```shell
    ip 192.168.1.33/28 192.168.1.46
    ```

## 3. Configurar a rede (R1, R2).

- R1

    ```shell
    enable
    configure terminal
    interface fastEthernet 1/0
    ip address 11.0.0.17 255.255.255.252
    no shutdown
    end
    ```

- R2

    ```shell
    enable
    configure terminal
    interface fastEthernet 1/0
    ip address 11.0.0.18 255.255.255.252
    no shutdown
    end
    ```

## 4. Configuração do método de roteamento RIP.

- R1

    ```shell
    enable
    configure terminal
    router rip
    network 11.0.0.16
    network 192.168.0.32
    end
    ```

- R2

    ```shell
    enable
    configure terminal
    router rip
    network 11.0.0.16
    network 192.168.1.32
    end
    ```