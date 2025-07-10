# Configuracao de acesso via SSH e implementacao de medidas básicas de segurança

- tabela do comando ssh
    ```
    ssh ?

    -c         Selecionar algoritmo de criptografia
    -l         Iniciar sessão com este nome de utilizador
    -m         Selecionar algoritmo HMAC
    -o         Especificar opções
    -p         Conectar a esta porta
    -v         Especificar a versão do protocolo SSH
    -vrf       Especificar o nome do vrf
    WORD       Endereço IP ou nome de host de um sistema remoto
    ```

## Configurar o roteador R2

Pelo fato do VPCs do GNS3 não dar suporte a SSH, vamos usar outro roteador cisco, o processo é quase o mesmo.

1. Configure o R2 com um endereço IP e máscara de sub-rede.

## Configurar o roteador R1

1. Desative a pesquisa do DNS para evitar que o roteador tente converter comandos inseridos incorretamente como se fossem nomes de host.

2. Crie um banner que avisará que o acesso não autorizado é proibido.

3. Configure e ative a interface **fastEthernet 0/0** no roteador usando as informações da tabela de endereçamento.

4. Salve a configuração atual no arquivo de inicialização.

## Configurar o Roteador R1 para o Acesso SSH

1. Configure o nome do dispositivo.

2. Configure o domínio do dispositivo.

3. Configure o método de chave de criptografia

4. Configure um nome de usuário no banco de dados local

5. Habilitar o SSH nas linhas VTY

    1. Habilite Telnet e SSH nas linhas VTY de entrada.

    2. Altere o método de login para usar o banco de dados local.

6. Salve a configuração atual no arquivo de configuração inicial

7. Estabelecer uma conexão SSH com o R1 apartir do R2 usando o usuário admin e senha @Dmin123

## Implementar as Medidas de Segurança no Roteador

1. Criptografe todas as senhas de texto não criptografado.

2. Configure o sistema para exigir uma senha mínima de 12 caracteres.

3. Altere as senhas (exec privilegiado, console e vty) para atender ao novo requisito de comprimento.

    1. Defina uma senha exec privilegiada para __$cisco!PRIVA*__

    2. Defina a senha do console como __$cisco!!CON*__

    3. Defina uma senha da linha vty para __$cisco!!VTY*__

4. Configurar o roteador para aceitar somente conexões SSH de locais remotos, com usuario **SSHAdmin** e senha **55Hadm!n2020**. (Obs: remova o usuario antigo)

5. Defina configurações de segurança e práticas recomendadas no console e nas linhas vty (como timeout).

## Configure medidas de segurança avançada

1. Verificar se todas as portas não utilizadas estão desativadas

    1. Verifique as interfaces com:

    2. Desative interfaces não utilizadas:

2. Verificar se é possivel usar Telnet para conectar R1.

3. Verificar se é possivel usar SSH para conectar R1.

4. Digite errado intencionalmente as informações de usuário e senha para o SSH. O que aconteceu após o login falhar pela segunda vez?

5. De sua sessão de console no roteador, examine o status de login.

6. Visualize as configurações de segurança aplicadas, verifique as senhas e outros dados.

## Implementar configurações básicas no switch

1. Desative a pesquisa do DNS.

2. Crie um banner de aviso.

4. Salve a configuração atual.

## Implementar as Medidas de Segurança no no Switch

1. Criptografe todas as senhas de texto não criptografado.

2. Configurar o sistema para exigir uma senha mínima de 12 caracteres

3. Defina uma senha exec privilegiada para __$cisco!PRIVA*__

4. Defina a senha do console como __$cisco!!CON*__

5. Configure o tempo limite por inatividade

6. Configure o bloqueio de login após tentativas falhas

7. Desative todas as portas não utilizadas

## Verificar se as medidas de segurança foram implementadas corretamente

1. Verifique o status das interfaces

2. Entre no modo EXEC privilegiado

3. Verifique a configuração em execução