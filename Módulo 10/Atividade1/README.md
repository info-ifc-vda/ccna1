# Roteiro para prática em aula

## Configurando o roteador
```sh
Router>en
Router#conf t
Router(config)#hostname R0
R0(config)#banner motd #
=======================================================
ACESSO RESTRITO!
Somente pessoal autorizado pode acessar este equipamento.
Tentativas de acesso não autorizado serão registradas.
=======================================================
```
### Proteger o modo exec privilegiado
```sh
R0(config)#enable secret senhasecret
```

### Proteger exec do usuário
```sh
R0(config)#line console 0
R0(config-line)#password senhausuario
R0(config-line)#login
R0(config-line)#end
R0#exit
```
> Digitar a senhausuario
```sh
R0>en
Password: senhasecret
R0#show ru
```
> Ver a senha em texto limpo…

### Criptografando a senha
```sh
R0#conf t
R0(config)#service password-encryption
R0(config)#end
R0#show running-config
```
### Configurando as interfaces dos dispositivos
```sh
R0(config)#interface gigabitEthernet 0/0/0
R0(config-if)#description LAN
R0(config-if)#ip address 192.168.0.1 255.255.255.0
R0(config-if)#ipv6 address 2001:db8:acad:1::1/64
R0(config-if)#no shutdown

R0(config)#interface GigabitEthernet 0/0/1
R0(config-if)#description WAN
R0(config-if)#ip address 200.200.200.1 255.255.255.252
R0(config-if)#ipv6 address 2001:db8:acad:2::1/64
R0(config-if)#no shutdown
```

## Configurar R1
```sh
Router>en
Router#conf t
Router(config)#hostname R1
R1(config)#interface GigabitEthernet 0/0/0
R1(config-if)#ip address 200.200.200.2 255.255.255.252
R1(config-if)#ipv6 address 2001:db8:acad:2::2/64
R1(config-if)#no shutdown
R1(config-if)#end

R1#ping 200.200.200.1
R1#ping 2001:db8:acad:2::1
```

## Configurar PC
- IP: 192.168.0.1
- IPv6: 2001:db8:acad:1::2/64
- GW: 2001:db8:acad:1::1

> Volta para R0 -> Configurar telnet
```sh
R0(config)#line vty 0 4
R0(config-line)#password senhatelnet
R0(config-line)#login
R0(config-line)#transport input telnet
```
> Testar telnet do PC0

### Configurando ssh
```sh
R0(config)#ip domain-name
R0(config)#ip domain-name meu.dominio
R0(config)#crypto key generate rsa
How many bits in the modulus [512]: 1024

R0(config)#username admin privilege 15 secret admin123
R0(config)#line vty 0 4
R0(config-line)#login local
R0(config-line)#transport input ssh
R0(config-line)#exit

privilege 15
```
Nível de privilégio 15 é o mais alto no Cisco IOS (equivalente ao modo EXEC privilegiado, ou "enable").

Usuários com este nível têm acesso total para visualizar e modificar todas as configurações do equipamento.

Resumo dos principais níveis:

    0: Apenas comandos extremamente básicos (nem mesmo “show running-config” está disponível).
    1: Acesso básico de usuário, não permite configuração.
    2 a 14: Personalizável (normalmente não usados por padrão).
    15: Permite tudo, inclusive entrar no modo de configuração global (configure terminal).

Níveis 2 a 14 não vêm com permissões pré-definidas, mas você pode atribuir comandos específicos para eles.

Vamos permitir que usuários de nível 5 possam executar o comando show running-config:
```sh
    privilege exec level 5 show running-config
```

Volta para PC0 -> já não acessa mais por telnet. Precisa usar o comando ssh:
```sh
C:\>ssh -l admin 192.168.0.1
Password: admin123
```

### Verificando as configurações no Roteador R0
```sh
R0#show running-config

R0# show ip interface brief
R0#show ipv6 interface brief

R0#show ip route
R0#show ipv6 route

R0#show interfaces
R0#show ip interfaces
R0#show ipv6 interfaces
```

### Configurando o Switch
```sh
Switch(config)#hostname s1
banner motd #ACESSO RESTRITO! Somente pessoal autorizado.#
```

Configurar interface virtual do switch:
```sh
configure terminal
interface vlan 1
ip address 192.168.1.254 255.255.255.0
no shutdown
exit
ip default-gateway 192.168.1.1
```

Para SSH:
```sh
ip domain-name exemplo.local
crypto key generate rsa
username admin privilege 15 secret admin123
line vty 0 4
login local
transport input ssh
exit
```
