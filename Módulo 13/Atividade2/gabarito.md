# Gabarito:

## 1. Divisao de enderecos.

Dividindo a rede 192.168.3.0/26 em um /29 se obtem essas 4 redes, O range da rede 192.168.3.0/26 'e de "192.168.3.1 - 192.168.3.62" o que nos da apenas 62 enderecos.

| Subnet ID 	| Subnet Address 	| Host Address Range          	| Broadcast Address 	|
|-----------	|----------------	|-----------------------------	|-------------------	|
| 1         	| 192.168.3.0    	| 192.168.3.1 - 192.168.3.6   	| 192.168.3.7       	|
| 2         	| 192.168.3.8    	| 192.168.3.9 - 192.168.3.14  	| 192.168.3.15      	|
| 3         	| 192.168.3.16   	| 192.168.3.17 - 192.168.3.22 	| 192.168.3.23      	|

Essas 3 sub-redes sao o suficientes para suprir a necessidade atual, e ainda teriamos mais 5 caso necessario.

## 2. Configurar a interface <fa 0/0> de cada roteador.

- R1
    ```shell
    enable
    configure terminal
    interface fastEthernet 0/0
    ip address 192.168.3.1 255.255.255.248
    no shutdown
    end
    ```

- R2
    ```shell
    enable
    configure terminal
    interface fastEthernet 0/0
    ip address 192.168.3.9 255.255.255.248
    no shutdown
    end
    ```

- R3
    ```shell
    enable
    configure terminal
    interface fastEthernet 0/0
    ip address 192.168.3.17 255.255.255.248
    no shutdown
    end
    ```

## 3. Conectar os roteadores.

- R1 <fa 0/1> <--> R2 <fa 0/1>
- R2 <fa 1/0> <--> R3 <fa 1/0>

    | Subnet ID 	| Subnet Address 	| Host Address Range    	| Broadcast Address 	|
    |-----------	|----------------	|-----------------------	|-------------------	|
    | 1         	| 10.0.0.0       	| 10.0.0.1 - 10.0.0.2   	| 10.0.0.3          	|
    | 2         	| 10.0.0.4       	| 10.0.0.5 - 10.0.0.6   	| 10.0.0.7          	|

- R1
    ``` shell
    enable
    configure terminal
    interface fastEthernet 0/1
    ip address 10.0.0.1 255.255.255.252
    no shutdown
    end
    ```

- R2
    ``` shell
    enable
    configure terminal
    interface fastEthernet 0/1
    ip address 10.0.0.2 255.255.255.252
    no shutdown
    end
    ```
    ``` shell
    enable
    configure terminal
    interface fastEthernet 1/0
    ip address 10.0.0.5 255.255.255.252
    no shutdown
    end
    ```
- R3
    ``` shell
    enable
    configure terminal
    interface fastEthernet 1/0
    ip address 10.0.0.6 255.255.255.252
    no shutdown
    end
    ```

## 4. Configurar o RIP

- R1
    ```shell
    enable
    configure terminal
    router rip
    version 2
    network 10.0.0.0
    network 192.168.3.0
    end
    ```
- R2
    ```shell
    enable
    configure terminal
    router rip
    version 2
    network 10.0.0.0
    network 10.0.0.4
    network 192.168.3.8
    end
    ```
- R3
    ```shell
    enable
    configure terminal
    router rip
    version 2
    network 10.0.0.4
    network 192.168.3.16
    end
    ```

## 5. configurar o DHCP

- R1
    ```shell
    enable
    conf terminal
    ip dhcp pool DHCP
    network 192.168.3.0 255.255.255.248
    default-router 192.168.3.1
    exit
    ip dhcp excluded-address 192.168.3.1
    end
    ```
- R2
    ```shell
    enable
    conf terminal
    ip dhcp pool DHCP
    network 192.168.3.8 255.255.255.248
    default-router 192.168.3.9
    exit
    ip dhcp excluded-address 192.168.3.9
    end
    ```

- R3
    ```shell
    enable
    conf terminal
    ip dhcp pool DHCP
    network 192.168.3.16 255.255.255.248
    default-router 192.168.3.17
    exit
    ip dhcp excluded-address 192.168.3.17
    end
    ```

## 6. Va em cada um dos PCs e use o comando `dhcp`.

```shell
dhcp -d
```
```shell
ping <algum ip de host na rede>
```