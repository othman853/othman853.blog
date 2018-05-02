---
title: "JavaScript: Objetos, funções e arrays"
date: 2018-05-02T17:09:26-03:00
draft: false
---

Javascript é uma linguagem que possui uma sintaxe muito simples, em outras palavras, se pode expressar uma ideia imensa com poucas linhas de
código.

Entendendo o que são `Arrays`, `Objetos` e `Funções`, se pode fazer praticamente tudo em JavaScript.

## Arrays

São as listas do Javascript, ou seja, eles servem para armazenar múltiplos elementos.

Arrays são representados por um par de colchetes (`[]`).

__Exemplos:__

Podemos ter um array vazio:


``` javascript
  const umArrayVazio = []
```

Um array com dados:

```javascript
  const umArrayComNumeros = [1, 2, 3, 4, 5]
```

Um array com arrays:

```javascript
  const umArrayDeArrays = [[1], [], [3], []]
```

Em Javascript, não é necessário que todos os elementos de um array sejam do mesmo tipo, o que nos permite fazer coisas como:

``` javascript
  const saladaDeFrutas = [1, '2', 'tres', false, undefined, null, /expressao_regular/, {}]
```

Os arrays em Javascript são objetos, o que significa que eles possuem atributos e "métodos". Ou seja, podemos fazer coisas como:

```javascript
  const arraySimples = [1, 2, 4]
  console.log(arraySimples.length) // 3
```

Podemos adicionar novos elementos no final do array:

```javascript
  const arraySimples = [1, 2, 4]
  arraySimples.push(5)
  console.log(arraySimples) // [1, 2, 4, 5]
```

__Acessando elementos de um array:__

```javascript
  const arraySimples = [1, 2, 4]
  const primeiroElemento = arraySimples[0]
  console.log(primeiroElemento) // 1
```

Quando tentamos acessar um elemento que não existe, recebemos `undefined`:

```javascript
  const arraySimples = [1, 2, 4]
  const vigesimoElemento = arraySimples[20]
  console.log(vigesimoElemento) // undefined
```

[Mais informações sobre arrays](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array).


## Objetos

Em Javascript, objetos nada mais são do que um mapa, ou mais simplesmente, um conjunto de pares de informações no formato chave/valor.

Objetos são representados por um par de chaves (`{}`).

__Exemplos:__

Podemos ter um objeto vazio:

```javascript
  const umObjetoVazio = {}
```

Um objeto com campos:

```javascript
  const pessoa = {
    nome: 'Silva',
    idade: 30
  }
```

_Não existe restrição quanto ao tipo de informação que se pode guardar em um campo de um objeto._

Podemos ter, por exemplo:

Um objeto com um campo que contém outro objeto:

```javascript
  const pessoaComPet = {
    nome: 'Silva',
    idade: 30,
    pet: {
      nome: 'Silvinha',
      tipo: 'gato',
      idade: 5
    }
  }
```

Um campo que contém um array:

```javascript
  const resultadoDaLoteria = {
    nome: 'Mega Sena',
    data: '2018-05-02',
    numerosSorteados: [10, 40, 23, 35, 50, 87]
  }
```

Um campo que contém um array que contém outros objetos:

```javascript
  const aviao = {
    fabricante: 'Boeing',
    modelo: '787-900',
    voos: [
      {
        numero: 'LA751',
        horarioDePartida: '07:30',
        origem: 'GRU',
        destino: 'SCL'
      },
      {
        numero: 'LA750',
        horarioDePartida: '16:30',
        origem: 'SCL',
        destino: 'MIA'
      }
    ]
  }
```

### Construindo objetos com variáveis

Podemos construir objetos à partir de outras variáveis, ou seja, não precisamos sempre colocar os dados de maneira estática em cada campo
(como fora demonstrado nos exemplos anteriores). Podemos fazer coisas como:

```javascript
const nome = 'Lopes'
const idade = 30

const pessoa = {
  nome: nome,
  idade: idade
}

// Ou, podemos simplificar para o seguinte:

const pessoa = {
  nome,
  idade
}

```

### Acessando elementos de um objeto

Existem diferentes maneiras de se acessar elementos de um objeto, a mais comum é através do ponto (`.`). Considerando os exemplos acima:

```javascript
  console.log(pessoa.nome) // 'Silva'
  console.log(pessoaComPet.pet.nome) // 'Silvinha'
```

Assim como num array, também podemos usar a notação de chaves para acessar os elementos de um objeto:

```javascript
  console.log(pessoa['nome']) // 'Silva'
  console.log(pessoaComPet['pet']['nome']) // 'Silvinha'
```

Também como nos arrays, acessar um elemento inexistente de um objeto nos retorna undefined:

```javascript
  console.log(pessoa.aaaaaaa) // undefined
  console.log(pessoa['aaaaaaa']) // undefined
```

## Funções

No começo, funções são a parte mais confusa do Javascript, pois a natureza da linguagem permite que as tratemos como qualquer outro objeto,
o que significa que podemos fazer coisas como:

- Guardar uma função em uma variável
- Enviar uma função por parâmetro
- Ter uma função que retorna uma função
- Ter uma função como membro de um objeto

Vamos começar pelo começo, entendendo como declarar uma função. Temos duas opções na hora de declarar uma nova função:

- Usar a palavra reservada `function`
- Definir uma arrow function

Vejamos:

Uma nova `function`:

```javascript

function saudacao() {
  return "Oi"
}

```

Uma arrow function:

```javascript
const saudacao = () => {
  return "Oi"
}

```