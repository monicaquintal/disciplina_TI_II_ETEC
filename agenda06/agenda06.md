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

### 1. Topologia Anel (ou token ring)

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

### 2. Topologia Barramento (ou em barra)