1 A escolha de SGBD é motivada pela consistencia rigosa ,onde as propiedades acid são inegociaveis para integridade de dados ,
   Quando os dados são estruturados, possuem esquemas definidos e relacionamentos complexos, um SGBD Relacional é superior porque garante
   o uso de esquemas , em vez do esquema padrao em engenharia de dados é uma pratica comum para garantir segurança e organizaçao


# Projeto de Normalização de Banco de Dados

## 1ª Forma Normal (1FN)

A planilha foi analisada e já se encontrava na Primeira Forma Normal (1FN), pois não apresentava atributos multivalorados nem grupos repetitivos. Cada campo possuía valores atômicos.

## 2ª Forma Normal (2FN)

Foram identificadas dependências parciais na tabela original, onde atributos como nome, email e cidade dependiam apenas do identificador do aluno.

Para atender à 2FN, os dados foram decompostos nas seguintes entidades:

* ALUNO
* DISCIPLINA
* PROFESSOR
* TURMA

## 3ª Forma Normal (3FN)

Foram removidas dependências transitivas, especialmente a relação entre disciplina e professor. Assim, foi criada a entidade intermediária OFERTA_DISCIPLINA para representar a oferta de uma disciplina por um professor em uma turma.

---

# Modelo Lógico

## Tabela: ALUNO

* id_aluno (PK)
* nome
* email
* cidade

## Tabela: DISCIPLINA

* id_disciplina (PK)
* nome
* carga_horaria

## Tabela: PROFESSOR

* id_professor (PK)
* nome

## Tabela: TURMA

* id_turma (PK)

## Tabela: OFERTA_DISCIPLINA

* id_oferta (PK)
* id_disciplina (FK)
* id_professor (FK)
* id_turma (FK)

## Tabela: MATRICULA

* id_matricula (PK)
* id_aluno (FK)
* id_oferta (FK)

---

# Relacionamentos

* Um ALUNO pode ter várias MATRÍCULAS (1:N)
* Uma MATRÍCULA pertence a uma OFERTA_DISCIPLINA (N:1)
* Uma DISCIPLINA pode ter várias OFERTAS (1:N)
* Um PROFESSOR pode ministrar várias OFERTAS (1:N)
* Uma TURMA pode ter várias OFERTAS (1:N)
  
