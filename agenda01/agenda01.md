<div align="center">
<a href="https://github.com/monicaquintal" target="_blank"><img align="right" height="100" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg" /></a>
<h2>Estudando MySQL</h2>
<p>Disciplina: Tecnologia da Informação II - ETEC</p>
</div>

<div id="agenda01">
<h2>Agenda 01: Apresentação da Linguagem SQL ANSI.</h2>
</div>

### Relembrando... 

`Modelo Entidade-Relacionamento`: modelo conceitual usado para identificar como as `entidades` (pessoas, objetos ou conceitos) com suas propriedades e características (`atributos`) se relacionam entre si dentro de um sistema (`relacionamento`).

`Diagrama Entidade Relacionamento (DER)`: conjunto de símbolos utilizados para representar a estrutura do banco de dados do sistema que se pretende desenvolver.

### Origem do Modelo Relacional e do SQL:

- Em 1970, Dr. E. F. Codd (do laboratório de pesquisas da IBM) publicou o artigo “A Relational Model of Data for Large Shared Data Banks” (“Um modelo relacional de dados para banco de dados volumosos compartilhados”), que propunha a representação dos dados como conjuntos de tabelas. Em vez de usar ponteiros para navegar entre entidades relacionadas, ***dados redundantes seriam usados para conectar registros em diferentes tabelas***!

- Junto com a definição de Codd, é proposta uma linguagem chamada ***DSL/Alpha*** para manipular os dados em tabelas relacionais. Logo após a publicação do artigo de Codd, a IBM comissionou um grupo para construir um protótipo de suas ideias. Esse grupo criou uma versão simplificada da DSL/Alpha, que foi chamada de ***SQUARE***. Refinamentos da SQUARE levaram a uma linguagem denominada ***SEQUEL***, que foi, finalmente, renomeada para `SQL`. 

- Por volta da década de 1980, o American National Standars Institute (ANSI) começou a trabalhar no primeiro padrão da linguagem SQL, que foi publicado em 1986.

- O último padrão, SQL 2006, focou uma integração entre SQL e XML e define a linguagem chamada Xquery, que é usada para consultar dados em documentos XML.

> A linguagem SQL anda de mãos dadas com o modelo relacional, porque o resultado de uma consulta SQL é uma tabela (também chamada, nesse contexto, de conjunto-resultado ou, em inglês, result set).

***Observação***: SQL não é um acrônimo, apesar de algumas pessoas insistirem que significa “Structure Query Language” (Linguagem Estruturada de Consulta). Ao se referir à linguagem, podemos dizer as letras individualmente (S.Q.L.) ou usar a palavra sequel (pronuncia-se “síquel”). 

### Instalação do Sistema Gerenciador de Banco de Dados MYSQL:

Relizado download e instalação do SGBD MYSQL e ferramenta gráfica Workbench, que utilizaremos em nossos estudos, com base [neste vídeo](https://www.youtube.com/watch?v=TbzfByXwCxk).

### Utilizando MySQL 5.7 Command Line Client:

***Importante***: sempre incluir `“;” (ponto e vírgula)`, pois sua função no MYSQL é a de finalizar a linha de comando, informando que
deverá ser executada após teclar &lt;ENTER&gt;.

***Sintaxe:***

1. Para verificar os Bancos de Dados instalados:

~~~sql
show databases;
~~~

2. Para selecionar um banco de dados:

~~~sql
use nome_banco_de_dados;
~~~

3. Para listar todas as tabelas de um banco de dados:

~~~sql
show tables;
~~~

4. Para criar um banco de dados, utiliza o comando create database ou create schema:

~~~sql
create database nome_do_banco_de_dados; 
create schema nome_do_banco_de_dados;
~~~

***Um detalhe muito importante***: quanto ao recurso `CASE SENSITIVE` (que difere letras maiúsculas de minúsculas), nos computadores com S.O. WINDOWS por padrão não é diferenciado; já em computadores com S.O. LINUX, você poderá ter alguns problemas de adaptação, pois normalmente seus filesystems são CASE SENSITIVE.

5. Para sair da linha de comando do MySQL:

~~~sql
quit;
~~~

[Voltar à página inicial!](https://github.com/monicaquintal/disciplina_TI_II_ETEC)