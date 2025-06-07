
# Guia de Referência Rápida: Ruby para Estudos

## Introdução

Ruby é uma linguagem de programação interpretada, de fácil leitura e altamente produtiva. Para testar códigos rapidamente, pode-se usar o terminal com o comando `irb` (Interactive Ruby).

---

## Conceitos Básicos

### Entrada e Saída

```ruby
puts "texto"      # Exibe na tela
gets              # Captura entrada do usuário
gets.chomp        # Captura e remove o '\n' (Enter)
```

### Inspeção de variáveis

```ruby
variavel.inspect  # Mostra o conteúdo com detalhes (inclui '\n')
```

### Comentários

```ruby
# Comentário de uma linha
=begin
Comentário de
múltiplas linhas
=end
```

### Interpolação de Strings

```ruby
nome = "Gui"
puts "Olá #{nome}"  # Correto com aspas duplas
```

---

## Conversão de Tipos (Coerção)

```ruby
.to_i  # Inteiro
.to_f  # Float
.to_s  # String
```

## Operadores Aritméticos

```ruby
+ soma
- subtração
* multiplicação
/ divição
% mod = resto da divição
** esponeciação = potência
```

## Operadores Relacionais

```ruby
> maior que 
< menor que 
>= maior igual 
<= menor igual
== iguais 
!= diferente
<=> spaceship 
    quando os dois elementao são iguais ele retorna 0
    quando o elemento da direita -> e maoir retorna -1
    quando o elemento da esquerda <- e maoir retorna 1
```

## Atribuições Compostas

```ruby
= recebe
+= variavel recebe variavel + alguma coisa 
-= variavel recebe variavel - alguma coisa 
*= variavel recebe variavel * alguma coisa 
/= variavel recebe variavel / alguma coisa 
%= variavel recebe variavel % alguma coisa 
**= variavel recebe variavel ** alguma coisa 
```

---

## Estruturas Condicionais

```ruby
if condicao
elsif outra_cond
else
end

unless (a menos )condicao
  # executa se falso
end

case (caso) variavel
when (onde) valor1
when valor2
else
end
```

## Operadores Lógicos

```ruby
&& / and : e       (os dois tem que ser verdadeiros)
|| / or  :ou       (uma das duas condições tem que ser verdadeira)
!  / not :negação  ( inverte o resultado verdadeiro ou falso)
```

---

## Estruturas de Repetição

```ruby
while (enquanto) condicao
  # código
end

until(ate que ) condicao
  # código
end

5.times { puts "Oi" } repete a quantidade informado

```

## Ranges e Intervalos

```ruby
1..5   # Inclui 5
1...5  # Vai até 4
```

---

## Arrays

```ruby
arr = []
arr.push(1)
arr.delete(1)
```

## Hashes

```ruby
h = { a: "123", b: "456" }
puts h[:a]  # Acessa valor pela chave
```

## Símbolos

```ruby
:a  :b  :c
# Strings imutáveis e eficientes na memória
```

## Iteradores

```ruby
arr.each do |el|
  puts el
  puts el *2
end

(passe em cada elemento e faça) mostre o elemento e depois mostre esse mesmo elemento muldiplicado por 2
```

---

## Programação Orientada a Objetos
#OS PILARES DA ORIENTAÇÃO A OBJETOS

#Abstração 
    imaginar o objeto
        identidade única
        Atributos
        Métodos
#Encapsulamento
    esconder as propiedades dos objetos para obter + segurança
#Herança
    permitir o reúso de código
#Polimorfismo
     é a capacidade de referencias um objeto de várias formas diferentes

### Conceitos

- **Classe**: Modelo do objeto
- **Objeto**: Instância da classe
- **Encapsulamento**: Oculta atributos internos
- **Herança**: Reutiliza comportamentos
- **Polimorfismo**: Múltiplas formas de um método

### Classe e Objeto
#classes
    é um gabarito para a definição de objetos

    atraves da definição de uma classe, descreve-se que propriedades/atributos e métodos/ações o objeto terá

#Em resumo
    uma classe representa um conjunto de objetos com características afins.

    uma classe define o comportamento dos objetos atraveś de seus métodos , e quais estados ele é capaz de manter através de deus atributos.

#especificar classes para entidades
fisicas (caminhão, carro ...)
conceituais (processo quimico, matricula...)
software (lista encadeada, arquivo)

- Camel Casse: nome da classe inicia com letra maiúscula e toda nova palabra tem letra maiúscula.
Ex NomeDaMinhaClasse

#O corpo da classe deve ter:
    atributos
    métodos
    construtor(método de inicialização)

#intanciando uma classe 
```ruby
    nomeDoObjeto = NomeDaClasse.new
    
```

caso a classe esteja na mesma pasta do projeto, para se usar ela é só por o comando (require_relative "nome do arquivo sem o .rb") 

```ruby
class Pessoa
end

pessoa = Pessoa.new
```

### Atributos com `attr_`
em java podemos usar o attr_accessor para substituir os get/set, ficando mais limpo e evitando reptições no codigo

attr_reader : serve apenas para mostras sem deixar guardar

attr_whriter : serve apenas para guardar sem mostrar
```ruby
class Pessoa
  attr_accessor :nome, :idade
end
```

### Construtor (initialize)
o metodo utilizado para iniciar seria o initialize, ele vai funcuionar passando por parametros, como no ex abaixo nome e idade, na hora que for instanciar pode fazer tudo na mesma linha passando por parametro
esse metodo tem que ficar dentro da classe porque pode gerar erros, afinal um obejeto herdam de obejeto

```ruby
class Pessoa
  def initialize(nome, idade)
    @nome = nome
    @idade = idade
  end
end
```

---

## Herança
Herança "<"
    classe filha < classepai
    SubClass < SuperClass

```ruby
class Pai
end

class Filho < Pai
end
```

### Override e `super`
# override
sobrescrecer(reescrever) metodos da classe pai que ja existia, para dar funcionalida a classe herdade
# super
serve para ivocar o método correspondente na classe pai 

```ruby
class Pai
  def saudacao
    "Olá"
  end
end

class Filho < Pai
  def saudacao
    super + ", tudo bem?"
  end
end
```

---

## `self` e Escopos

- Dentro da classe: se refere à própria classe
- Fora da classe: refere-se ao `main`

## Métodos de Classe vs Instância
O nome do método deve iniciar com letra minúscula e para nomes compostos deve usar o padrão snke_case
    EX: nome_do_meu_metodo
```ruby
class Teste
  def ola
    "instância"
  end

  def self.hello
    "classe"
  end
end
```

---

## Constantes
Constante: É declarada com letras maiuculas (não pode mudar depois que for informada)

constantes podem ser armazenada em uma classe para ser chamada ao longo do programa 
```ruby
class Teste
  PI = 3.14
end

puts Teste::PI
```

## Módulos e Mixins
# Módulo
São similares a classes em relação ao fato de que tambè armazenam uma coleção de métodos, contants, ou efinições de módulo e classes 

Diferente das classes, você não pode criar objetos baseados em módulo nem pode criar módulos que herdan desse módulo 

 objetivos
 priemeiro eles agem como nomespace, permitendo que você defina métodos cujos nomes não irão colidir com aqueles definidos em outras partes de um programa

 segundo pemitem que vocẽ compartilhe funcionalidades entre classes
 
# Mixins
permite que faça uma pseudo herança multipla
faz varias combinações para que possa ter uma herança multipla 
 
```ruby
module Pagamento
  def pagar(valor)
    "Pagando #{valor}"
  end
end

class Compra
  include Pagamento
end
```

## Polimorfismo & Duck Typing

Ruby não exige tipo explícito; se o objeto responde ao método, é suficiente.

Polimorfismo significa "muitas formas". Em Ruby, isso quer dizer que métodos com o mesmo nome podem funcionar de formas diferentes dependendo da classe que os implementa.

Duck typing é um princípio do Ruby que diz:

    "Se anda como um pato e faz quack como um pato, então é um pato."

Ruby não se importa com o tipo da variável, mas sim se ela responde ao método esperado.

reabrindo classe == monkey patch
---

## Manipulação de Strings
aplicado em qual quer string, ele separa em um vetor cada palavra por espaço

para separar letra por letra e so usar da seguinte forma 
"palavraUsada".split("")

```ruby
"abc def".split     # ["abc", "def"]
"abc".split("")    # ["a", "b", "c"]
```

## Trabalhando com Arquivos

```ruby
File.open('arquivo.txt', 'w') { |f| f.puts "Oi" }
File.open('arquivo.txt', 'r') do |f|
  f.each_line { |linha| puts linha }
end
```

## ARGV (Argumentos de linha de comando)

```ruby
puts ARGV.inspect
```

---

## Gems e Bundler

- Instalar gem: `gem install nome_da_gem`
- Requerer: `require 'nome_da_gem'`
- `Bundler` gerencia dependências via `Gemfile`

```ruby
# Gemfile
source 'https://rubygems.org'
gem 'cpf_utils'
```

```sh
bundle install
```

---

## Referências Oficiais

- [Documentação Ruby](https://ruby-doc.org)
- [Ruby Style Guide](https://rubystyle.guide)
- [RubyGems](https://rubygems.org)
- [IRB](https://ruby-doc.org/stdlib/libdoc/irb/rdoc/IRB.html)
- [Bundler](https://bundler.io)
- [Guia POO Ruby](https://ruby-doc.org/core/classes/Object.html)

---
