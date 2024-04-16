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

### Nomes de constantes: Constantes em Ruby são escritas em letras maiúsculas, com palavras separadas por underscores. Por exemplo: CONSTANTE_EXEMPLO.
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
```ruby
numero = 2            # Number
bool = true           # Boolean
str = "Exemplo"       # String
hash = {              # Hash
  chave1: "Exemplo",
  chave2: 2
}
arr = [1, 2, 3, 4]    # Array
:exemplo              # Symbol
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

  inner_method = Proc.new do
    puts variavel_externa
  end

  metodo_interno.call
end

metodo_externo # Saída: "Exemplo de variável externa"
```
