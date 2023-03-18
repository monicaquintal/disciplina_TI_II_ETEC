<div align="center">
<a href="https://github.com/monicaquintal" target="_blank"><img align="right" height="100" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg" /></a>
<h2>Estudando MySQL</h2>
<p>Disciplina: Tecnologia da Informação II - ETEC</p>
</div>

<div id="agenda05">
<h2>Agenda 05: Linguagem de Consulta de Dados - DQL (Data Query Language).</h2>
</div>

## Comando `SELECT`

Utilizado quando é necessário buscar informações no Banco de Dados.

### Sintaxe:

~~~sql
select campo1, campo2, campoN
from tabela1
where condicao1 and condicaoN
order by campo asc/desc;
~~~

### Onde:

- `ASC`: resultados apresentados em ordem ascendente.
- `DESC`: resultados apresentados em ordem descendente.

### Outros Operadores:

1. `between`: "entre". Utilizado para obter intervalos de dados.
2. `in`: utilizado para obter valores específicos de uma lista.
3. `like`: faz a busca de conteúdos parecidos ou semelhantes.


### Adicionando novos registros à tabela:

~~~sql
insert into professor(nome, dt_nascimento, logradouro, bairro, cidade, uf, cep, salario) values ('João de Souza', '1970-12-12', 'Travessa Mato Grosso', 'Bom Retiro', 'São Paulo', 'SP', '01122-010', '1530.00');
insert into professor(nome, dt_nascimento, logradouro, numero, bairro, cidade, uf, cep, salario) values ('Ana Maria', '1976-06-14', 'Alameda Dom Pedro I', '432', 'Independência', 'São Paulo', 'SP', '04470-010', '1812.80');
insert into professor(nome, dt_nascimento, logradouro, numero, bairro, cidade, uf, cep, salario) values ('Marilda Dutra', '1979-01-23', 'Rua Adolfo Belini', '621', 'São Francisco', 'São Paulo', 'SP', '01005-020', '1480.00');
insert into professor(nome, dt_nascimento, logradouro, numero, bairro, cidade, uf, cep, salario) values ('Acácio Moura', '1985-04-29', 'Avenida General Costa e Silva', '908', 'Vila Militar', 'São Paulo', 'SP', '06442-007', '1340.00');
~~~

### Exemplos:

~~~sql
select matricula, nome from professor;
/* seleciona apenas os campos matricula e nome da tabela professor */

select * from professor;
/* seleciona todos os campos da tabela */

select * from professor where salario > 1600;
/* seleciona registros que atendam ao critério estabelecido*/

select * from professor where salario between 1000 and 1600;
/* critério estabelecido: salário ENTRE 1000 e 1600 */

select * from professor where matricula in (3, 4);
/* critério estabelecido: matrículas nas posições 3 e 4 */

select * from professor where matricula in (3, 4) order by salario;
/* matrículas nas posições 3 e 4, ordenadas por salário (o padrão é ordenar de modo ascendente) */

select * from professor order by salario desc;
/* seleciona todos os campos da tabela professor por ordem decrescente de salario */

select * from professor where nome like 'A%';
/* seleciona todos os professores cujo campo nome inicia-se com a letra “A” */

select * from professor where nome like '%O';
/* seleciona todos os professores cujo campo nome termina com a letra “O”, independente do que está preenchido antes */

select * from professor where nome like '%ri%';
/* retorna nomes que contenham os caracteres “ri”, independente do que está antes ou depois de deles */
~~~

## Cláusula Distinct

Utilizada para distinguir conteúdos, ou mesmo verificar quais conteúdos foram definidos para um ou mais campos.

Exemplo:

~~~sql
update professor set logradouro = 'Avenida São Bernardo', numero = 127, bairro = 'Vila Luzita', cidade = 'Santo André', uf = 'SP', cep = '09171-195' where matricula = 5;

select distinct cidade from professor;
~~~

## Junção `JOIN`

Permitem criar consultas mais avançadas: conectar registros de tabelas diferentes, formando um resultado de pesquisa composto (uma consulta retornará registros compostos por diversas colunas, de tabelas diferentes, desde que os registros entre elas se relacionem).

Exemplo:

~~~sql
select p.nome, pt.numero
from professor p inner join professor_telefone pt
  on p.matricula = pt.matricula
order by p.matricula;

/*
p: também chamado de alias, é um apelido dado à Tabela (neste caso,tabela professor).
pt: apelido dado à tabela professor_telefone
*/
~~~

- `inner join`: tipo de junção interna mais utilizado; se um valor existe em uma Tabela mas não existe na outra, a junção falha, e esses registros não são exibidos no resultado.

### Juntando 3 ou mais tabelas:

- Para juntar duas tabelas, utilizamos somente um tipo de junção na cláusula from, além de uma única subcláusula on. 

- Quando temos que juntar três tabelas, devemos utilizar dois tipos de junção na cláusula from, além de duas subcláusulas on.

~~~sql
select p.matricula, p.nome, c.descricao
from professor p
inner join curso_professor cp
  on p.matricula = cp.matricula_prof
  inner join curso c
  on cp.codigo_curso = c.codigo
where c.codigo = 1
order by p.matricula;
~~~

## Funções de agregação

- max () : retorna o maior valor dentro de um conjunto.
- min () : retorna o menor valor dentro de um conjunto.
- avg () : retorna o valor médio de um conjunto.
- sum () : retorna a soma dos valores de um conjunto.
- count () : retorna a quantidade de valores em um conjunto.

Exemplo:

~~~sql
select max(p.salario) maior_salario,
  min(p.salario) menor_salario,
  avg(p.salario) media_salarios,
  sum(p.salario) total_salarios,
  count(*) quant_professores
from professor p;
~~~

Para incrementar a utilização das funções de agregação, podemos incluir outras cláusulas:
- group by: usada para agrupar os registros por meio de conteúdos comuns de campos.
- having: filtra grupos indesejados.

~~~sql
select p.cidade,
  count(*) quant_professores
from professor p
group by p.cidade;
~~~

~~~sql
select p.cidade,
  sum(p.salario) total_salarios
from professor p
group by p.cidade
having count(*) > 1;
~~~


<hr>

[Voltar à página inicial!](https://github.com/monicaquintal/disciplina_TI_II_ETEC)