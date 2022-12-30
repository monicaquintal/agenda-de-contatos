<div align="center">
<h1>Agenda de Contatos 📓</h1>
Projeto desenvolvido no capítulo 06 do Nivelamento em Lógica de Programação - FIAP.
</div>

## Definição:

Neste projeto, não serão abordadas as melhores práticas em construção de tabelas/Banco de dados, pois a prioridade é a manipulação dos comandos aprendidos no [Nivelamento](https://github.com/monicaquintal/nivelamentoLogicaDeProgramacao) para fazer as quatro operações fundamentais: cadastro, consulta, alteração e exclusão (CRU),além da listagem dos registros. Vale salientar que essas operações serão feitas em estruturas de memória, ou seja, não serão armazenadas magneticamente no computador.

Para este projeto, utilizaremos a estrutura apresentada:

Campo | Tipo
:-----:|:----:
Nome | Texto
Celular | Texto
e-mail | Texto

## Funcionamento do projeto:

Antes de apresentar os projetos, vale ressaltar que a sistemática de utilização de matriz/listas entre Pseudocódigo, Python e Java são diferentes. As diferenças mais importantes são:

- Vetor e matriz:
  - Pseudocódigo e Java: estruturas estáticas; deve-se definir antes a quantidade de linhas e colunas que armazenarão.
  - Python: estruturas dinâmicas; começam vazias e podem ser inseridos e removidos elementos no decorrer do programa.

- Tipo do vetor e matriz:
  - Pseudocódigo e Java: uma vez definido o tipo dos elementos, todas as células só podem ser daquele tipo.
  - Python: não há tipo definido, cada célula pode conter qualquer tipo de dado.

- Codificação:
  - Pseudocódigo e Java: toda manipulação é feita pelos indices e de forma manual, através de comandos.
  - Python: há comandos/métodos específicos para manipulação das listas, como append() e del(), apesar de também poder tratar pelo índice os elementos já existentes.

Por esse motivo, há construções diferentes dos subalgoritmose do programa principal (do projeto) em Pseudocódigo e Java (que são similares) com a construção do código Python.

O programa:

~~~
---------- M E N U ----------

1 - Adicionar novo contato
2 -Editar contato
3 -Pesquisar contato
4 -Lista de contatos
5 -Apagar um contato
6 -Sair

Escolha uma opção: _
~~~