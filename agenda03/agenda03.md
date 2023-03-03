<div align="center">
<a href="https://github.com/monicaquintal" target="_blank"><img align="right" height="100" src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg" /></a>
<h2>Estudando MySQL</h2>
<p>Disciplina: Tecnologia da Informação II - ETEC</p>
</div>

<div id="agenda03">
<h2>Agenda 03: Comandos SQL e Linguagem de Definição de Dados.</h2>
</div>

## Praticando com a ferramenta Workbench

### Exemplo:

Utilizar o contexto de uma escola que necessita gerenciar o cadastro de seus professores.
1. O professor pode ter vários telefones e lecionar em vários cursos;
2. Um curso pode ter vários professores;
3. Um telefone não pode ser cadastrado para o mesmo professor mais de uma vez, assim como um professor não pode estar vinculado mais de uma vez a um curso.

### Mapeamento:

**Curso**: codigo e descricao.
**Professor**: matricula, nome, dt_nascimento, logradouro, numero, bairro, cidade, uf, cep e salário.
**Professor Telefones**: professor_fone_id, matricula e numero.
**Curso Professores**: curso_prof_id, codigo_curso e matricula_prof.

### Implementando o Banco de Dados

1. Pela janela de SQL, digite:

~~~sql
create database bd_agenda2;
~~~

***OU***

2. Botão direito do mouse no quadro Schemas > Create Schema > Insira o nome do BD > confirmar

### Selecionando o Banco de Dados criado:

1. Pela janela do SQL:

~~~sql
use bd_agenda2;
~~~

***OU***

2. Clique duplo sobre o Banco de Dados bd_agenda2, no quadro Schemas.

### Criando tabelas:

1. Pela janela do SQL:

~~~sql
create table curso (
	codigo integer(3) not null auto_increment,
    descricao varchar(50) not null,
    constraint pk_curso primary key (codigo),
    constraint uk_cur_desc unique key (descricao)
);

create table professor (
	matricula int(5) not null auto_increment,
    nome varchar(80) not null,
    dt_nascimento date not null,
    logradouro varchar(50) not null,
    numero varchar(10),
    bairro varchar(30) not null,
    cidade varchar(40) not null,
    uf varchar(2) not null,
    cep varchar(9) not null,
    salario double(10,2) default 0,
    constraint pk_professor primary key (matricula)
);

create table professor_telefone (
	professor_fone_id int(10) not null auto_increment,
    matricula int(5) not null,
    numero varchar(15) not null,
    constraint pk_professor_telefone primary key (professor_fone_id),
    constraint fk_pt_matricula foreign key (matricula) references professor (matricula),
    constraint uk_pt_mat_tel unique key (matricula, numero)
);

create table curso_professor (
	curso_prof_id int(10) not null auto_increment,
    codigo_curso int(3) not null,
    matricula_prof int(5) not null,
    constraint pk_curso_professor primary key (curso_prof_id),
    constraint fk_cp_cod_curso foreign key (codigo_curso) references curso (codigo),
    constraint fk_cp_mat_prof foreign key (matricula_prof) references professor (matricula),
    constraint uk_cp_cur_mat unique key (codigo_curso, matricula_prof)
);
~~~

***OU***

PÁGINA 12