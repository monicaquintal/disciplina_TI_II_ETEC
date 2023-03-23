<div align="center">
<a href="https://github.com/monicaquintal" target="_blank"><img align="right" height="100" src="https://www.svgrepo.com/show/204548/wifi-signal-monitor.svg" /></a>
<h1>Estudando Redes de Computadores</h1>
<p>Disciplina: Tecnologia da Informação II - ETEC</p>
</div>

<div id="agenda06" align="center">
<h2>Agenda 06: Fundamentos da Rede de Computadores.</h2>
</div>

## Introdução

- redes foram desenvolvidas pela necessidade de transmitir dados a longas distâncias entre os computadores. 
- a Internet nasceu de um projeto chamado de `ARPANet` (Advanced Research Projects Agency Network) do departamento de defesa dos Estados Unidos que interligava as bases militares.

<div align="center">

## Topologias de Rede

</div>

> A `Topologia de Redes` descreve como é estruturada uma rede de computadores, tanto física como logicamente.

- ***Topologia Física***: descreve como as redes estão conectadas fisicamente pelos cabos.
- ***Topologia Lógica***: descreve como os dados são transmitidos e trafegam pela rede (fluxo de dados entre os computadores que compõe a rede).

## Topologias Físicas de Rede

Há alguns tipos distintos de topologias físicas de rede de computadores, podendo apresentar diferentes classificações: Anel, Barramento, Estrela, Malha, Árvore e Híbrida. 

<em>Nesta agenda, foram estudadas as topologias Anel, Barramento e Estrela.</em>

### 1. `Topologia Anel` (ou token ring)

- é composta por uma rede interligada de computadores ou equipamentos de redes (chamados de nós) em forma de anel.
- este anel é composto por um conjunto de ligações ponto a ponto individuais que formam um círculo.
- a comunicação nesse tipo de topologia é controlada por um token (ou ficha) = token ring. 
  - o token controla quem pode transmitir a informação na rede. 
  - a ficha fica circulando na rede e o computador que deseja transmitir a informação captura o token e inicia a  transmissão de dados > os dados circulam pelo anel até o destinatário > os dados continuam a circular pelo anel, até que o emissor os retire > quando o transmissor acabar o envio de informações, ele libera o token na rede para outro nó poder executar a comunicação. 
- ***importante***:
  - conforme o número de estações aumenta, o congestionamento para a transmissão de dados também cresce, uma vez
que somente um nó pode transmitir por vez. 
  - cada computador deve ter 2 placas de rede para fazer a comunicação.
  - caso haja um problema nos cabos que ligam o anel ou em uma estação (ou algum tupo de ruptura de conexão), a rede pode parar de funcionar.

### 2. `Topologia de Barramento` (ou em barra)

- todos os computadores são ligados fisicamente a um mesmo cabo. 
- somente um computador pode realizar a transmissão de dados, sem que haja colisão. 
- se o cabo que compõe a barra falhar, a rede para de funcionar!
- os cabos utilizados nessa topologia são: coaxiais 10Base2 e 10Base5.

### 3. `Topologia Estrela`

- os nós de rede são conectados a um dispositivo concentrador chamado ***switch***, que faz a tarefa de recepção dos dados, para o posterior envio destes para o destinatário.
- há duas opções:
  - switch: sabe todas as máquinas que estão conectadas a ele (ip).
  - hub: não sabe quais são (ou se há) computadores conectados, encaminhando para todas as máquinas o mesmo pacote.
- ***vantagens***: 
  - o switch encaminha o dado somente para o computador de destino e não para toda a rede como nas duas topologias anteriores. Logo, a rede funciona de modo muito mais eficiente. 
  - caso haja um problema em um dos cabos, somente a estação cujo cabo houve problema é prejudicada, enquanto a rede continua funcionando normalmente.

### Comparando:

Topologia / Características | Estrela | Anel | Barramento
-----------------------------|--------|-------|------------
Simplicidade funcional | Melhor | Razoável | Razoável (melhor que o anel)
Roteamento | Inexistente | Inexistente no anel unidirecionado, simples nos outros tipos | Inexistente
Custo de conexão | Alto | Baixo para médio | Baixo
Crescimento incremental | Limitado à capacidade do nó central | Teoricamente infinito | Alto
Aplicação adequada | Aquelas envolvendo processamento | Sem limitação | Sem limitação
Desempenho | Baixo, todas as mensagens precisam passar pelo nó central | Alto, possibilidade de mais de uma mensagem ser transmitida ao mesmo tempo | Médio
Confiabilidade | Pouca | Boa, desde que sejam tomados cuidados adicionais | A melhor de todas; interface passiva com o meio
Retardo de transmissão | Médio | Baixo, podendo chegar a não mais do que 1 bit por nó | O mais baixo de todos
Limitação quanto ao meio de transmissão | Nenhuma, ligação ponto-a-ponto | Nenhuma, ligação ponto-a-ponto | Devido à ligação multiponto, sua ligação ao meio de transmissão pode ser de custo elevado

<div align="center">

## Classificação de Redes de Computadores

</div>

As redes de computadores podem também ser classificadas conforme a sua extensão geográfica.

### Classificações:

1. ***PAN***:

- Personal Area Network ou rede de área pessoal.
- é uma rede de computadores doméstica que interliga computadores pessoais, impressoras, dispositivos móveis, etc.
- possui alcance limitado, geralmente em metros.
- pode utilizar equipamentos de rede comuns.
- pouca possibilidade de expansão.
- exemplos: Interligação entre dispositivos móveis como computadores, smartphones, tablets etc.

2. ***LAN***:

- Local Area Network ou redes de área local. 
- é a mais conhecida e permite interligar computadores, servidores e outros equipamentos de rede numa área geográfica limitada.
- operam em velocidades entre 10Mbps e 1Gbps.
- exemplos: Interligação de equipamentos de um escritório, escola, empresa, prédio ou conjunto de prédios. 

3. ***MAN***:

- Metropolitan Area Network ou rede de área metropolitana.
- interconecta diversos negócios.
- ode ter um tamanho de dezenas de quilômetros.
- em geral, as conexões de uma MAN são feitas por cabos de fibra óptica. 
- exemplo: pode interligar uma rede de lojas em uma região metropolitana. Um exemplo de MAN são as empresas de
TV a cabo.

4. ***WAN***:

- Wide Area Network ou rede de longa distância. 
- utilizadas para a interconexão de redes menores como LANs e MANs. 
- podem se estender desde cidades inteiras, passando por estados, países, até continentes. 
- um exemplo de WAN é a Internet.

<div align="center">

![Classificação de Redes de Computadores](./assets/classificacao-redes.png)<br>
<em>Classificação de Redes de Computadores.</em>

</div>

<div align="center">

## Meios de Transmissão

</div>

Os meios de transmissão de dados podem ser por cabos de metal, fibra óptica e sem fio.

## Cabos de metal:

- utilizam energia para o transporte de dados.
- são os mais simples. 
- podem ser do tipo coaxial ou par trançado:
  - ***CABO COAXIAL***: 
    - composto por um núcleo de cobre, envolto por uma malha externa de metal, separados por um material isolante.
    - foram muito utilizados em redes com topologia barramento.
    - ainda são utilizados para a conexão de antenas de televisão a TVs. 
    - possuem uma “blindagem” natural a ruídos externos devido a seu tipo de construção.
  - ***CABO DE PAR TRANÇADO*** ou ETHERNET:
    - composto por 4 pares de fios trançados dois a dois em espiral para reduzir o ruído eletromagnético. 
    - são classificados em categorias que vão de 1 a 7, que indicam a qualidade do cabo e a frequência máxima de transmissão de dados suportada por eles. 
    - atualmente, são mais utilizados os cabos de categoria 5e que suportam a transmissão de dados até 1Gbps. Porém, estes cabos estão sendo substituídos pelos de categoria 6 e 6a que suportam transmissões até 10Gbps.
    - existem também os cabos ethernet blindados e sem blindagem. Os cabos sem blindagem são chamados de UTP (Unshielded Twistes Pair) e os blindados são divididos em três categorias: FTP (Foiled Twisted Pair), STP (Shilded Twisted Pair) e SSTP (Screened Shilded Twisted Pair) ou SFTP(Screened Foiled Twisted Pair).
    - Para cabos ethernet são utilizados os conectores 8PC8, conhecidos como RJ45.

## Cabos de fibra óptica

- usam luz para o transporte de dados.
- é imune a interferências eletromagnéticas.
- tem um custo maior de implantação e manuseio. 
- possuem velocidade de transmissão de dados muito superior, além de atingirem distâncias maiores de transmissão de informações sem a necessidade de regeneração do sinal.

## Sem fio (wireless)

- os dados são transmitidos sem a utilização de fios, utilizando ondas eletromagnéticas através do ar. 
- são utilizados equipamentos chamados de roteadores sem fio ou access points (pontos de acesso) que convertem os dados de uma rede cabeada tradicional para Wifi. 

</div>

<div align="center">

## Equipamentos de Rede

</div>

### 1. MODEM:

- seu nome provém da junção das palavras modulador e demodulador. 
- é um equipamento capaz de aceitar uma comunicação serial de entrada, produzindo uma portadora modulada na saída (converte sinais digitais em analógicos), no caso de modens de conexão discada ou ADSL.

### 2. Hub:

- funciona como se fosse uma multiplicador de portas de rede.
- toda a informação que entra por uma porta é replicada para todas as demais, atingindo todas as estações da rede. 
- podia provocar sobrecarga na rede pois, ao invés de somente o receptor das mensagens receber os dados, esses eram recebidos por toda a rede, durante o tempo dessa transmissão, e a rede permanecia ocupada para o envio e recebimento de
dados por parte de outros terminais. 
- atualmente não são mais utilizados.

### 3. Switch:

- usado para interligar os computadores, impressoras e dispositivos de redes. 
- é uma evolução do hub, cuja função também era a de interconectar os nós de rede.
- podem determinar qual estação de rede está interligada, por meio da análise dos dados que trafegam em suas portas e enviar os dados somente para a estação de destino e não para toda a rede, diminuindo o tráfego da rede e proporcionando  maior eficiência.

### 4. PATCH PANEL:

- utilizado para organizar os cabos, possibilitando a fácil identificação e proteção dos cabos de rede nos racks. 
- utilizados para fazer a conexão entre o cabeamento que sai do rack e chegam às tomadas (cabeamento horizontal) ou em outro patch panel interligando outro rack (cabeamento vertical).

### 5. ROTEADORES:

- equipamentos que fazem a conexão de redes distantes entre si ou que operam com protocolos diferentes. 
- responsáveis pelo encaminhamento dos dados através da rede de acordo com o endereço fornecido pelo protocolo da camada de rede ao enviar um pacote.
- são equipamentos mais inteligentes que os switches porque operam na camada de rede do modelo OSI/ISO.
- capazes de analisar o endereço de rede do destinatário antes de encaminhar os pacotes para a porta correta.
- permitem que redes de diferentes tipos possam ser interconectadas, pois podem fazer a tradução de protocolos para essa intercomunicação.
- controlam o tráfego na internet, decidindo por qual caminho os dados trafegarão entre a origem e o destino.
 
### 6. ACCESS POINTS (AP)

- equipamentos que transformam o sinal de uma rede ethernet cabeada em sinal de rede sem fio, popularmente conhecida como wi-fi.
- para utilização em ambientes domésticos, a fim de simplificar e diminuir a quantidade de dispositivos, os fabricantes de equipamentos condensaram os modens, roteadores e APs em um único equipamento. Dessa forma, utilizamos apenas um modem/roteador que é capaz de interligar todos os dispositivos de nossa residência.

---

<div align="center">
<h2>Exercícios</h2>
</div>

1. Diferencie uma PAN de uma LAN.

> LAN: rede de área local comumente utilizada por empresas. PAN: possui tecnologicamente a mesma estrutura de uma LAN, porém é para uso pessoal dentro de uma residência, por exemplo, com uma baixa capacidade de expansão.

2. Pensando nos equipamentos de interconexão de redes, qual é a diferença entre um hub e um switch?

> Um hub repassa todas as informações recebidas em suas portas para todos as estações de uma rede assim como faz um famoso “benjamim” que colocamos na tomada para aumentar o número de tomadas. Já o Switch analisa o nó que está conectado às suas portas, bem como parte do pacote de dados que trafega por ele para determinar o seu destinatário e enviar os dados somente para quem deve recebê-los. Dessa forma, ele diminui o tráfego desnecessário de informações em uma rede de computadores.

3. Explique a função do token na rede em anel?

> O token em uma rede em anel tem a função de indicar quem pode realizar a transmissão de dados, uma vez que somente um computador pode enviar uma informação por vez.

4. O que diferencia um cabo de rede ethernet blindado de um sem blindagem.

> Cabo UTP ou sem blindagem não possui uma folha de metal que previne ou minimiza a interferência nos dados que por ele trafegam como nos cabos blindados (FTP, STP, SFTP, SSTP).

5. Explique um motivo da fibra ótica transmitir dados de modo mais eficiente que
condutores metálicos.

A fibra óptica consegue transmitir dados a uma velocidade maior, primeiramente por utilizar a luz para transmissão, ao passo que condutores metálicos utilizam eletricidade. Pelo fato de utilizarem luz, os dados são imunes a interferências
eletromagnéticas como nos cabos metálicos.

6. Como utilizar os Roteadores ou os Access Points nas seguintes situações:
  a. Moro num prédio e preciso evitar a interferência de sinais dos meus vizinhos;

  > Para evitar a interferência de sinais dos vizinhos, devemos realizar a análise dos canais de wifi que estão sendo utilizados por eles. Para isso devemos utilizar um programa que realiza uma varredura nos canais sem fio e apresenta-os em forma de gráfico. Um APP para celulares e tablets Android fácil de se obter é o Wi-Fi analyzer apresentando um gráfico 

  b. Tenho um roteador na Sala de TV da minha casa, mas o sinal se torna fraco no quarto.
  c. Possuo uma rede cabeada e quero disponibilizar internet sem fio (Wi-fi).
7. Preciso montar uma rede no laboratório de informática de uma Etec. Qual a
topologia de rede mais indicada para esse caso? Por quê?
8. De que forma o mundo é conectado? Como os dados conseguem trafegar entre
os continentes?
