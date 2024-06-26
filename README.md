# Introdução 

## Categoria de Linguagem

Ruby é uma linguagem de programação versátil que oferece suporte a uma ampla gama de paradigmas, incluindo programação funcional, orientada a objetos e imperativa. Isso significa que os desenvolvedores podem utilizar diferentes estilos de programação, dependendo das necessidades específicas de seus projetos.

### Paradigma Funcional:
```ruby
lista = [1, 2, 3, 4, 5]
soma = lista.reduce(0) { |acumulador, numero| acumulador + numero }

puts soma  # Saída: 15
```

### Orientação a Objetos:
```ruby
class Cachorro
  attr_reader :nome

  def initialize(nome)
    @nome = nome
  end

  def latir
    "Au Au!"
  end
end

cachorro = Cachorro.new("Bob")
puts cachorro.latir  # Saída: Au Au!
```

### Programação Imperativa:
```ruby
lista = [11, 4, 9, 18, 2]

maior = lista[0]
lista.each do |numero|
  maior = numero if numero > maior
end

puts maior  # Saída: 18
```

## Métodos de Implementação

Ruby implementada por meio da interpretação pura, ou seja, é executado diretamente por um interpretador, sem a necessidade de compilação prévia para código de máquina.

# Variáveis: Nomes e Amarração 

## Atributos das Variáveis

## Nome

O nome das variáveis em ruby segue as seguintes convenções e regras:

### Case sensitivity: Ruby é case-sensitive, o que significa que variáveis com nomes em maiúsculas e minúsculas são tratadas como diferentes.
```ruby
variavel = 1
variaveL = 2

puts variavel # Saída: 1
puts variaveL # Saída: 2
```

### Snake case: A convenção mais comum para nomes de variáveis em Ruby é usar snake case, onde palavras são separadas por underline.
```ruby
minha_variavel = "Exemplo"
```

### Nomes de variáveis locais: Variáveis locais começam com uma letra minúscula ou um underline.
```ruby
exemplo1 = "Exemplo 1"
_exemplo2 = "Exemplo 2"
```

### Nomes de variáveis de instância: Variáveis de instância começam com um @. 
```ruby
class Pessoa
  def initialize(nome)
    @nome = nome
  end

  def saudacao
    puts "Olá, #{@nome}!"
  end
end
```

### Nomes de variáveis de classe: Variáveis de classe começam com dois @. Por exemplo: @@contador, @@total.
```ruby
class Pessoa
  @@total_pessoas = 0

  def initialize(nome)
    @nome = nome
    @@total_pessoas += 1
  end

  def self.total_pessoas
    @@total_pessoas
  end

  def saudacao
    puts "Olá, #{@nome}!"
  end
end
```

### Nomes de constantes: Constantes em Ruby são escritas em letras maiúsculas, com palavras separadas por underscores.
```ruby
MINHA_CONSTANTE = 3.141592
```

## Palavras Especiais
```ruby
# Retirado da documentação oficial da linguagem

_ENCODING__ # The script encoding of the current file. See Encoding.
__LINE__    # The line number of this keyword in the current file.
__FILE__    # The path to the current file.
BEGIN       # Runs before any other code in the current file. See miscellaneous syntax
END         # Runs after any other code in the current file. See miscellaneous syntax
alias       # Creates an alias between two methods (and other things). See modules and classes syntax
and         # Short-circuit Boolean and with lower precedence than &&
begin       # Starts an exception handling block. See exceptions syntax
break       # Leaves a block early. See control expressions syntax
case        # Starts a case expression. See control expressions syntax
class       # Creates or opens a class. See modules and classes syntax
def         # Defines a method. See methods syntax
defined?    # Returns a string describing its argument. See miscellaneous syntax
do          # Starts a block.
else        # The unhandled condition in case, if and unless expressions. See control expressions
elsif       # An alternate condition for an if expression. See control expressions
end         # The end of a syntax block. Used by classes, modules, methods, exception handling and control expressions.
ensure      # Starts a section of code that is always run when an exception is raised. See exception handling
false       # Boolean false. See literals
for         # A loop that is similar to using the each method. See control expressions
if          # Used for if and modifier if expressions. See control expressions
in          # Used to separate the iterable object and iterator variable in a for loop. See control expressions
module      # Creates or opens a module. See modules and classes syntax
next        # Skips the rest of the block. See control expressions
nil         # A false value usually indicating “no value” or “unknown”. See literals
not         # Inverts the following boolean expression. Has a lower precedence than !
or          # Boolean or with lower precedence than ||
redo        # Restarts execution in the current block. See control expressions
rescue      # Starts an exception section of code in a begin block. See exception handling
retry       # Retries an exception block. See exception handling
return      # Exits a method. See methods
self        # The object the current method is attached to. See methods
super       # Calls the current method in a superclass. See methods
then        # Indicates the end of conditional blocks in control structures. See control expressions
true        # Boolean true. See literals
undef       # Prevents a class or module from responding to a method call. See modules and classes
unless      # Used for unless and modifier unless expressions. See control expressions
until       # Creates a loop that executes until the condition is true. See control expressions
when        # A condition in a case expression. See control expressions
while       # Creates a loop that executes while the condition is true. See control expressions
yield       # Starts execution of the block sent to the current method. See methods
```

## Tipos de Variável

Ruby suporta variáveis dos tipos Number, Boolean, String, Hash, Array e Symbol
### Number
```ruby
numero = 2
numero = 2.5
```

### Boolean
```ruby
booleano = false
booleano = true
```

### String
```ruby
exemplo_string = "Exemplo string"
```

### Hash
```ruby
exemplo_hash = { :nome => "Pedro", :idade => 28 }
```

### Array
```ruby
arr = [1, 2, 3, 4, 5]
```

### Symbol
```ruby
:exemplo_symbol
```

## Amarração do Tipo das Variáveis

Ruby possui amarração dinâmica de tipo, isto é, o tipo da variável é atribuído ao valor, não ao nome dela.
```ruby
exemplo = 2   # Number
exemplo = "2" # String 
```

## Escopo

Ruby possui escopo estático, ou seja, as variáveis são resolvidas em tempo de execução, com base no contexto em que são chamadas.
```ruby
def metodo_externo
  variavel_externa = "Exemplo de variável externa"

  metodo_interno = Proc.new do
    puts variavel_externa
  end

  metodo_interno.call
end

metodo_externo # Saída: "Exemplo de variável externa"
```

# Expressões e Sentenças de Atribuição

## Expressões Aritméticas

### Soma
```ruby
soma = 3 + 5
puts soma  # Saída: 8
```

### Subtração
```ruby
subtracao = 5 - 3
puts subtracao  # Saída: 2
```

### Multiplicação
```ruby
multiplicacao = 4 * 2
puts multiplicacao  # Saída: 8
```

### Divisão
```ruby
divisao = 10 / 2
puts divisao  # Saída: 5
```

### Resto
```ruby
resto = 5 % 2
puts resto  # Saída: 1
```

### Potência
```ruby
potencia = 5 ** 3
puts potencia  # Saída: 125
```

## Precedência de Operadores
```ruby
a = 10
b = 5
c = 2

resultado = a + b * c    
puts resultado           # Saída: 20

resultado = (a + b) * c
puts resultado           # Saída: 30

resultado = a * b + c
puts resultado           # Saída: 52

resultado = a * (b + c)
puts resultado           # Saída: 70
```

## Associatividade

### Esquerda para a Direita
```ruby
resultado1 = 15 / 3 / 5
resultado2 = 20 - 5 - 3 - 2

puts resultado1  # Saída: 1
puts resultado2  # Saída: 10
```

### Direita para a Esquerda
```ruby
resultado3 = 2 ** 3 ** 2
resultado4 = 10 ** 2 ** 3

puts resultado3  # Saída: 512
puts resultado4  # Saída: 10000000000
```

## Expressões Condicionais

### if-else
```ruby
idade = 20

if idade >= 18
  puts "Você é maior de idade"
else
  puts "Você é menor de idade"
end
```

### ternário
```ruby
idade = 14

puts idade >= 18 ? "Você é maior de idade" : "Você é menor de idade"
```

### if-elsif-else
```ruby
nota = 70

if nota >= 90
  puts "Aprovado com A"
elsif nota >= 80
  puts "Aprovado com B"
elsif nota >= 70
  puts "Aprovado com C"
else
  puts "Reprovado"
end
```

## Ordem de Avaliação dos Operandos

```ruby
def retorna_10
  return 10
end

resultado = retorna_10 + 5 * 2
puts resultado # Saída: 20
```

## Sobrecarga de Operadores
```ruby
class Vetor2D
  attr_accessor :x, :y

  def initialize(x, y)
    @x = x
    @y = y
  end

  def +(outro)
    Vetor2D.new(@x + outro.x, @y + outro.y)
  end


  def to_s            # Método utilizado para printar o valor 
    "(#{@x}, #{@y})"
  end
end

vetor1 = Vetor2D.new(1, 2)
vetor2 = Vetor2D.new(3, 4)

resultado = vetor1 + vetor2

puts resultado       # Saída: (4, 6)
```

## Conversões de Tipo

### Implícita
```ruby
x = 10
y = 3.5

soma = x + y  # 10 é implicitamente convertido para float
puts soma     # Saída: 13.5
```

### Explícita
```ruby
num_inteiro = 10
num_string = "20"

soma = num_inteiro + num_string.to_i  # Conversão explícita de num_string para inteiro
puts soma                             # Saída: 30
```

## Expressões Relacionais

### Igual a
```ruby
5 == 10  # false
```

### Diferente de
```ruby
5 != 10  # true
```

### Maior que
```ruby
5 > 10  # false
```

### Menor que
```ruby
5 < 10  # true
```

### Maior ou igual a
```ruby
5 >= 10  # false
```

### Menor ou igual a
```ruby
5 <= 10  # true
```

## Atribuição

### Simples 
```ruby
x = 10
puts x  # Saída: 10
```

### Com Operadores Aritméticos
```ruby
y = 5
y += 2 # Equivalente a y = y + 2
puts y # Saída: 7
```

### Atribuição múltipla
```ruby
a, b, c = 1, 2, 3
puts a # Saída: 1
puts b # Saída: 2
puts c # Saída: 3
```

### Atribuição condicional
```ruby
z = 20
z ||= 30  # Atribui 30 a z apenas se z for nil ou false
puts z # Saída: 20
```

# Estruturas de Controle

## Sentenças de seleção

### Expressão de Controle
```ruby
if a == 2
  print a
else
  print "não é igual"
end
```

### Seletores Aninhados
```ruby
if a == 2
  if a < b
    puts b
  end
else
  puts a
end
```

### Seleção Múltipla
```ruby
z = 3
case z
when 1
  puts "z é 1"
when 2
  puts "z é 2"
else
  puts "z é diferente de 1 e 2"
end
```

## Sentença Iterativa

### Loops Controlados por Contadores
```ruby
for i in 1..5
  puts i
end
```
### Loops Controlados Logicamente
```ruby
contador_while = 1
contador_until = 1

while contador_while <= 5 do
  puts contador_while
  contador_while += 1
end

until contador_until > 5 do
  puts contador_until
  contador_until += 1
end
```

### Controle definido pelo usuário
```ruby
i = 0
loop do
  puts i
  i += 1
  break if i >= 5 # para o loop se a condição for verdadeira
end

for i in 0..5
  next if i % 2 == 0  # Pula para a próxima iteração se i for par
  puts i
end
```

### Iteração Baseada em Estrutura de Dados
```ruby
numeros = [1, 2, 3, 4, 5]

numeros.each do |numero|
  puts numero
end
```


# Subprogramas

Subprogramas em Ruby são métodos definidos com a palavra-chave `def`. Eles podem receber parâmetros formais e informais e permitem diferentes tipos de passagem de parâmetro.

## Definição de Métodos

Em Ruby, um método é definido usando a palavra-chave `def`, seguida pelo nome do método e, opcionalmente, uma lista de parâmetros:

```ruby
def saudacao
  puts "Olá, mundo!"
end
```

## Parâmetros Formais

Parâmetros formais são definidos na declaração do método. Eles podem ser obrigatórios ou opcionais:

```ruby
def saudacao(nome)
  puts "Olá, #{nome}!"
end

# Chamada do método
saudacao("João") # Saída: Olá, João!
```

## Parâmetros Opcionais

Parâmetros opcionais podem ter valores padrão, que serão usados se nenhum argumento for passado:

```ruby
def saudacao(nome = "Mundo")
  puts "Olá, #{nome}!"
end

saudacao()          # Saída: Olá, Mundo!
saudacao("João")    # Saída: Olá, João!
```

## Parâmetros Variáveis

Métodos em Ruby podem aceitar um número variável de argumentos usando o operador splat (`*`):

```ruby
def soma(*numeros)
  numeros.reduce(0) { |soma, num| soma + num }
end

puts soma(1, 2, 3, 4)  # Saída: 10
puts soma(5, 10)       # Saída: 15
```

## Tipos de Passagem de Parâmetro

Ruby utiliza passagem de parâmetros por valor para objetos imutáveis (como números e símbolos) e passagem por referência para objetos mutáveis (como arrays e hashes).

```ruby
def modificar_parametros(a, b)
  a += 10
  b << "mundo"
end

x = 5
y = "Olá, "

modificar_parametros(x, y)

puts x  # Saída: 5 (imutável, não alterado)
puts y  # Saída: "Olá, mundo" (mutável, alterado)
```

# Tratamento de Exceção

Ruby possui um robusto sistema de tratamento de exceções, permitindo que erros sejam gerenciados de forma eficaz.

### Bloco `begin-rescue`

Você pode capturar exceções usando blocos `begin-rescue`:

```ruby
begin
  # Código que pode lançar uma exceção
  resultado = 10 / 0
rescue ZeroDivisionError => e
  # Código para lidar com a exceção
  puts "Erro: #{e.message}"
end
```

### Bloco `ensure`

O bloco `ensure` é utilizado para executar código que deve ser executado independentemente de uma exceção ter ocorrido ou não:

```ruby
begin
  # Código que pode lançar uma exceção
  resultado = 10 / 0
rescue ZeroDivisionError => e
  # Código para lidar com a exceção
  puts "Erro: #{e.message}"
ensure
  # Código que sempre será executado
  puts "Operação finalizada."
end
```

### Bloco `retry`

O bloco `retry` permite tentar executar o bloco `begin` novamente, útil em situações onde uma falha pode ser temporária:

```ruby
begin
  # Código que pode lançar uma exceção
  resultado = 10 / 0
rescue ZeroDivisionError => e
  # Código para lidar com a exceção
  puts "Erro: #{e.message}. Tentando novamente..."
  retry
end
```

### Exceções Personalizadas

Você pode definir suas próprias exceções em Ruby criando subclasses da classe `StandardError`:

```ruby
class MinhaExcecao < StandardError; end

def metodo_que_lanca_excecao
  raise MinhaExcecao, "Algo deu errado!"
end

begin
  metodo_que_lanca_excecao
rescue MinhaExcecao => e
  puts "Capturada minha exceção: #{e.message}"
end
```