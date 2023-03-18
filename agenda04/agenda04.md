<div align="center">
<a href="https://github.com/monicaquintal" target="_blank"><img align="right" height="100" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg" /></a>
<h2>Estudando MySQL</h2>
<p>Disciplina: Tecnologia da Informação II - ETEC</p>
</div>

<div id="agenda04">
<h2>Agenda 04: Linguagem de Manipulação de Dados - DML (Data Manipulation Language).</h2>
</div>

`DML`: comandos para inserir, alterar e excluir registros nas estruturas do BD.

Nesta aula, será dada continuidade ao exemplo anterior (bd_agenda2).

## Comando `describe`:

Sintaxe:

~~~sql
describe tabela;
~~~

- utilizando os comandos "describe curso;" e "describe professor;", são visualizadas as estruturas das tabelas.

- há outras formas de visualizar a estrutura de uma Tabela pelo quadro SCHEMAS; uma delas é utilizando a opção (ícone de ferramenta) que é apresentada quando posicionamos o ponteiro do mouse sobre o nome da Tabela.

## Inserindo registros: `INSERT INTO`

Sintaxe:

~~~sql
insert into nome_da_tabela  
  (campo1, campo2, campoN)
values 
  (valor1, valor2, valorN)
~~~

Exemplo 1 - **Tabela de Cursos**:

~~~sql
insert into curso (descricao) values ('Sistemas');
insert into curso (descricao) values ('Designer');
insert into curso (descricao) values ('Redes');
~~~

Exemplo 2 - **Tabela de Professores**:

~~~sql
insert into professor
  (nome, dt_nascimento, logradouro, numero, bairro, cidade, uf, cep, salario)
values
  ('José da Silva', '1977-10-03', 'Alameda 5', 1000, 'Centro', 'São Paulo', 'SP', '08150-640', 1800);
~~~

Exemplo 3 - **Tabela de Professores**:

~~~sql
insert into professor
  (nome, dt_nascimento, logradouro, bairro, cidade, uf, cep, salario)
values
  ('Maria de Souza', '1970-12-12', 'Travessa Mato Grosso', 'Bom Retiro', 'São Paulo', 'SP', '01122-010', 1500);
~~~

### Observações:
- Para atribuir um conteúdo a um campo do tipo date, utilizar o formato AAAA-MM-DD.
- quando um campo não tem valor definido ou padrão, é apresentado o valor NULL.
- nesta aula, são utilizadas instruções para alteração e exclusão de registros; para esses casos, há um controle de segurança do Workbench  que não permite alteração e exclusão de registros sem que na cláusula where tenha sido informado um campo chave. Como utilizamos campos que não são chaves, é necessário desabilitar essa configuração (Menu Edit > opção Preferences > desmarcar a opção, que se encontra em SQL Editor > Reiniciar o Workbench).

## Verificando se um registro foi incluído: `SELECT`

Sintaxe:

~~~sql
select * from nome_da_tabela;
~~~

Exemplo:

~~~sql
select * from curso;
~~~

## Alterando registros da tabela: `UPDATE`

Sintaxe: 

~~~sql
update nome_da_tabela
set campo_1 = valor_1
.
.
.
set campo_n = valor_n
where condicao_1 and/or
.
.
.
condicao_n;
~~~

### Importante:
- `WHERE`: cláusula que especifica que uma instrução deve afetar apenas as linhas que atendem aos critérios informados.
- `AND/OR`: operadores lógicos usados para combinar dois ou mais critérios em uma instrução DML ou DQL da Linguagem SQL. Além dos operadores lógicos, podemos usar os operadores relacionais na cláusula where.

Exemplo 1 - **Tabela de Cursos**:

~~~sql
update curso set descricao = 'Designer Web' where codigo = 2;
~~~

Exemplo 2 - **Tabela de Professores**:

~~~sql
update professor
set salario = salario * 1.02
where matricula = 2
and salario <= 1500;
~~~

Exemplo 3 - **Tabela de Professores**:

~~~sql
update professor set
salario = salario * 1.03
where salario < 1400 or
salario > 1700;
~~~

## Excluindo registros da tabela: `DELETE`

Sintaxe:

~~~sql
delete from nome_da_tabela
where condição_1 and/or
.
.
.
condição_n;
~~~

Exemplo:

~~~sql
delete from curso
where codigo = 3;
~~~

<hr>

[Voltar à página inicial!](https://github.com/monicaquintal/disciplina_TI_II_ETEC)