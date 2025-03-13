# Atividade Introdutoria GNS3

## Roteiro

### Configuração dos PCs (VPC)

Configurar o ip em cada um dos PCs.

- PC1

   ```shell
   ip 192.168.0.2/24 192.168.0.1
   save startup.vpc
   ```

- PC2

   ```shell
   ip 192.168.0.3/24 192.168.0.1
   save startup.vpc
   ```

### Configuração do Switch

Nao ha a necessidade

### Configuração do Roteador

Configurar o ip na NIC da localhost


``` shell
enable
show interfaces summary
configure terminal
interface fa 0/0
ip address 192.168.0.1 255.255.255.0
no shutdown
end
copy running-config startup-config
```

### Teste a rede

A partir do PC1 ping para os outros dispositivos

- para o PC2
    ```shell
    ping 192.168.0.3
    ```
- para o Roteador
    ```shell
    ping 192.168.0.1
    ```