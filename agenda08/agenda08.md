<div align="center">
<a href="https://github.com/monicaquintal" target="_blank"><img align="right" height="100" src="https://www.svgrepo.com/show/204548/wifi-signal-monitor.svg" /></a>
<h1>Estudando Redes de Computadores</h1>
<p>Disciplina: Tecnologia da Informação II - ETEC</p>
</div>

<div id="agenda06" align="center">
<h2>Agenda 08: Internet e Protocolos - Endereçamento de Redes.</h2>
</div>

## Introdução

### Wi-fi:
- abreviação de “Wireless Fidelity” (fidelidade sem fio).
- é uma tecnologia de comunicação que não faz uso de cabos.
- geralmente é transmitida através de frequências de rádio, infravermelhos etc.

### IP (Protocolo da Internet):
- composto por um conjunto de números. 
- permite a comunicação entre computadores por meio do endereço IP.
- para organizar a distribuição de IPs, foram reservados alguns números para as redes locais e na internet, e essa responsabilidade é da Internet ***Assigned Numbers Authority*** (Autoridade Atribuidora de Números para Internet). 
- dois computadores não podem ter o mesmo IP. 
- finalizada a conexão, esse IP poderá ser atribuído a outro computador.

## Endereçamento de Redes

### Na arquitetura TCP/IP...
- cada computador é endereçado utilizando-se um endereço IP.
- tanto o computador quanto a rede devem ter endereços únicos.

## Como funciona o endereço IP versão 4 (IPv4)?

### Sobre o endereço IP:
- é um endereço lógico que funciona com 32bits (4 bytes) de comprimento, divididos de 8 em 8 (1 byte), ou octetos. 
- esses octetos geram uma representação em números decimais de 0 a 255;
- 1 octeto = 8bits, logo para representação em decimal temos 28 = 256 endereços.

### Protocolos IPv4 E IPv6:
- protocolo IPv4 possui um número de endereços limitado que já se esgotou. 
- para resolver o problema, foi desenvolvido o protocolo IPv6, que utiliza 128bits.
- a transição já está em curso.
- como o IPv4 ainda é amplamente utilizado, é nele que focaremos nossos estudos.

### Exemplo de um endereço de IP:

<div align="center">

&#32; | Endereço IP
------|:-------------:
Binário | 0000 1010.0000 0000.0000 0000.0110 0100
Decimal | 10.0.0.100

</div>

Portanto, é mais simples representar um endereço IP em decimal que em binário; porém, para realizar os cálculos para determinar os endereços de rede e broadcast deve-se utilizar a notação binária.

## Endereço e Classes de IP

- o endereço IP possui uma hierarquia composta por `endereço de rede`, de `sub-rede` e de `host` (computadores). 
- a parte do endereço de rede é utilizada pelos roteadores de rede para encaminhar os dados com os pacotes IP até a rede de destino.
- no exemplo da tabela, o número 10 corresponde ao endereço de rede e os números 0.0.100 ao endereço de host.

### Classes de IP

- o endereçamento IP está dividido em 5 classes. 
- a classe do IP determina o número de Bytes que são utilizados para representar o endereço de rede e o de hosts. 
- para determinar a classe de um endereço de IP, analisar os 4 primeiros bits do primeiro octeto dos 32 existentes.

<div align="center">

Classe | Regra | Exemplo
------|---------|--------
A | Primeiro bit é 0 | 0000 1010. 0000 0000. 0000 0000. 0000 0001 = 10.0.0.1
B | Primeiros dois bits são 10 | 1010 1100. 0001 0000. 0000 0000. 0000 0001 = 172.16.0.1
C | Primeiros três bits são 110 | 1100 0000. 1010 1000. 0000 0000. 0000 0001 = 192.168.0.1
D | Primeiros quatro bits são 1110 | 1110 0000. 1111 1111. 0000 0000. 0000 1010 = 224.255.0.10
E | Primeiros quatro bits são 1111 | 1111 0000. 1010 1010. 0101 0101. 0000 1111 = 240.170.85.15

</div>

Considerando um número de IP com a seguinte notação X.Y.Z.W, onde:

- 1º octeto = X
- 2º octeto = Y
- 3º octeto = Z
- 4º octeto = W

Com base na regra apresentada na tabela anterior, podemos chegar à seguinte conclusão:

<div align="center">

Classe | Faixa de endereços (X) | Indicador de rede | Indicador de host | Nº de redes disponíveis | Nº de hosts disponíveis
-------|-------------------------|------------------|-------------------|-------------------------|----------------------
A | 0 a 127 | X (7 bits) | Y.Z.W (24 bits) | 126 | 16.777.214
B | 128 a 191 | X.Y (14 bits) | Z.W (16 bits) | 16.384 | 65.534
C | 192 a 223 | X.Y.Z (21bits) | W (8bits) | 2.097.152 | 254
D | 224 a 239 | - | - | - | -
E | 240 a 255 | - | - | - | -

</div>

***Observações:*** 
- classes D e E não podem ser utilizadas sendo reservadas. A classe D é reservada para multicast (envio de dados específico para um grupo) e a classe E para pesquisa e desenvolvimento.
- na coluna Indicador de rede:
  - Classe A o primeiro bit sempre vai ser zero, logo 8 bits – 1 =7.
  - Classe B os dois primeiros bits serão 10, logo 16 – 2 = 14.
  - Classe C os três primeiros bits serão 110, logo 24 – 3 = 21.

<div align="center">
<img src="./assets/enderecos-rede-host.png" width="50%">
</div><br>

<details><summary><strong>Dados os endereços de IP 30.56.120.240 e 200.123.6.8 você sabe identificar a
classe de cada um deles?</strong></summary>

- pegar o primeiro octeto e converter para um valor binário. 
- no caso do número 30.56.120.240: 
  - o primeiro octeto é o número 30, então 30 (decimal) = 0001 1110 (binário).
  - analisando o primeiro bit à esquerda que é zero, determinamos que o IP pertence à classe A de endereços.
- segundo número 200.123.6.8:
  -  convertendo 200 para binário, temos 11001000.
  - como os três primeiros bits são um, um e zero (110) temos um IP classe C.
</details>

## Redes Classe A

- utiliza o primeiro octeto para o endereçamento de rede e os três restantes para o endereçamento de host.
- logo, o formato de um número de IP X.Y.Z.W, X corresponde ao endereço de rede e Y.Z.W ao endereço de host.
- a classe A permite somente 126 redes com 16.777.214 hosts. 
  - devido ao grande número de hosts na rede, podemos subdividi-los em sub-redes para poder gerenciar esta rede. 
  - um número elevado de hosts em uma única rede pode levar a alguns problemas como, por exemplo, colisões dentro dessa rede ou um grande
número simultâneo de broadcasts de mensagens, congestionando-a.

página 8