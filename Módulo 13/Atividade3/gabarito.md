# Gabarito:

## 1. Divisao de enderecos.

Dividindo a rede 192.168.3.0/26 em /27, /29 e /28.

| Subnet ID 	| Subnet Address 	| Host Address Range          	| Broadcast Address 	| Mascara                |
|-----------	|----------------	|-----------------------------	|-------------------	|----------------------  |
| 1         	| 192.168.3.0    	| 192.168.3.1 - 192.168.3.30   	| 192.168.3.31       	| 255.255.255.224/27     |
| 2         	| 192.168.3.48   	| 192.168.3.49 - 192.168.3.54 	| 192.168.3.55      	| 255.255.255.248/29     |
| 3         	| 192.168.3.32    	| 192.168.3.33 - 192.168.3.46  	| 192.168.3.47      	| 255.255.255.240/28     |

Essas 3 sub-redes sao o suficientes para suprir a necessidade atual.

## 2. Configurar a interface <fa 0/0> de cada roteador.

- R1
    ```shell
    enable
    configure terminal
    interface fastEthernet 0/0
    ip address 192.168.3.1 255.255.255.224
    no shutdown
    end
    ```

- R2
    ```shell
    enable
    configure terminal
    interface fastEthernet 0/0
    ip address 192.168.3.49 255.255.255.248
    no shutdown
    end
    ```

- R3
    ```shell
    enable
    configure terminal
    interface fastEthernet 0/0
    ip address 192.168.3.33 255.255.255.240
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
    network 192.168.3.48
    end
    ```
- R3
    ```shell
    enable
    configure terminal
    router rip
    version 2
    network 10.0.0.4
    network 192.168.3.32
    end
    ```

## 5. configurar o DHCP

- R1
    ```shell
    enable
    conf terminal
    ip dhcp pool DHCP
    network 192.168.3.0 255.255.255.224
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
    network 192.168.3.48 255.255.255.248
    default-router 192.168.3.49
    exit
    ip dhcp excluded-address 192.168.3.49
    end
    ```

- R3
    ```shell
    enable
    conf terminal
    ip dhcp pool DHCP
    network 192.168.3.32 255.255.255.240
    default-router 192.168.3.33
    exit
    ip dhcp excluded-address 192.168.3.33
    end
    ```

## 6. Va em cada um dos PCs e use o comando `dhcp`.

```shell
dhcp -d
```
```shell
ping <algum ip de host na rede>
```