### Finalidade da Camada Física

É na camada física que é estabelecida uma conexão física, seja ela com fio usando um cabo ou sem fio usando ondas de rádio.

No modelo OSI, esta camada fornece os meios para transportar os bits que formam um quadro da camada de enlace no meio físico de rede.

Além disso, são as NICs que conectam um dispositivo à rede. NICs Ethernet são usadas para uma conexão com fio, já NICs WLAN são usadas para sem fio.

### Características da Camada Física

Seus padrões abordam 3 áreas funcionais: componentes físicos, codificação e sinalização.

**Largura de banda:** É a capacidade na qual um meio pode transportar dados.

**Taxa de transferência:** É a medida da transferência de bits pela mídia durante um determinado período de tempo e geralmente é menor que a largura de banda.

**Latência:** Se refere ao tempo necessário para os dados viajarem de um ponto a outro, incluindo atrasos.

**Goodput:** É a medida de dados usáveis transferidos em um determinado período.

A  representação e os agrupamentos de bits para cada tipo de mídia são divididos da seguinte maneira:

* Cabo de cobre \- Os sinais são padrões de pulsos elétricos.
* Cabo de fibra óptica \- Os sinais são padrões de luz.
* Wireless \- Os sinais são padrões de transmissão por microondas.

#### Cabeamento de Cobre

É barato, fácil de instalar e tem baixa resistência à corrente elétrica, entretanto, é limitado pela distância e interferência de sinal que pode ser de duas fontes: EMI e diafonia.

As características elétricas do cabeamento de cobre são definidas pelo IEEE.

Os principais tipos de cabos que são obtidos usando convenções de fiação específicas são Ethernet Straight-through e Ethernet Crossover.
Existem três tipos de cabeamento de cobre, são eles: UTP, STP e cabo coaxial.

- UTP

Tem uma “jaqueta” externa para proteger os fios de cobre contra danos físicos, os pares de fio são torcidos para proteger o sinal de interferência. Além disso, existe um isolamento plástico codificado por cores que isolam eletricamente os fios uns dos outros e identificam cada par.

A Cisco tem um cabo UTP proprietário chamado rollover que conecta uma estação de trabalho a uma porta de console do roteador.

- STP

Usa quatro pares de fios, cada um enrolado em uma blindagem de alumínio, que é enrolada em uma trança ou folha metálica geral.

- Coaxial

Ou coax para abreviar, recebeu seu nome porque tem dois condutores que compartilham o mesmo eixo. É usado para conectar antenas a dispositivos sem fio.

#### Cabeamento em Fibra Óptica

A fibra óptica é um fio flexível, extremamente fino e transparente de vidro muito puro, não muito maior do que um fio de cabelo humano.

É completamente imune a EMI e RFI e transmite dados por longas distâncias e a larguras de banda mais altas do que qualquer outra mídia de rede.

Os cabos de patch de fibra óptica incluem multimodo e monomodo.

Existem quatro tipos de conectores de fibra óptica: ST, SC, LC e LC multimodo duplex.

É utilizado em quatro tipos de indústria: redes empresariais, FTTH, redes de longo curso e redes de cabos submarinos.

#### Mídia sem Fio

Transporta sinais eletromagnéticos que representam os dígitos binários de comunicações de dados usando frequências de rádio ou de micro-ondas.

A rede sem fio tem algumas limitações, incluindo: área de cobertura, interferência, segurança e os problemas que ocorrem com qualquer mídia compartilhada.

Os padrões sem fio incluem o seguinte: Wi-Fi (IEEE 802.11), Bluetooth (IEEE 802.15), WiMAX (IEEE 802.16) e Zigbee (IEEE 802.15.4).
