# Tipos de Variáveis em Python

Em Python, variáveis são contêineres para armazenar valores de dados. Variáveis em Python podem conter dados de diferentes tipos, e o tipo de uma variável é determinado dinamicamente quando um valor é atribuído. Aqui, vamos abordar os principais tipos de variáveis e alguns conceitos adicionais sobre tipos de variáveis em Python.

## 1. Variáveis Globais

- **Definição**: Variáveis declaradas fora de uma função ou no corpo principal do código.
- **Escopo**: Acessíveis em qualquer lugar dentro do arquivo e podem ser acessadas e modificadas por qualquer função no programa.

Exemplo:
  ```python
  x = 10  # Variável global
  
  def exibir():
      print(x)  # Acessando a variável global dentro de uma função
  
  exibir()
  ```

## 2. Variáveis Locais
- **Definição**: Variáveis definidas dentro de uma função e que só são acessíveis dentro dessa função.
- **Escopo**: Limitado à função onde são declaradas.

Exemplo:
  ```python
  def exibir():
      y = 5  # Variável local
      print(y)
      
  exibir()
  # print(y)  # Isso causará um erro, pois 'y' é uma variável local
  ```

## 3. Variáveis de Instância
- **Definição**: Variáveis definidas dentro de uma classe e associadas a uma instância (ou objeto) dessa classe. Cada objeto possui sua própria cópia das variáveis de instância.
- **Escopo**: Limitado à instância à qual estão associadas.

Exemplo:
  ```python
  class Carro:
      def __init__(self, cor):
          self.cor = cor  # Variável de instância
          
  carro1 = Carro("vermelho")
  carro2 = Carro("azul")
  
  print(carro1.cor)  # Saída: vermelho
  print(carro2.cor)  # Saída: azul
  ```

## 4. Variáveis de Classe
- **Definição**: Variáveis que são compartilhadas entre todas as instâncias de uma classe. Elas são definidas dentro de uma classe, mas fora de qualquer método de instância.
- **Escopo**: Compartilhado entre todas as instâncias da classe; mudanças em uma instância refletem nas outras.

Exemplo:
  ```python
  class Carro:
      rodas = 4  # Variável de classe
      
      def __init__(self, cor):
          self.cor = cor  # Variável de instância
          
  carro1 = Carro("vermelho")
  carro2 = Carro("azul")
  
  print(carro1.rodas)  # Saída: 4
  print(carro2.rodas)  # Saída: 4
  Carro.rodas = 6
  print(carro1.rodas)  # Saída: 6, pois 'rodas' é uma variável de classe
  ```

## 5. Constantes
- **Definição**: Variáveis cujos valores não mudam ao longo do programa. Em Python, as constantes são tipicamente escritas em letras maiúsculas para diferenciá-las de outros tipos de variáveis.
- **Escopo**: Podem ser globais ou locais, mas destinam-se a permanecer inalteradas.

Exemplo:
  ```python
  PI = 3.14159
  GRAVIDADE = 9.8
  ```

## 6. Variáveis Estáticas
- **Definição**: Semelhantes às variáveis de classe, as variáveis estáticas são compartilhadas entre todas as instâncias de uma classe. São definidas usando o decorador `@staticmethod`.
- **Escopo**: Compartilhado entre todas as instâncias de uma classe.

Exemplo:
  ```python
  class Exemplo:
      contador = 0
      
      @staticmethod
      def aumentar():
          Exemplo.contador += 1
          
  Exemplo.aumentar()
  print(Exemplo.contador)  # Saída: 1
  ```

## 7. Variáveis Não-locais
- **Definição**: Variáveis declaradas dentro de uma função aninhada para indicar que não são locais para aquela função, mas também não são globais. Podem acessar variáveis da função envolvente (externa).
- **Escopo**: Limitado a funções aninhadas, mas permite acesso a variáveis na função externa.

Exemplo:
  ```python
  def externa():
      x = 5
      
      def interna():
          nonlocal x
          x = 10
          print("Interna x:", x)
      
      interna()
      print("Externa x:", x)

  externa()
  # Saída:
  # Interna x: 10
  # Externa x: 10
  ```

## Resumo
- **Variáveis Globais**: Acessíveis em todo o código; declaradas fora de funções.
- **Variáveis Locais**: Acessíveis apenas dentro da função onde são definidas.
- **Variáveis de Instância**: Únicas para cada objeto, definidas dentro de métodos de classe.
- **Variáveis de Classe**: Compartilhadas entre todas as instâncias de uma classe, definidas no escopo da classe.
- **Constantes**: Valores que permanecem constantes, normalmente escritas em maiúsculas.
- **Variáveis Estáticas**: Compartilhadas entre todas as instâncias; acessadas com `@staticmethod`.
- **Variáveis Não-locais**: Usadas dentro de funções aninhadas para acessar variáveis da função externa.

Cada tipo de variável em Python serve a um propósito diferente, dependendo do escopo, persistência e comportamento necessário no programa. Compreender esses tipos é essencial para escrever um código organizado e eficiente.
