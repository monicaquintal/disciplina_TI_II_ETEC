<div align="center">
<a href="https://github.com/monicaquintal" target="_blank"><img align="right" height="100" src="https://www.svgrepo.com/show/204548/wifi-signal-monitor.svg" /></a>
<h1>Estudando Redes de Computadores</h1>
<p>Disciplina: Tecnologia da Informação II - ETEC</p>
</div>

<div id="agenda06" align="center">
<h2>Agenda 07: Modelos de Referência.</h2>
</div>

## Introdução

Nem todas as máquinas são iguais e, para que haja comunicação entre os diferentes tipos de computadores, há necessidade de um tipo de intérprete, que chamamos de `Protocolo`.

O protocolo serve para realizar a comunicação entre os mais variados tipos de computadores e dispositivos sem perda de mensagem.
Se você possui um sistema Linux e deseja mandar um arquivo para um computador Windows, você manda por meio de algum protocolo e o outro sistema conseguirá identificar o arquivo. Obviamente você não vai a um menu e escolher o protocolo, é automático.

Nos tempos mais remotos das redes, quando ainda se começavam a desenvolver os protocolos, não eram seguidos padrões que possibilitassem a interligação entre redes de diferentes arquiteturas (falta de padronização dos componentes; cada fabricante produzia seu hardware e software, que muitas vezes não era compatível com os dos demais fabricantes).

Para solucionar esse problema, foi criado o `modelo OSI` (Open System Interconnection), a fim de padronizar a comunicação entre hardware e software. Esse modelo foi definido pela ISO (International Standards Organization), e foi arquitetado e segmentado em camadas que representam as etapas para que a comunicação ocorra.

<div align="center">

## Modelo OSI/ISO

</div>

- criado em 1971 e formalizado em 1983.
- composto por sete camadas.
  - 7 - aplicação.
  - 6 - apresentação.
  - 5 - sessão.
  - 4 - transporte.
  - 3 - rede.
  - 2 - enlace.
  - 1 - física.
- ***objetivo***: interconectar sistemas abertos a comunicação com outros sistemas. 
- “O modelo OSI em si não é uma arquitetura de rede, pois não especifica os serviços e os protocolos que devem ser usados em cada camada. Ele apenas informa o que cada camada deve fazer”.

<div align="center">
<img src="./assets/modelo-osi-iso.png" width="50%"><br>
<em>Modelo OSI/ISO e suas sete camadas.</em>
</div>

> No modelo OSI/ISO, quando dois dispositivos se comunicam, cada uma das camadas do remetente comunicam-se somente com as camadas correspondentes do receptor, devido ao processo de encapsulamento (com o qual, ao transmitirmos um pacote do computador A para o computador B, cada camada do modelo vai acrescentando cabeçalhos para que as camadas inferiores não precisem trabalhar com as informações das camadas superiores, já encapsuladas/empacotadas). E quando o pacote chega ao computador B esses dados vão sendo desemcapsulados (desempacotados).

Portanto, quando enviamos um dado do computador A, a camada de Aplicação encapsula os dados colocando identificadores e cabeçalhos antes de passar para a camada de Apresentação. A camada de Apresentação faz o mesmo antes de enviar os dados para a camada de Sessão e assim sucessivamente até chegar à camada física onde os dados são transmitidos. 

Chegando ao receptor, o computador B, na camada de Enlace, por exemplo, desencapsula os dados correspondentes a essa camada e os repassa para a camada de Rede, continuando o processo até chegar à camada de Aplicação. Assim, cada camada funciona de maneira independente das outras.

## Camada Física

- ***envolve o hardware e o meio de transmissão*** usados na comunicação de dados.
- define ***qual tipo de meio físico será feita a transmissão de dados*** (fibra ótica, cabo de cobre, sem fio/wireless).
- ***quanto ao hardware***, é definido:
  - se a comunicação será bidirecional ou unidirecional.
  - nível de tensão para representação de um bit 0 e um bit 1.
  - quantidade de tempo (duração) que cada bit leva para ser transmitido.
  - handshake para início e fim das comunicações físicas (processo de início do estabelecimento de uma comunicação, em que são definidos os protocolos de comunicação e a velocidade de transmissão de dados).
  - layout e tamanho dos conectores de rede (incluindo n°. de pinos).
- é a ***camada mais baixa*** do modelo OSI/ISO, na qual há a ***transmissão bruta dos bits*** no canal de comunicação.

## Camada de Enlace

- também chamada de enlace de dados ou link de dados. 
- ***transforma os dados brutos (trem de bits) recebidos pela camada física em um quadro ou frames de dados***, permitindo o acesso de camadas superiores ao meio físico.
- um quadro é montado a partir de padrão especial de bits no início e no fim do quadro que são reconhecidos pela camada de enlace. 
- é nessa camada que os ***erros de transmissão/recepção são tratados***.
- é a ***responsável pelo endereço físico do equipamento***, conhecido como `MAC address`.
- exemplos de equipamentos que trabalham na camada 2 do modelo OSI/ISO: hub e switch não gerenciável.

> O `MAC address` (Media Access Control) é um endereço de 48 bits representado em numeração hexadecimal, e tem que ser único na rede para não haver conflito de endereços.

## Camada de Rede

- uma das mais importantes no modelo OSI. 
- ***responsável por estabelecer o caminho/rota que os dados percorrerão desde a sua origem até o seu destino final***.
  - ***rotas podem ser estáticas ou dinâmicas***. 
  - rotas estáticas sempre seguirão pelo mesmo percurso, independentemente do que aconteça.
  - rotas dinâmicas podem ser alteradas conforme a necessidade (caso o tráfego de dados em uma determinada conexão esteja muito alto e causando congestionamentos na rede, por exemplo).

<div align="center">
<img src="./assets/camada-de-rede.png" width="50%"><br>
<em>Exemplo de rotas de comunicação (Camada de Rede).</em>
</div>

- a camada de rede ***também pode realizar a “tradução” de protocolos de rede*** para que estas se comuniquem.
  - os protocolos mais comuns são: IP, IPX e Apple Talk.
- ao contrário da camada de Enlace que utiliza endereços físicos (MAC), a ***camada de rede utiliza endereços lógicos, como o endereço de IP***.
- roteadores e os switches gerenciáveis l3 atuam na camada de rede.

## Camada de Transporte

- a camada de transporte ***pode segmentar os dados na origem para enviar os dados pelo meio de comunicação e reagrupá-los no destinatário, entregando-os para a aplicação correta.***
- é na camada de transporte que a função de ***QoS (Quality of Service)*** é fornecida.
- os dois protocolos mais comuns da pilha TCP/IP presentes nessa camada são TCP e o UDP.
  - `Protocolo TCP (Transmission Control Protocol)`:
    - é um protocolo do modelo TCP/IP orientado para conexão. 
    - permite que os seguimentos de comunicação sejam entregues de forma ordenada, confiável e com controle de fluxo. 
    - exemplos de aplicações que utilizam esse protocolo são clientes de e-mail, FTP e browsers.
  - `Protocolo UDP (User Datagram Protocol)`:
    - é mais simples que o TCP.
    - também pertencente ao modelo TCP/IP.
    - não é orientado para a conexão e não fornece controle de erros.
    - exemplos de aplicações são Streaming de vídeo e chamadas VoIP.
- é ***responsável pelo endereçamento (número) das portas dependendo da aplicação***.

<div align="center">

Lista de postas mais utilizadas:
Porta (n°.) | Serviço
-----------|-----------
20 | FTP 
23 | Telnet
25 | SMTP
53 | DNS
63 | Whois
80 | HTTP
110 | POP3
119 | NNTP
161 | SNMP
194 | IRC
443 | HTTPS
993 | IMAPS

</div>

## Camada de Sessão

- ***responsável por estabelecer seções entre eles, controlando o diálogo entre as aplicações nos sistemas local e remoto***. 
- uma sessão é uma comunicação entre hosts, permitindo a transferência de dados de forma segura, como utilizando login e senha.

## Camada de Apresentação

- ***responsável por estabelecer a comunicação de duas redes com protocolos distintos***, fazendo com que uma rede TCP/IP comunique-se com outra IPX/SPX, por meio da tradução dos dados. 
- ***faz também a conversão de formatos de dados diferentes*** como por exemplo o ASCII e o Unicode.
- o gateway (“ponte”) que traduz protocolos atua na camada de apresentação.

## Camada de Aplicação

- é a ***camada mais visível para os usuários***. 
- trabalhamos com ela diariamente quando utilizamos programas como clientes de e-mail, mensagens instantâneas, navegadores, entre outros.
- trabalha com diversos protocolos como:
  - DHCP – Dynamic Host Configuration Protocol - responsável pela distribuição de endereços de IP automaticamente.
  - HTTP – HyperText Transfer Protocol – para páginas da internet (web).
  - DNS – Domain Name System – responsável por traduzir nomes para endereços de IP e vice-versa.
  - FTP – File Transfer Protocol – responsável por permitir a transferência de arquivos. 

<div align="center">
<img src="./assets/resumo-camadas.png" width="50%"><br>
<em>Resumo das Camadas do modelo OSI/ISO.</em>
</div>

<div align="center">

## Modelo TCP/IP

</div>

- surgiu devido a uma necessidade do departamento de defesa americano (DoD), que com a ameaça da guerra fria teve receio de ter suas instalações destruídas, suas comunicações interrompidas e seus dados perdidos.
- é um modelo, também arquitetado e estrutural, que propôs resolver o problema da falta de dinâmica da comunicação entre essas instalações.
- pode ser considerado o avô da internet como conhecemos hoje.
- foi desenvolvido no final da década de 1960 e ínício de 70, pelo DoD, para realizar a comunicação entre as unidades militares.
- surgiu de um projeto experimental chamado ***ARPANET*** (Advanced Research Project Agency Network) que valia-se de links de comunicação de alta velocidade utilizando comutação por pacotes.
- em 1972, o uso da ARPANET começou a crescer internacionalmente e se tornou a Internet como conhecemos hoje.

> `IP (Internet Protocol)` é o protocolo de Internet que é responsável pelo endereçamento de dispositivos nas redes para que os dados consigam chegar ao seu destino, conforme o endereço de IP do destinatário.

- o modelo TCP/IP possui 4 camadas (Enlace, Internet, Transporte e Aplicação).

<div align="center">
<img src="./assets/comparacao-iso-ip.png" width="30%"><br>
<em>Comparativo do Modelo OSI/ISO com o TCP/IP.</em>
</div>

## Camada de Enlace

- equivale às camadas 1 e 2 (física e enlace) do modelo OSI.
- é composta pelo hardware, meios de transmissão, níveis de sinais e conexões elétricas; ou seja, ***equipamentos que realizam as conexões físicas dos equipamentos de comunicação***.
- MAC address pertence a esta camada.
- protocolos de enlace como o Ethernet-CSMA/CD, o FDDI e o token-ring são utilizados nessa camada.
  - CSMA/CD (acrônimo de Carrier Sense Multiple Access with Collision Detection): é um protocolo de comunicação que utiliza a tecnologia Ethernet com detecção de colisão na transmissão de dados. Uma colisão ocorre quando duas estações tentam transmitir dados ao mesmo tempo ocasionando perda de dados transmitidos.
  - FDDI (Fiber Distributed Data Interface ou interface de dados distribuídos de fibra óptica): é um padrão para a utilização de cabos de fibra óptica em anel padronizado pela ANSI (American National Standards Institute) para utilização em LANs ou MANs.

## Camada de Internet

- correspondende à camada 3 (rede) do modelo OSI que os endereços lógicos são especificados.
- nesta camada que entra o endereço de rede de origem e destino, como o endereço IP, por exemplo.
- protocolos de roteamento de dados atuam nessa camada. 
- exemplo: protocolos OSPF (Open Shortest Path First) e RIP (Routing Information Protocol), responsáveis por determinar a rota ou caminho que os dados seguirão desde a sua origem até o destino final.

### Qual é a diferença entre o protocolo de roteamento OSPF e o RIP?
- Protocolo OSPF: escolhe a melhor rota dos dados de acordo com a melhor velocidade ou melhor desempenho entre os trechos analisados. 
- protocolo RIP: escolhe a rota com o menor número de hops ou saltos entre a origem e o destino.

## Camada de Transporte

- corresponde à camada 4 (transporte) do modelo OSI.
- sua função é controlar a comunicação fim a fim (host a host). 
- esta camada verifica se os pacotes enviados ou recebidos chegaram na ordem correta, se não estão faltando (perda) ou se tem erros. Caso estejam com algum problema pode solicitar o reenvio dos dados.
- protocolos TCP e UDP situam-se nessa camada.

## Camada de Aplicação

- corresponde às camadas 5, 6 e 7 (Sessão, Apresentação e
Aplicação) do modelo OSI.
- é a responsável pela comunicação através da rede da maioria dos programas como aplicações de gerenciamento de e-mails, navegadores de internet, emuladores de terminais, entre outros.
- na camada de aplicação, temos alguns programas específicos que podem suportar aplicações HTTP, WWW, DNS, FPT e SMTP, por exemplo.
  - HTTP – Hypertext Transfer Protocol ou protocolo de transferência de hipertexto utilizado em páginas da internet.
  - WWW – World Wide Web é um Sistema de documentos na internet que permite o acesso de informações no formato de hipertexto. Hipertexto são documentos digitais que podem conter textos, sons, imagens e vídeos.
  - DNS – Domain Name System ou sistema de nome de domínios. Converte nomes no formato de URL (Uniform Resource Locator), como, por exemplo, http://www.cps.sp.gov.br para endereços de ip (ex.: 192.168.0.1).
  - FTP – File Transfer Protocol ou protocolo de Transferência de arquivos. Permite a troca de arquivos pela Internet.
  - SMTP – Simple Mail Transfer Protocol ou protocolo de transferência de e-mail simples. Permite o envio de e-mails usando a Internet.
  
<div align="center">

## Mas qual modelo atualmente é o mais utilizado?

</div>

Trata-se do ***modelo TCP/IP***.

O modelo OSI de sete camadas é bem didático, pois cada uma delas possui as suas funções e especificações para a comunicação dos dados. Porém, o modelo OSI foi lançado em 1984, depois do TCP/IP (1960 - 1970). A esta altura, o modelo TCP/IP já estava sendo utilizado em diversas universidades de pesquisa e diversos fabricantes começaram a oferecer produtos TCP/IP. Esse foi somente um dentre os diversos fatores para que o modelo TCP/IP saísse vitorioso. Hoje em dia, praticamente todas as comunicações que utilizam a internet valem-se do modelo TCP/IP.

--- 

<div align="center">

## Exercitando e aprimorando

</div>

### 1. Quantas camadas existem respectivamente no modelo OSI e no TCP/IP?

No modelo OSI existem 7 camadas e no modelo TCP/IP existem 4 camadas.

### 2. Por que existe a necessidade de uma padronização das comunicações de dados?

Para que os dispositivos de fabricantes diferentes possam se comunicar entre si, independente da marca ou modelo que os consumidores possuam.

### 3. Qual é a diferença entre os protocolos UDP e TCP?

- Protocolo TCP: orientado para a conexão, fornecendo controle de erros de transmissão e garantindo confiabilidade na transmissão de dados. 
- Protocolo UDP: não é orientado para a conexão, não fornecendo controle de erros de transmissão. Por essa razão, quando um pacote de um protocolo UDP de uma chamada de vídeo, por exemplo, é perdido, temos uma falha momentânea na chamada.

### 4. Explique a diferença entre os protocolos de roteamento OSPF e RIP.

- protocolo de roteamento OSFP: traça a rota dos dados baseado naquela que possuir a maior velocidade ou desempenho.
- protocolo RIP: traça a rota dos dados com base naquela que possuir o menor número de saltos entre a origem e o destino.

### 5. Enumere 5 portas de comunicação e os serviços associados a elas.

<div align="center">

Lista de postas mais utilizadas:
Porta (n°.) | Serviço
-----------|-----------
20 | FTP 
23 | Telnet
25 | SMTP
53 | DNS
63 | Whois
80 | HTTP
110 | POP3
119 | NNTP
161 | SNMP
194 | IRC
443 | HTTPS
993 | IMAPS

</div>

### 6. Qual é a diferença entre um endereço MAC e IP?

- endereço MAC é o endereço físico da interface de rede.
- endereço de IP é o endereço lógico.

--- 

<div align="center">

## Debate

</div>

<em>"Sabemos que os modelos de referência têm grande importância no estabelecimento de padrões de comunicação de dados e todos os desenvolvedores de aplicações necessitam seguir esses padrões para que os seus programas possam se comunicar satisfatoriamente com outros sistemas informatizados. Analise a seguinte situação:

Antônio está desenvolvendo um Sistema de Gerenciamento de Estoque integrado entre diversas filiais de uma empresa no Brasil. Esse sistema deve realizar a comunicação com a matriz que detém os Bancos de Dados para o controle do estoque e com os outros setores da sociedade como, por exemplo, o governo para a emissão de guias fiscais.

Debata com os seus colegas e com o professor mediador a forma como Antônio deve seguir os padrões de comunicação de dados, respeitando os modelos OSI/ISO ou TCP/IP."</em>

### Resposta:

Boa noite,

"Acredito que Antônio deva seguir os padrões de comunicação de dados baseados no modelo TCP/IP, considerando que este é o modelo mais utilizado atualmente em redes de computadores, amplamente utilizado para a comunicação entre sistemas em uma rede.

O modelo OSI/ISO trata-se de um modelo teórico de rede, que define sete camadas para a comunicação de dados. Embora seja útil para estudar e entender os conceitos de redes, não é amplamente utilizado na prática. Por outro lado, o modelo TCP/IP é um modelo mais simples e prático que define quatro camadas, sendo elas: camada de aplicação, camada de transporte, camada de rede e camada física.

O modelo TCP/IP é amplamente utilizado para a comunicação de dados em redes (incluindo a Internet), e é uma boa escolha para comunicação de dados entre diferentes filiais de uma empresa, bem como com outros setores da sociedade, como o governo para a emissão de guias fiscais. Portanto, acredito que seja a forma indicada para Antônio seguir os padrões de comunicação de dados."

---

[Voltar à página inicial!](https://github.com/monicaquintal/disciplina_TI_II_ETEC)