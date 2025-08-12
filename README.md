# Linguagens Interpretadas VS Linguagens Compiladas

A primeira tarefa para compreender as diferenças entre as linguagens que precisam de um compilador, as que precisam de um interpretador e as que precisam/podem utilizar de ambos é saber que a máquina 
entende apenas linguagem de máquina, as famosas sequências binárias que nos atormentaram no semestre passado em Organização. Entretanto, quando escrevemos códigos, fazemos isso utilizando linguagens de alto nível, que não são
entendidas pelo computador, sendo necessária uma tradução. 

<br><img width="1862" height="1047" alt="1" src="https://github.com/user-attachments/assets/9ba5e22b-539a-4d33-9c27-32ce540e6e75" /><br>


Pronto, agora temos a base de tudo o que será discutido nesta apresentação, de maneira geral, tanto compiladores quanto interpretadores buscam realizar a mesma tarefa, fazer essa conversão do código escrito em linguagens de
alto nível para a linguagem de máquina. A diferença entre um e outro, falaremos sobre as variações posteriormente, é justamente quando essa tradução ocorre e como ela é feita.

Para facilitar, vamos pensar em uma analogia: imagine que temos um novo colega que entende apenas a língua alemã. A professora Andrea passa uma tarefa e você fica responsável de realizar a tradução do português para o alemão
. Para isso, algumas abordagens são possíveis. 

## Linguagens compiladas
- Você recebe o trabalho em português, realiza a tradução de todo o conteúdo para o alemão e, posteriormente, o entrega para o seu novo colega, que executa o trabalho. A imagem exemplifica o funcionamento das linguagens compiladas utilizando a analogia apresentada anteriormente.
<img width="927" height="416" alt="compiladas" src="https://github.com/user-attachments/assets/368369d0-9727-48e3-8bb7-b91220ba692c" />

### Pontos Positivos:

1) Velocidade de execução (performance): O código já está totalmente traduzido para uma linguagem que a máquina entende, assim, não é necessário esperar uma tradução e apenas posteriormente fazer a execução.
2) Portabilidade: O código pode ser compilado para vários sistemas operacionais.
3) Privacidade: Não há necessidade de divulgar o código fonte.
4) Erros de compilação: O compilador já checa e avisa alguns erros.

### Pontos Negativos:
1) Tempo de compilação: Em projetos mais robustos o tempo de compilação pode ser significativo.
2) Recompilação: É necessário recompilar novamente o código a cada modificação efetuada.
3) Executável engessado: O executável só funciona no sistema operacional para o qual ele foi compilado.

#### Alguns exemplos de linguagens compiladas são: C, C++, Fortran, Go, Rust,
Compiladores C / C++
1) GCC -> Linux // Windows com MinGW;
2) MSCVC (C++) para Windows;
3) Clang -> Windows, Linux, MacOS / C e C++

## Linguagens Interpretadas
- A tradução e a execução são feitas linha a linha, ou seja, o código está rodando ao mesmo tempo em que a tradução está acontecendo.
  <img width="947" height="473" alt="interpretadas" src="https://github.com/user-attachments/assets/269c9675-841d-41b9-b0c3-242e980658ea" />

### Pontos Positivos:

1) Portabilidade: Aqui pode haver uma confusão com a portabilidade das linguagens compiladas. Nesse caso, o usuário pode rodar o código em qualquer sistema operacional, tendo apenas o interpretador da linguagem.
Exemplo: Eu testo o código no Windows 64bit, Python versão 3.2, e passo para o meu colega que testa o mesmo código na máquina dele, MacOS 64bit com Python versão 3.2.
2) Debug: O debug é feito com o código em execução, em tese, torna-se mais fácil de realizar essa tarefa.
3) Não há necessidade de compilar o programa inteiro.

### Pontos Negativos:
1) Portabilidade apenas se você tiver o interpretador instalado no sistema operacional que você deseja rodar o código.
2) Execução é mais lenta, pela necessidade de tradução.

#### Alguns exemplos de linguagens são: Python, R, MATLAB e LUA
Interpretadores Python:
1) CPython -> Implementação mais utilizada, é a que vem quando baixamos o python no site oficial.
2) PyPy -> Interpretador que utiliza a metodologia JIT.
3) Jython -> Permite que o Python rode na JVM e acesse classes do Java.
4) IronPython -> Permite utilizar python no ecossistema Microsoft, permitindo acessar diversas bibliotecas do .NET.

## Linguagens Mistas

Tradução Dinâmica ou Compilação Just-In-Time (JIT)

Esse método busca utilizar a vantagem de ambas maneiras citadas anteriormente. A tradução é feita:
1) Conversão do código para uma linguagem mais próxima da linguagem de máquina. Bytecode em Java e IL (Linguagem Intermediária) em .NET
2) O código em bytecode ou IL é interpretado na execução inicial do programa.
3) Os métodos mais chamados ou partes do código que são executadas com mais frequência são compiladas, esse código compilado fica em cache na memória.
4) Na próxima vez que essa parte do código for chamada, utiliza-se o código compilado.
#### Exemplos de linguagens: Java, C# e Python (Nuitka)

## Como funciona o código em Java ?
Exemplo de código:
```
public class MinhaClasse {
  public static void main(String[] args) {
    System.out.println("Hello World");
  }
}
```
Inicialmente, esse código é compilado para Bytecode
```
javac meuprimeiroprograma.java
```
O resultado será um arquivo em bytecode: 
```
meuprimeiroprograma.class
```

Esse arquivo será executado pela JVM. 

Observação: Uma série de processos mais específicos são feitos até a execução, como a criação de objetos e verificação de métodos e classes.

## Referências
https://www.geeksforgeeks.org/java/how-jvm-works-jvm-architecture/
https://www.reddit.com/r/computerscience/comments/x4xxcj/why_java_has_a_jvm/
https://medium.com/@ahmetbeskazalioglu/compiled-and-interpreted-programming-languages-advantages-disadvantages-and-language-selection-b260ff8d2a50
https://www.ibm.com/docs/en/zos-basic-skills?topic=zos-compiled-versus-interpreted-languages
https://www.freecodecamp.org/news/compiled-versus-interpreted-languages/
https://www.geeksforgeeks.org/compiler-design/advantages-and-disadvantages-of-compiler/
https://www.dio.me/articles/linguagens-de-baixo-e-alto-nivel-o-que-sao-e-qual-a-diferenca
https://www.freecodecamp.org/portuguese/news/compilacao-just-in-time-explicada/
https://www.youtube.com/watch?v=1rd9TP692AM
https://www.youtube.com/watch?v=mQ-vQ2BlKrw
https://www.reddit.com/r/learnprogramming/comments/fada5a/what_is_the_difference_between_compiling_and/
https://www.geeksforgeeks.org/compiler-design/difference-between-compiler-and-interpreter/
Livro: Head First Java 3ed. Sierra; Bates e Gee, 2022.
https://hackr.io/blog/python-interpreters
https://terminalroot.com/list-of-top-10-c-cpp-compilers/

# Parte Prática:

O Haskell pode ser tanto compilado quanto interpretado. Aqui utilizamos o Stack, um gerenciador de projetos e dependências para Haskell (https://docs.haskellstack.org/en/stable/). Ele permite tanto 
a execução compilada quanto a interpretada. No vídeo, utilizamos o comando do Stack

```
stack runghc src/nomedoarquivo.hs
```
Que utiliza o ghc para compilar o código em linguagem intermediária na memória, não salvando um arquivo binário. Essa maneira é bastante interessante para testes rápidos no código.

https://github.com/user-attachments/assets/f0209182-d12e-4148-ac45-1df3e114513f

Referências:
https://www.arquivodecodigos.com.br/dicas/4825--haskell-para-iniciantes-como-ler-a-entrada-do-usuario-em-haskell-ler-o-nome-da-pessoa-e-exibir-uma-mensagem-de-boas-vindas.html
https://www.facom.ufu.br/~madriana/PF/IOHaskell.pdf
