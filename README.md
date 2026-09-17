# Atividade3
# 🚀 Manipulação de Listas em JavaScript
Um tutorial prático e explicativo focado na manipulação de arrays em JavaScript utilizando os métodos funcionais de alta ordem: `map`, `filter` e `reduce`.


## 🧠 Conceitos Fundamentais
Os métodos `map`, `filter` e `reduce` são chamados de Funções de Alta Ordem. Isso significa que eles recebem uma função como parâmetro (*callback*) e a executam para cada elemento do array.

## map()

O método `map()` percorre o array e retorna um **novo array** com a mesma quantidade de elementos, onde cada elemento é o resultado da transformação feita pela função callback.

### Sintaxe
```javascript
const novoArray = arrayOriginal.map((elemento, indice, array) => {
  return elementoTransformado;
});

Exemplo 1: Extrair uma propriedade específica de um array de objetos
JavaScript
const usuarios = [
  { nome: 'Ana', idade: 25 },
  { nome: 'Carlos', idade: 30 },
  { nome: 'Marina', idade: 22 }
];
// Mapeia o array extraindo apenas a propriedade "nome"
const nomes = usuarios.map(usuario => usuario.nome);
console.log(nomes); // Saída: ['Ana', 'Carlos', 'Marina']


Exemplo 2: Converter temperaturas de Celsius para Fahrenheit
JavaScript
const celsius = [0, 10, 20, 30];
// Aplica a fórmula de conversão a cada temperatura do array
const fahrenheit = celsius.map(temp => (temp * 9 / 5) + 32);
console.log(fahrenheit); // Saída: [32, 50, 68, 86]
```


## filter()
O `filter()` cria um novo array contendo apenas os elementos que retornam true na condição testada pelo callback.

### Sintaxe
``` javaScript
const novoArray = arrayOriginal.filter((elemento, indice, array) => {
  return condicaoBooleana;
});


Exemplo 1: Filtrar pessoas com idade maior ou igual a 18 anos
JavaScript
const pessoas = [
  { nome: 'Lucas', idade: 16 },
  { nome: 'Beatriz', idade: 21 },
  { nome: 'Gabriel', idade: 17 },
  { nome: 'Fernanda', idade: 19 }
];
// Filtra apenas os objetos com idade maior ou igual a 18
const maioresDeIdade = pessoas.filter(pessoa => pessoa.idade >= 18);
console.log(maioresDeIdade);
// Saída: [ { nome: 'Beatriz', idade: 21 }, { nome: 'Fernanda', idade: 19 } ]


Exemplo 2: Filtrar palavras com mais de 5 letras
JavaScript
const palavras = ['sol', 'javascript', 'web', 'computador', 'code'];
// Filtra apenas as palavras com comprimento maior que 5
const palavrasLongas = palavras.filter(palavra => palavra.length > 5);
console.log(palavrasLongas); // Saída: ['javascript', 'computador']
``` 

## reduce()
O `reduce()` processa cada elemento do array e acumula o resultado para reduzir a lista a um único valor final (um número, string, objeto ou novo array).

### Sintaxe
``` javaScript
const resultado = arrayOriginal.reduce((acumulador, elementoAtual) => {
  return novoValorDoAcumulador;
}, valorInicial);


Exemplo 1: Somar o valor total de itens em um carrinho de compras
JavaScript
const carrinho = [
  { produto: 'Caderno', preco: 15 },
  { produto: 'Caneta', preco: 3 },
  { produto: 'Mochila', preco: 80 }
];
// Acumula os preços dos produtos a partir do valor inicial 0
const valorTotal = carrinho.reduce((acumulador, item) => acumulador + item.preco, 0);
console.log(valorTotal); // Saída: 98


Exemplo 2: Contar a frequência de elementos repetidos
JavaScript
const frutas = ['maçã', 'banana', 'maçã', 'laranja', 'banana', 'maçã'];
// O acumulador inicia como um objeto vazio {}
const contagem = frutas.reduce((acc, fruta) => {
  acc[fruta] = (acc[fruta] || 0) + 1;
  return acc;
}, {});
console.log(contagem); // Saída: { maçã: 3, banana: 2, laranja: 1 }
```
