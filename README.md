> # Potigol is ...
> Uma linguagem moderna (funcional) para aprender a programar.
> A modern language (functional) to learn code computer.


Try it online: [![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io#snapshot/635c2c25-4a9a-4f97-a258-594be811ef1b)




   ![Editor Potigol](pootigol.jpg)

---

## [Download](https://github.com/potigol/Potigol/releases)* and how *[Instalar](https://github.com/potigol/Potigol#como-usar)*

 - Follow us on twitter: *[@potigol](https://twitter.com/potigol)*

 - [Examples of code](https://potigol.github.io/URI-Potigol/) in Language Potigol :new:

 - *[Try it!](https://potigol.github.io/tente)* :new:


Meet too the library to make games in 2D [Jerimum](https://potigol.github.io/Jerimum/) :video_game:


## Feature
 * Created for to be used by beginning students 
 * Static typing with type inference
 * keywords in portuguese
 * Mult paradigm
 * Encouraging the functional paradigm: unchanging values, junction of functions, function like values

## How to use
  - Download the latest version fo Potigol https://github.com/potigol/Potigol/releases/latest
  - Unzip the file
  - To run Code Editor, type at the terminal prompt
  
  ````java -jar epotigol.jar````

  - Windows, just run `epotigol.bat`.

  - To run a program in Potigol, type at the terminal prompt 

  ````java -jar potigol.jar arquivo.poti````

  - Windows, just run `potigol arquivo.poti`.

Examples: https://github.com/potigol/Potigol/wiki/jogos

## The Language

### Variables
````scala
x = 10                 # Declaration of a fixed value (don't be changed)
y, z = 20              # Many variables receive a same value y = 20 and z = 20
a, b, c = 1, 2, 3      # Parallel declaration: a = 1, b = 2 e c = 3
var y := 10            # Declaration of a changeable variable
y := y + 2             # Assigning of a value for a variable
var a, b, c := 1, 2, 3 # Parallel declaration: var a := 1, var b := 2 e var c := 3
a, b, c := b, a, 4     # Assigning paralela: a := 2, b := 1 e c := 4
````

### Tipes Basics

| Type | Values |
| --- | --- |
| Integer | `-4`, `0`, `5`, ... |
| Float | `-7.23`, `0.0`, `5.25`, ... |
| String | `"text"`, `"hello"`, `"world"`, ... |
| Logic | `true` and `false` |
| Character | `'a'`, `'4'`, `'&'`, ... |


### Arithmetic Operations
````scala
5 + 3         # Sum: 8
5 - 3         # Subtration: 2
5 * 3         # Multiply: 15
5 / 3         # Float division: 1.66667
5 div 3       # Integer division: 1
5 mod 3       # Rest of division: 2
````

### Logic Operations and Relational
````scala
# Logic Values: true, false
true and false                        # and logic             : false
verdadeiro ou falso                   # or logic              : true
not true                              # not logic             : false

2 == 3                                # test of equal         : false
2 <> 3                                # teste de unequal      : true
2 < 3                                 # less                  : true
2 <= 3                                # less than or equal to : true
2 > 3                                 # greater               : true
2 >= 3                                # greater than or equal to : false
````


### Input
````scala
a = leia_inteiro                # read a integer number typed of keyboard
b = leia_real                   # read a float number typed of keyboard
c = leia_texto                  # read a text/string typed of keyboard
x, y = leia_inteiro             # read two integer numbers, this is same that x = leia_inteiro, y = leia_inteiro
numbers = leia_inteiros(5)      # read a list of five integer numbers, one by line
numbers = leia_inteiros(",")    # read a list of integer numbers, comma separated
````

### Output
````ruby
escreva "Hello World"   # write and pass to next line
imprima "Hello "        # write and continue in the same line
escreva "World"

name = "World"
escreva "Hello {name}!"  # "Hello World!"
````

### If
````scala
x = leia_inteiro

# se ... então ... fim
se x > 5 então
  escreva "greater than five."
fim

# se ... então ... senão ... fim
se x > 5 então
  escreva "greater than five."
senão
  escreva "less than or equal to five."
fim

se verdadeiro então                # write "true"
  escreva "true"
senão
  escreva "false"
fim

se falso então                     # write "false"
  escreva "true"
senão
  escreva "false"
fim

# se ... então ... senãose ... senão ... fim
se x > 8 então
  escreva "greater than eight."
senãose x > 6 então
  escreva "greater than six."
senãose x > 4 então
  escreva "greater than four."
senãose x > 2 então
  escreva "greater than two."
senão
  escreva "less than or equal to two."
fim

# using se how a expression
a = se x mod 2 == 0 então "even" senão "odd" fim

greater = se a >= b e a >= c então a senãose b > c então b senão c fim
````

### Escolha (Choice, Case)
````scala
x = leia_inteiro
escolha x
  caso 1 => escreva "One"                # se x == 1
  caso 2 => escreva "Two"                # se x <> 1 e x == 2
  caso 3 => escreva "Three"              # se x <> 1 e x <> 2 e x == 3
  caso _ => escreva "Another value"      # se x <> 1 e x <> 2 e x <> 3
fim

# Escolha (Choice) with conditions
escolha x
  caso n se n < 0        => escreva "{n} is negative"
  caso n se n mod 2 == 0 => escreva "{n} is even"
  caso n                 => escreva "{n} is odd"
fim

# using Escolha (Choice) how a expression
é_zero = escolha x
  caso 0 => verdadeiro
  caso _ => falso
fim

sinal = escolha x               # escolha (choice) retorn a number: -1, 0 or 1
  caso n se n < 0 => -1
  caso n se n > 0 =>  1
  caso _          =>  0
fim
````

### Repetion: Para (For)
````scala
para i de 1 até 10 faça            # write the numbers 1 to 10
  escreva i
fim

var sum := 0
para i de 1 até 10 faça            # sum the numbers 1 to 10
  sum := sum + i
fim
escreva "The sum is {sum}."

para i de 1 até 10 passo 2 faça    # write the odd numbers 1 to 10
  escreva i
fim

# Para (For) decreasing numbers
para i de 10 até 1 passo -1 faça   # write numbers 10 to 1
  escreva i
fim

# Para with more one generator
para i de 1 até 4,
     j de 1 até 3 faça             # write multiplication
     escreve a tabuada {1..4} x {1..3}
  escreva "{i} * {j} == {i * j}"
fim

# Para (For) with lists
colors = ["blue", "red", "green"]
para color em colors faça
  escreva color
fim

# Para gerando uma lista
numeros = para i de 1 até 5 gere i fim             # [1, 2, 3, 4, 5]

pares = para i de 1 até 10 se i mod 2 == 0 gere i  # [2, 4, 5, 6, 8, 10]

````

### Repetição: Enquanto
````scala
var i := 0
enquanto i<=10 faça                 # Escreve os números de 1 a 10
  escreva i
  i := i + 1
fim
````

### Funções
````scala
soma(x: Inteiro, y: Inteiro) = x + y    # Declaração de função em uma linha

soma(x, y: Inteiro) = x + y             # Agrupando parâmetros do mesmo tipo

rep(a: Texto, n: Inteiro) = a * n       # Funções com parâmetros de tipos diferentes

a, b = leia_inteiro
c = soma(a, b)                          # Aplicando a função
escreva "{a} + {b} = {c}"

soma(x, y: Inteiro): Inteiro = x + y    # O tipo de retorno pode ser definido explicitamente

soma(x, y: Inteiro)                     # Declaração de função com corpo
  c = x + y
  retorne c                             # A última linha tem o valor de retorno
fim

soma(x, y: Inteiro)                     # Declaração de função com corpo
  c = x + y
  c                                     # A palavra 'retorne' é opcional
fim

fatorial(n: Inteiro): Inteiro           # Função recursiva (tipo de retorno é obrigatório)
  se n <= 1 então
    1
  senão
    n * fatorial(n - 1)
  fim
fim
a = leia_inteiro
escreva "Fatorial de {a} é {fatorial(a)}"

f(a: Inteiro)
  g(b: Inteiro) = b * 2                 # Função interna
  retorne g(a) + 3
fim
````

### Tipo de parâmetros

| Tipo | Exemplo | Aplicação|
| --- | --- | --- |
| `Inteiro` | `proximo(a: Inteiro) = a + 1 `| `proximo(3)` |
| `Real`    | `dobro(a: Real) = a * 2` | `dobro(3.6)` |
| `Texto`   | `inicio(s: Texto) = s.pegue(5)` | `inicio("Olá mundo!")` |
| `Lógico`  | `negacao(a: Lógico) = não a` | `negacao(verdadeiro)` |
| `Caractere` | `id(c: Caractere) = c` | `id('a')` |
| `Tupla` | `f(a : (Inteiro, Texto)) = ...` | `f((10,"ok"))` |
| `Lista` | `soma(a: Lista[inteiro]) = ...` | `soma([1,2,3,4,5])` |
| Função | `f(g: (Inteiro, Inteiro) => Inteiro) = g(2,3)` | `f((a,b) => a + b)` |
| Classe ou Registro | `f(a: T) = ...` | `f(T(...))` |

## Tipos

### Número (Inteiro e Real)
````scala
12345.qual_tipo                   # "Inteiro"
12345.real                        # 12345.0
12345.texto                       # "12345"
97.caractere                      # 'a'
12345 formato "%8d"               # "   12345"

12345.678.qual_tipo               # "Real"
12345.678.inteiro                 # 12345
12345.678.texto                   # "12345.678"
12345.678.arredonde               # 12346
12345.678.arredonde(2)            # 12345.68
123.45 formato "%.1f"             # "123.4"

12345.678.piso                    # 12345.0 (arredonda para baixo)
12345.678.teto                    # 12346.0 (arredonda para cima)
12345.678.inteiro                 # 12345
````

### Texto
````scala
"abc".qual_tipo                   # "Texto"
"123".inteiro                     # 123
"12abc3".inteiro                  # 12
"abc".inteiro                     # 0
"abc"[2]                          # 'b' (caractere na posição 2)

"12.3".real                       # 12.3
"12a.3".real                      # 12.0
"abc".real                        # 0.0

"ab" + "cd"                       # "abcd"  (concatenação)
"abcb" - "bd"                     # "acb"   (subtração)

"abc".tamanho                     # 3
"abc".posição('b')                # 2 (posição de 'b' em "abc")
"abc".posição('d')                # 0
"abc".contém('a')                 # verdadeiro (testa de 'a' está em "abc")
"abc".contém('d')                 # falso

"Abc".maiúsculo                   # "ABC"
"Abc".minúsculo                   # "abc"
"Abc".inverta                     # "cbA"
"cab".ordene                      # "abc"
"abc".junte("-")                  # "a-b-c"
"abc".junte("[", ", ", "]")       # "[a, b, c]"

"Um texto".divida                 # ["Um", "texto"]
"Um texto".divida("t")            # ["Um ", "ex", "o"]
"Um texto".lista                  # ['U', 'm', ' ', 't', 'e', 'x', 't', 'o']

"abc".cabeça                      # 'a'  (primeiro caractere de "abc")
"abc".cauda                       # "bc" ("abc" sem o primeiro caractere)
"abc".último                      # 'c'  (último caractere de "abc")
"abcde".pegue(3)                  # "abc" (primeiros 3 caracteres)
"abcde".descarte(3)               # "de"  (sem os primeiros 3 caracteres)

"abcb".selecione(letra => letra<>'c')          # "abb" ("abcb" sem 'c')
"abc".injete(0)((x,y) => x + y)                # 294   (97 + 98 + 99)
"abc".injete("")((x,y) => x + "-" + y)         # "-a-b-c"

"abcb".descarte_enquanto(letra => letra<>'c')  # "cb" (descarte caracteres antes de 'c')
"abcb".pegue_enquanto(letra => letra<'c')      # "ab" (pegue caracteres antes de 'c')

x = "abc".remova(2)               # x = "ac"  (remove o caractere na posição 2)
y = "abc".insira(3, 'd')          # y = "abdc" (insere 'd' na posição 2)
z = "abc".insira(3, "def")        # z = "abdefc" (insere "def" na posição 2)
````

### Lista
````scala
[2, 4, 6, 8, 10]                         # lista literal
2 :: [4, 6, 8, 10]                       # [2, 4, 6, 8, 10]
[2, 4, 6, 8, 10].tamanho                 # 5
[2, 4, 6, 8, 10].cabeça                  # 2
[2, 4, 6, 8, 10].cauda                   # [4, 6, 8, 10]
[2, 4, 6, 8, 10].último                  # 10
[2, 4, 6, 8, 10].pegue(2)                # [2, 4]
[2, 4, 6, 8, 10].descarte(2)                # [6, 8, 10]


[2, 4, 6, 8, 10].inverta                 # [10, 8, 6, 4, 2]
[2, 6, 8, 10, 4].ordene                  # [2, 4, 6, 8, 10]
[2, 4, 6] + [8, 10]                      # [2, 4, 6, 8, 10]
[2, 4, 6].junte                          # "246"
[2, 4, 6].junte(", ")                    # "2, 4, 6"
[2, 4, 6].junte("[", ", ", "]")          # "[2, 4, 6]"

a = [2, 4, 6, 8, 10]
a[3]                                     # 6
a.posição(6)                             # 3
a.posição(12)                            # 0
a.contém(6)                              # verdadeiro
a.contém(12)                             # falso
a.remova(4)                              # [2, 4, 6, 10]
a.insira(3,5)                            # [2, 4, 5, 6, 8, 10]

Lista.imutável(5, 0)                     # [0, 0, 0, 0, 0]
Lista.vazia[Inteiro]                     # []   - Lista vazia de inteiros

# Matrizes e Cubos
a = [[1, 2], [3, 4]]                     # Matriz 2x2
a[2]                                     # [3, 4]
a[2][1]                                  # 3
b = Matriz.imutável(2, 2, 0)             # b == [[0, 0], [0, 0]]
c = Cubo.imutável(2, 2, 2, "-")          # c == [[["-", "-"],["-", "-"]],[["-", "-"],["-", "-"]]]
c[1][2][1]                               # "-"

# Listas mutáveis
a = Lista.mutável(5, 0)                      # [0, 0, 0, 0, 0].mutável
a[3] := 5                                    # a == [0, 0, 5, 0, 0].mutável

# Funções de alta-ordem
[2, 4, 6, 8, 10].selecione(n => n mod 4 == 0)  # [4, 8]
[2, 4, 6, 8, 10].mapeie(n => n div 2)          # [1, 2, 3, 4, 5]
[2, 4, 6].injete(0)((a, b) => a + b)           # 0 + 2 + 4 + 6 == 12
[2, 4, 6].injete((a, b: Inteiro) => a + b)     # 2 + 4 + 6 == 12
[2, 4, 6, 2, 4].pegue_enquanto(n => n < 6)     # [2, 4]
[2, 4, 6, 2, 4].descarte_enquanto(n => n < 6)  # [6, 2, 4]
````

### Tupla
````ruby
t = (2015, "potigol", 1.0)                     # Tupla do tipo (Inteiro, Texto, Real)
t.primeiro                                     # 2015
t.segundo                                      # "potigol"
t.terceiro                                     # 1.0
````

## Funções Matemáticas
````ruby
PI
sen(3.14)
cos(3.14)
tg(1)
arcsen(1)
arccos(1)
arctg(1)

abs(-2.4)                              # 2.4
raiz(9)                                # 3.0
log(2)
log10(2)

aleatório()                            # número aleatório entre 0 e 1
aleatório(10)                          # número aleatório entre 1 e 10
aleatório(1, 6)                        # número aleatório entre 1 e 6
aleatório([2, 4, 6, 8, 10])            # número aleatório pertencente à lista [2, 4, 6, 8, 10]
````

## Programação Orientada a Objetos

Classes são definidas através de tipos. Os tipos são compostos por atributos e métodos (funções). Todos elementos de um tipo são públicos, mas não é possível alterar diretamente um atributo.

### Declaração de um Tipo (Classe)
````scala
tipo «Tipo»
  «[var]» «lista de atributos do construtor» : «tipo»
  «[var]» «atributos» = «valor»
  «métodos»
fim

«obj» = «Tipo»(«lista de valores do construtor»)
«obj».«atributo»
«obj».«método»
````

#### Exemplo

````ruby
tipo Quadrado
  lado: Real
  area() = lado * lado
  perimetro() = 4 * lado
fim

q1 = Quadrado(10)
escreva q1.area
escreva q1.perimetro
````

## Programação Funcional

### Valores (constantes)
````ruby
nome = "potigol"
````

### Listas
````ruby
lista1 = [1,2,3,4]
lista2 = 0::lista1
````

### Operações com listas (filter, fold, map)
````ruby
numeros = [1, 2, 3, 4, 5, 6, 7, 8]
pares = numeros.selecione(n => n mod 2 == 0)    # filtro
soma = numeros.injete(0)((a,b) => a + b)        # fold
dobro = numeros.mapeie(n => n * 2)              # map
````

### Expressões lambda
````ruby
x = (a: Inteiro) => a * 2
escreva x(4)
````

### "list comprehension"
````ruby
y = para i de 1 até 10,
         j de i + 1 até 10 gere
           i+j
    fim
escreva y
````

### Funções de Alta ordem
````scala
f(g: Inteiro => Inteiro, a: Inteiro) = g(a)
sucessor(n: Inteiro) = n + 1
escreva f(sucessor, 5)
````

### Currying
````scala
soma(a: Inteiro) = ((b: Inteiro) => a + b)
escreva soma(2)(3)
suc = soma(1)
escreva suc(4)
````

### Recursão em cauda otimizada
````scala
h(a, cont: Inteiro): Inteiro = escolha a
  caso 0 => cont
  caso n => h(a-1, cont+1)
fim
escreva h(1000,0)
````

### Casamento de Padrões
````scala
# QuickSort
quicksort(num: Lista[Inteiro]): Lista[Inteiro] =
  escolha num
    caso []  => []
    caso pivo::resto =>
      menores = resto.selecione( _ <= pivo )
      maiores = resto.selecione( _ >  pivo )
      quicksort(menores) + pivo::quicksort(maiores)
  fim

escreva "Digite alguns números separados por espaços"
numeros = leia_inteiros(" ")
escreva "Os números ordenados:"
escreva quicksort(numeros)
````
