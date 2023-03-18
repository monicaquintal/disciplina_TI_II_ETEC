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
~~~

## Importante:

- O caractere “%”, significa que não importa quais serão os próximos caracteres (no exemplo, o importante é que o nome comece com “A”,independente do conteúdo após essa letra).

página 09