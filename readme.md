<div align="center">
<h1>Agenda de Contatos 📓</h1>
Projeto desenvolvido no capítulo 06 do Nivelamento em Lógica de Programação - FIAP.
</div>

## Definição:

Neste projeto, não serão abordadas as melhores práticas em construção de tabelas/Banco de dados, pois a prioridade é a manipulação dos comandos aprendidos no [Nivelamento](https://github.com/monicaquintal/nivelamentoLogicaDeProgramacao) para fazer as quatro operações fundamentais: cadastro, consulta, alteração e exclusão (CRU),além da listagem dos registros. Vale salientar que essas operações serão feitas em estruturas de memória, ou seja, não serão armazenadas magneticamente no computador.

Para este projeto, utilizaremos a estrutura apresentada:

Campo       |       Tipo
:----------:|:-----------:
Nome        |       Texto
Celular     |       Texto
e-mail      |       Texto

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
2 - Editar contato
3 - Pesquisar contato
4 - Lista de contatos
5 - Apagar um contato
6 - Sair

Escolha uma opção: _
~~~

## Pseudocódigo:

### Subalgoritmos:

1. limpar_matriz (matriz[]][]: Texto)

    - Descrição: Este procedimento limpa a matriz;
    - Nome: limpar_matriz(matriz[]][]: Texto);
    - Tipo: void.

~~~
Procedimento limparMatriz(mm[][]: Texto)
Var
  l, c: inteiro
início
  // Insere vazio em todas as células da matriz
  para l de 0 até 10 inc 1 faça
    para c de 0 até 10 inc 1 faça
      mm[l][c] = ""
    fim_para
  fim_para
Fim
~~~

2. novo(matriz[][]: Texto, l: inteiro)

    - Descrição: Este procedimento cadastra um novo contato
    - Nome: novo(matriz[][]: Texto, l: inteiro)
    - Tipo: void

~~~
Procedimento novo(mm[][]: Texto, l: inteiro)
Início
  // Pede ao usuário a edição dos campos da linha por parâmetro
  Escreva "------------ PREENCHA O NOVO CONTATO: "
  Escreva "Nome.........: "
  Leia mm[l][0]
  Escreva "Celular......: "
  Leia mm[l][1]
  Escreva "E-mail.......: "
  Leia mm[l][2]
Fim
~~~

3. editarContato(matriz: Texto, l: inteiro)

    - Descrição: Este procedimento edita um contato
    - Nome: editarContato(matriz: Texto, l: inteiro)
    - Tipo: void

~~~
Procedimento editarContato(mm[][]: Texto, l: inteiro)
Início
  // Permite ao usuário editar o contato encontrado
  // Não permite que o nome seja editado por ser a chave
  Escreva "------------ EDITE O CONTATO: "
  Escreva "Nome.........: ", mm[l][0]
  Escreva "Celular......: "
  Leia mm[l][1]
  Escreva "E-mail.......: "
  Leia mm[l][2]
Fim
~~~

4. linhaProximoContato(matriz[][]: Texto)

    - Descrição....: Esta função retorna a próxima linha em branco da matriz
    - Nome.........: linhaProximoContato(matriz[][]: Texto)
    - Tipo.........: void

~~~
Função linhaProximoContato(mm[][]: Texto): Inteiro
Var
  l: inteiro
Início
  para l de 0 até 10 inc 1 faça
    Se mm[l][0] == "" então
      // caso tenha encontrado, retorne o número da linha
      // próxima linha vazia
      retorne l
    Fim_se
  Fim_para
        // -1 representa a matriz estar cheia
  Retorne -1
Fim
~~~

5. exibirContato(matriz[][]: Texto, l: inteiro)

    - Descrição: Este procedimento exibe um contato
    - Nome: exibirContato(matriz[][]: Texto, l: inteiro)
    - Tipo: void

~~~
Procedimento exibirContato(mm[][]: Texto, l: inteiro)
Início
  // Exibe o registro da linha passada por parâmetro
  Escreva "Nome........: ", mm[l][0]
  Escreva "Celular.....: ", mm[l][1]
  Escreva "E-mail......: ", mm[l][2]
Fim
~~~

6. listarAgenda(matriz[][]: Texto)

    - Descrição: Este procedimento lista todos os contatos
    - Nome: listarAgenda(matriz[][]: Texto)
    - Tipo: void

~~~
Procedimento listarAgenda(mm[][]: Texto)
Var
  l: inteiro
Início
  Escreva "------------ CONTATOS DA AGENDA: "
  para l de 0 até 10 inc 1 faça
    // Enquanto tiver registro, exibe-o
    Se mm[l][0] != "" Então
      exibirContato(mm, l)
      Escreva "------------------------------------------"
    Fim_se
  Fim_para
  Escreva "
------------ FIM DA AGENDA: "
Fim
~~~

7. pesquisarContato(matriz[][]: Texto, nome: Texto)

    - Descrição: Esta função pesquisa o contato e retorna a linha
    - Nome: pesquisarContato(matriz[][]: Texto, nome: Texto)
    - Tipo: inteiro (retorna -1 se não encontrou)

~~~
Função pesquisarContato(mm[][]: Texto, n: Texto): Inteiro
Var
  l: inteiro
Início
  // caso encontre o contato, retorna a linha onde ele está
  para l de 0 até 10 inc 1 faça
    Se mm[l][0] == n Então
      retorne l
    Fim_se
  // Se não encontrou o contato, retorna -1
  retorne -1
Fim
~~~

8. ExcluiLinha(String matriz, l: inteiro)

    - Descrição: Este procedimento exclui a linha passada por parâmetro
    - Nome: ExcluiLinha(String matriz, l: inteiro)
    - Tipo: void

~~~
Procedimento excluiLinha(mm[][]: Texto, l: inteiro)
Início
  // exclui o contato a partir da linha passada por parâmetro
  mm[l][0] = ""
  mm[l][1] = ""
  mm[l][2] = ""
  Escreva "Contato Excluído"
Fim
~~~

9. apagarContato(String matriz, String nome)

    - Descrição: Este procedimento pesquisa e exclui um contato
    - Nome: apagarContato(String matriz, String nome)
    - Tipo: void

~~~
Procedimento apagarContato(mm[][]: Texto, n: Texto)
Var
  Achou: Lógica
  opcao: Texto
  linha: Inteiro
Início
  // inicia a variável, achou como false
  achou = Falso
  // alimenta a linha com o valor da pesquisa (-1 não encontrou)
  linha = pesquisarContato(mm, n)
  Se linha != -1 então
    // Exibe o contato a partir da linha
    exibirContato(mm,linha)
    // Confirma com o usuário se ele quer excluir ou nao o contato
    Escreva "Confirma a exclusão do contato?
[S]im ou [N]ão?"
    Leia opcao
    Se opcao == "s" ou opcao == "S" Então
      // se a escolha for Sim, exclui o contato
      excluiLinha(mm, linha)
    else
      // Cancela a exclusão
      Escreva "Exclusão cancelada!"
    Fim_se
  senão
    // contato não encontrado
    Escreva "Contato não encontrado!"
  Fim_se
Fim
~~~

10. exibeMenu(String opcao)

    - Descrição: Este procedimento lista as opções do Menu
    - Nome: exibeMenu(String matriz, String nome)
    - Tipo: void

~~~
Procedimento exibeMenu()
Início
  Escreva "********* M E N U ********"
  Escreva "1 - Adicionar novo contato"
  Escreva "2 - Editar contato"
  Escreva "3 - Pesquisar contato"
  Escreva "4 - Lista de contatos"
  Escreva "5 - Apagar um contato"
  Escreva "6 - Sair"
Fim
~~~

### Programa principal:

~~~
Programa Agenda_de_contato
Var
  // variáveis e objetos públicos
  agenda[10][3]: Texto
  opcao, linha: inteiro
  nome: Texto
Início
  // ao iniciar a aplicação, sempre é bom limparmos a matriz para
  // que a "sujeira" do Buffer não influencie nos resultados
  limparMatriz(agenda)

  faça
    // Exibição do menu
    exibeMenu()

    // Colhe a opção escolhida pelo usuário
    Escreva "Escolha uma opção:"
    Leia opcao

    // Seleciona a opção escolhida
    Escolha(opcao)

      // Caso a escolha seja "adicionar novo contato"
      caso 1:
        // Retorna a próxima linha disponível antes de
        // incluir o novo contato
        novo(agenda, linhaProximoContato(agenda))


      // Caso a escolha seja "Editar contato"
      caso 2:
        Escreva "--------- EDITANDO (PESQUISE O CONTATO): "
        Escreva "Digite o nome.........:"
        nome = entrada.next(
        linha = pesquisarContato(agenda, nome
        Se (linha == -1) então
          // informa se não encontrou o contato
          Escreva "Contato não cadastrado!
"
        Senão
          // se encontrou, exibe o contato e o edita
          exibirContato(agenda, linha
          editarContato(agenda, linha
        Fim_se


      // Efetua a pesquisa do contato
      caso 3:
        // pede o nome
        Escreva "------------ PESQUISE O CONTATO: "
        Escreva "Digite o nome.........:"
        nome = entrada.next(
        // Retorna a linha da pesquisa
          linha = pesquisarContato(agenda, nome
        Se (linha == -1)
          // Se o contato não existe
          Escreva "Contato não cadastrado!
"
        Senão
          // Se o contato existe, exibí-lo
          exibirContato(agenda, linha
        Fim_se


      // Lista todos os Contatos da agenda
      caso 4:
        listarAgenda(agenda


      // Exclui um registro digitado pelo usuário
      caso 5:

        Escreva "------- EXCLUINDO (PESQUISE O CONTATO): "
        Escreva "Digite o nome.........:"
        nome = entrada.next(
        apagarContato(agenda, nome


      caso 6:
        Escreva "OBRIGADO POR UTILIZAR A NOSSA AGENDA :)"

    Fim_Escolha
  Enquanto opcao != 6
Fim
~~~