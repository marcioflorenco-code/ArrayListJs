# ArrayListJs

Inicialmente antes de começar a usar os métodos para manipulação de listas , e preciso entender o que elas são : 

#O que e uma lista (array) .... ?

Uma lista (array) e uma estrutura que nos permite armazenar valores , seja eles numeros, textos e objetos, dentro de uma única variável , como no exemplo abaixo .

let numeros = [1, 2, 3, 4, 5];

Mostrado como e a estruturação de uma lista , vou mostrar agora 3 métodos (filter , map , reduce) , que podemos usar para manipular essas listas .

#Metodo map 

O metodo map , ele vai percorrer todos os elementos da lista e logo em seguida ele cria uma nova lista com as especificações dadas da transformação ou operação do processo , como no exemplo abaixo:

```
let numeros = [1, 2, 3, 4, 5];

let dobrar = numeros.map(numero => numero * 2);

console.log(dobrar);
```

Nessa manipulação de lista , o map vai passar por todos os valores da lista , e ao passar pelo valor ,vai multiplica-lo por 2 , e em seguida o resultado dessa operação será armazenado em uma nova lista que irá seguir a ordem de índice da lista anterior .

```
[2, 4, 6, 8, 10]
```

#Metodo filter 

Nesse metodo, a sua função e relacionada a filtragem de valores , onde ela vai buscar apenas valores que atendem a uma condição específica , e nisso ela vai gerar tambem uma nova lista , podendo diminuir o seu tamanho ou manter-lo no tamanho normal caso todos valores atendam a condição , como por exemplo:

```
let numeros = [1, 2, 3, 4, 5, 6];

let pares = numeros.filter(numero => numero % 2 === 0);

console.log(pares);
```

Nesse caso o filter vai passar por todos os valores da lista , e em seguida vai ver se o resto da divisão por 2 e igual a 0 , dado os números que são pares ele vai criar uma nova lista , que nessa situação será menor que a original 

```
[2, 4, 6]
```

#Metodo reduce

O metodo reduce por outro lado , percorre os elementos de uma lista e combina seus valores afim de gerar um valor único final , sendo bastante usado para calcular valores finais ou ações que precisam de acumulação , como no exemplo abaixo :

```
let numeros = [10, 20, 30, 40];

let soma = numeros.reduce(
(acumulador, numero) => acumulador + numero, 0);

console.log(soma);
```

Nesse caso o 0 apresentado vai ser o pontapé inicial do meu acumulador , onde em seguida vai ser somado com primeiro valor da lista, e após a primeira somatória o resultado dela irá assumir o lugar do acumulador, e assim sucessivamente os resultaodos da operação apos cada rodada irão sendo acumulados ate que não tenha mais um valor na lista , e assim gerado um resultado final . 


Agora vou mostrar um exemplo onde os 3 métodos podem ser usados de uma maneira conjunta e até mais elegante de maneira encadeada :

```
let alunos = [{ nome: "Marcio", nota: 10 },{ nome:"Joao", nota: 5 },{ nome: "Maria", nota: 9 },{ nome: "Pedro", nota: 6 }];

let somarNotasAprovados = alunos.filter(aluno => aluno.nota >= 7).map(aluno => aluno.nota).reduce((total, nota) => total + nota, 0);

console.log(somaNotasAprovados);

``` 

Como mostrado, e dado uma lista de alunos onde nela haverá seu nome e uma nota para cada um deles, como uma média escolar , onde o filter inicial vai pegar e puxar apenas os alunos cujo a nota seja maior ou igual a 7 ,e o map ele vai extrair e criar uma nova lista apenas com as notas desses alunos aprovados, onde as outras informações como nome não serão mostradas , e por fim o reduce , ele vai pegar as notas dos alunos aprovados , e vai acumular elas gerando uma soma de ambas as notas , iniciando do zero como foi apresentado no exemplo de reduce .
