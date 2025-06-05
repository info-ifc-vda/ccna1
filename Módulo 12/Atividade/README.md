# Atividade Sub-redes de tamanho fixo.

Baixe o arquivo [RedeEstaticaIpv6.gns3](RedeEstaticaIpv6.gns3) (Acesse o link deste repositório dentro da máquina virtual)

## Roteiro

1. Em ambos os roteadores defina.
  - IPv6 como método de roteamento, use o comando `ipv6 unicast-routing`
  - Va na interface <fa 0/0> correspondente a rede local e defina o endereco IPv6, ` ipv6 address <ipv6>/64`, `ipv6 enable` e `no shutdown`.
  - defina o modo de descoberta como `ip forward-protocol nd`
  - defina a vizinhança com o comando `ipv6 route <ipv6 da rede>/<mascara> <ip da rede intermediaria>`
  - Va na interface <fa 0/1> correspondente a rede WAN e defina o endereco IPv6 para a comunicacao entre as redes, ` ipv6 address <ipv6>/64`, `ipv6 enable` e `no shutdown`.
  - No modo de configuração global defina a rota manualmente `ipv6 route <ip de destino> <ip do caminho para o deestino>`

2. Nos PCs defina o ipv6 `ip <ipv6 do host> <ipv6 do gateway>`

## Gabarito:

### 1. Configuracao do Roteador.

- R1

```shell
enable
configure terminal
ipv6 unicast-routing
interface fa 0/0
ipv6 address 2001:1::1/64
ipv6 enable
no shutdown
exit
interface fa 0/1
ipv6 address 2001:a::1/64
ipv6 enable
no shutdown
exit
ipv6 route 2001:2::1/64 2001:a::2
exit
copy running-config startup-config
```

-R2

```shell
enable
configure terminal
ipv6 unicast-routing
interface fa 0/0
ipv6 address 2001:2::1/64
no shutdown
exit
interface fa 0/1
ipv6 address 2001:a::2/64
no shutdown
exit
ipv6 route 2001:1::1/64 2001:a::1
exit
copy running-config startup-config
```

### 2. Configuracao dos PCs.

-PC1

```shell
ip 2001:1::2/64 2001:1::1
```

-PC2

```shell
ip 2001:2::2/64 2001:2::1
```