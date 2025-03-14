# Instruções
- Faça uma cópia deste arquivo .md para um repositório próprio
- Resolva as 8 questões objetivas assinalando a alternativa correta e **justificando sua resposta.**
- Resolva as 2 questões dissertativas escrevendo no próprio arquivo .md
- Lembre-se de utilizar as estruturas de código como ``esta aqui com ` `` ou
```javascript
//esta aqui com ```
let a = "olá"
let b = 10
print(a)
```
- Resolva as questões com uso do Visual Studio Code ou ambiente similar.
- Teste seus códigos antes de trazer a resposta para cá.
- Cuidado com o uso de ChatGPT (e similares), pois entregar algo só para ganhar nota não fará você aprender. Não seja dependente da máquina!
- Ao final, publique seu arquivo lista_01.md com as respostas em seu repositório, e envie o link pela Adalove. 

# Questões objetivas
**1) Considerando a execução do código abaixo, indique a alternativa correta e justifique sua resposta.**
```javascript
console.log(x);
var x = 5;
console.log(y);
let y = 10;
```
a) A saída será undefined seguido de erro (correta)

b) A saída será 5 seguido de 10

c) A saída será undefined seguido de undefined

d) A saída será erro em ambas as linhas que utilizam console.log

Justificativa:
A variável foi definida dps do comando,mas como é var o computador entende que ela existe só que está indefinida, já o let tem que ser dado antes do comando para que o computador entenda que ela existe, por isso da erro.

**2) O seguinte código JavaScript tem um erro que impede sua execução correta. Analise e indique a opção que melhor corrige o problema. Justifique sua resposta.**

```javascript
function soma(a, b) {
    if (a || b === 0) {
        return "Erro: número inválido";
    }
    return a + b;
}
console.log(soma(2, 0));
```

a) Substituir if (a || b === 0) por if (a === 0 || b === 0) (correta)

b) Substituir if (a || b === 0) por if (a === 0 && b === 0)

c) Substituir if (a || b === 0) por if (a && b === 0)

d) Remover completamente a verificação if (a || b === 0)

Justificativa:
Para que o computador entenda se A ou B = 0, então é necessário que um valor seja atribuido a cada variável, dentro dos "()" do if.
______
**3) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
function calcularPreco(tipo) {
    let preco;

    switch(tipo) {
        case "eletrônico":
            preco = 1000;
        case "vestuário":
            preco = 200;
            break;
        case "alimento":
            preco = 50;
            break;
        default:
            preco = 0;
    }

    return preco;
}

console.log(calcularPreco("eletrônico"));
```

a) O código imprime 1000.

b) O código imprime 200. (Correta)

c) O código imprime 50.

d) O código gera um erro.

Justificativa:
Dentro da switch é necessário ter a função break para que o comando pare de ser executado, mesmo que fosse "eletrônico" o código rodou até o próximo break que no caso é 200.

______
**4) Ao executar esse código, qual será a saída no console? Indique a alternativa correta e justifique sua resposta.**
```javascript
let numeros = [1, 2, 3, 4, 5];

let resultado = numeros.map(x => x * 2).filter(x => x > 5).reduce((a, b) => a + b, 0);

console.log(resultado);
```
a) 0

b) 6

c) 18

d) 24 (Correta)

Justificativa:
A lista numeros é inicialmente composta pelos valores de 1 a 5. Primeiramente, cada elemento é multiplicado por dois, gerando a nova sequência [2, 4, 6, 8, 10]. Em seguida, são filtrados apenas os números maiores que cinco, resultando na lista [6, 8, 10]. Por fim, os números restantes são somados, obtendo-se o total de 24.
______
**5) Qual será o conteúdo do array lista após a execução do código? Indique a alternativa correta e justifique sua resposta.**

```javascript
let lista = ["banana", "maçã", "uva", "laranja"];
lista.splice(1, 2, "abacaxi", "manga");
console.log(lista);
```

a) ["banana", "maçã", "uva", "abacaxi", "manga", "laranja"]

b) ["banana", "abacaxi", "manga"]

c) ["banana", "abacaxi", "manga", "laranja"] (Correta)

d) ["banana", "maçã", "uva", "abacaxi", "manga"]

Justificativa:
o comando splice() faz com que termos sejam substituidos, primeiro seleciona os termos, 1 e 2 que são referentes a maçã e uva, pois na lista os termos começam a serem contados do zero. Depois é selecionado quais termos substituirão os anteriores, abacaxi e manga.
______
**6) Abaixo há duas afirmações sobre herança em JavaScript. Indique a alternativa correta e justifique sua resposta**

I. A herança é utilizada para compartilhar métodos e propriedades entre classes em JavaScript, permitindo que uma classe herde os métodos de outra sem a necessidade de repetir código.  
II. Em JavaScript, a herança é implementada através da palavra-chave `extends`.


a) As duas afirmações são verdadeiras, e a segunda justifica a primeira. (Correta)

b) As duas afirmações são verdadeiras, mas a segunda não justifica a primeira.

c) A primeira afirmação é verdadeira, e a segunda é falsa.

d) A primeira afirmação é falsa, e a segunda é verdadeira.

Justificativa:
É necessário usar o extends, como em: class ClasseFilha extends ClassePai, no JS, para que seja possível que uma classe herde os métodos de outra, deixando o código mais organizado e compacto.
______
**7) Dado o seguinte código. Indique a alternativa correta e justifique sua resposta.**

```javascript
class Pessoa {
  constructor(nome, idade) {
    this.nome = nome;
    this.idade = idade;
  }

  apresentar() {
    console.log(`Olá, meu nome é ${this.nome} e tenho ${this.idade} anos.`);
  }
}

class Funcionario extends Pessoa {
  constructor(nome, idade, salario) {
    super(nome, idade);
    this.salario = salario;
  }

  apresentar() {
    super.apresentar();
    console.log(`Meu salário é R$ ${this.salario}.`);
  }
}
```


I) A classe Funcionario herda de Pessoa e pode acessar os atributos nome e idade diretamente.  
II) O método `apresentar()` da classe Funcionario sobrepõe o método `apresentar()` da classe Pessoa, mas chama o método da classe pai usando `super`.  
III) O código não funciona corretamente, pois Funcionario não pode herdar de Pessoa como uma classe, já que o JavaScript não suporta herança de classes.

Quais das seguintes afirmações são verdadeiras sobre o código acima?

a) I e II são verdadeiras. (Correta)

b) I, II e III são verdadeiras.

c) Apenas II é verdadeira.

d) Apenas I é verdadeira.

Justificativa:
Resposta: 1- verdadeiro, quando uma class herda os atributos de outra, ela pode usar esses atributos. 2-Sim, isso se chama sobreposição de métodos. A classe funcionário tem uma função método igual a classe pai, na linha super.apresentar() dentro do método Funcionario garante que o método da classe pai seja executado antes de adicionar funcionalidades específicas de Funcionario.
______

**8) Analise as afirmações a seguir. Indique a alternativa correta e justifique sua resposta.**

**Asserção:** O conceito de polimorfismo em Programação Orientada a Objetos permite que objetos de diferentes tipos respondam à mesma mensagem de maneiras diferentes.  
**Razão:** Em JavaScript, o polimorfismo pode ser implementado utilizando o método de sobrecarga de métodos em uma classe.

a) A asserção é falsa e a razão é verdadeira.

b) A asserção é verdadeira e a razão é falsa.(Correta)

c) A asserção é verdadeira e a razão é verdadeira, mas a razão não explica a asserção.

d) A asserção é verdadeira e a razão é verdadeira, e a razão explica a asserção.

Justifique:
Resposta: O polimorfismo consiste em um mesmo método que pode ser implementado por classes diferentes de formas diferentes, mas possui o mesmo efeito.

______

# Questões dissertativas
9) O seguinte código deve retornar a soma do dobro dos números de um array, mas contém erros. Identifique os problema e corrija o código para que funcione corretamente. Adicione comentários ao código explicado sua solução para cada problema.

```javascript
a = []
function somaArray(numeros) {

    for (i = 0; i < numeros.length; i += 1) { //o Size é usado para saber a quantidade de elementos em um objeto, mas não é usado em listas
                                             //para listas tem que usar o length
                                             //Retirei o objeto soma porque ele não tinha utilizade

        lista.push(numeros[i])//Estou criando um lista com todos os numeros
        
        
    }//Aqui, teremos um acumulador que percorre todos os elementos da lista.
    //Primeiro, o acumulador começa com 0 e é somado ao dobro do primeiro elemento da lista.
    //Esse resultado se torna o novo valor do acumulador, e esse processo se repete para todos os elementos.
    //Assim, teremos o exato resultado pedido para a questão, a soma do dobro dos números de um array.
    resultado = lista.reduce((acumulador, numeros) => acumulador + (numeros*2), 0) //Essa função reduce reduz a lista a um único número
    return resultado; 
    
};
console.log(somaArray([1, 2, 3, 4]));
```
______
10) Crie um exemplo prático no qual você tenha duas classes:

- Uma classe `Produto` com atributos `nome` e `preco`, e um método `calcularDesconto()` que aplica um desconto fixo de 10% no preço do produto.
- Uma classe `Livro` que herda de `Produto` e modifica o método `calcularDesconto()`, aplicando um desconto de 20% no preço dos livros.

Explique como funciona a herança nesse contexto e como você implementaria a modificação do método na classe `Livro`.
