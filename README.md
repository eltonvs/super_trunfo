# Super Trunfo

[![Build Status](https://travis-ci.org/eltonvs/super_trunfo.svg?branch=master)](https://travis-ci.org/eltonvs/super_trunfo)

## Descrição
**Super Trunfo** é um jogo de cartas que pode ser jogado por 2 ou mais pessoas.

Nele, o bolo de cartas é dividido igualmente entre os jogadores.

A cada rodada, é escolhido um dos 4 atributos da carta (pelo jogador que ganhou
a rodada anterior) e comparado entre a primeira carta do bolo de cada jogador.
O jogador que possuir a carta com a aributo de maior valor é o vencedor da rodada
e fica com todas as cartas usadas na rodada (colocando-as no fim de seu deck).

O vencedor é o jogador que ficar com as cartas de todos os outros jogadores.

### Inteligêcia Artificial
Quando ativada, a dinâmica do jogo é alterada, pois ao invés de pegar sempre a
primeira carta do deck de cada jogador, o programa procura em suas cartas a que
possui o maior valor para o atributo escolhido na rodada. Dessa forma, a cada
rodada, os jogadores farão a sua melhor opção de jogada.

Caso o jogador possua uma carta "Super Trunfo" ela será a escolhida.

### Casos especiais:
 - Caso o identificador da carta seja **ST** (*Super Trunfo*), essa carta será
   automaticamente a vencedora da rodada, independente do valor de seus atributos
   a não ser que uma das outras cartas possua o número 1 em seu identificador (A1, B1, ...).


## Como compilar
Para compilar, você só precisa executar o seguinte comando:

```
$ make
```

E para executar:

```
$ ./bin/supertrunfo input_file N_PLAYERS N_CARDS IA_FLAG
```

 * Sendo `input_file` o arquivo de entrada com as informações sobre as cartas,
   `N_PLAYERS` o número de jogadores, `N_CARDS` o número de cartas a ser
   distribuído entre eles e `IA_FLAG` um modificador (`-ai`) que, caso inserido, ativa
   a "inteligência artificial" do jogo.

### Debug
Caso você queira compilar uma versão para debug (com o `-g` e `-O0`), execute:

```
$ make debug
```

E para executá-lo:

```
$ ./bin/debug input_file N_PLAYERS N_CARDS
```


## Tópicos Utilizados
 - Classes;
 - Vectors;
 - Strings;
 - Argumentos por linha de comando;
 - Busca Sequencial;
 - Funções do STL:
   - `std::setw()`          // Para o ajuste da largura das tabelas (exibição)
   - `std::setprecision()`  // Para mostrar os números com apenas 2 casas decimais
   - `std::stoi()`          // Para a conversão de string para inteiro
   - `std::stod()`          // Para a conversão de string para double
   - `std::shuffle()`       // Para embaralhar as cartas antes de distribuí-las


## Bugs/Limitações
 - O programa não faz o tratamento de situações envolvendo empates.
 - O programa só lê o arquivo com os dados das cartas se elas estiverem no
   formato correto (para o caso de aviões, seguindo o exemplo abaixo):
    ```
    ID
    NOME
    EMPRESA DE FABRICAÇÃO - PAÍS DE ORIGEM
    ANO
    VELOCIDADE MÁXIMA
    AUTONOMIA
    COMPRIMENTO
    ENVERGADURA
    (LINHA EM BRANCO QUE SEPARA AS INFORMAÇÕES DE CADA CARTA)
    ```


## Autores
 - Elton de Souza Vieira
 - Pedro Arthur Medeiros Fernandes
