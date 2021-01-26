## Introdução a programação e a Lógica

### O que é um algoritmo
Um algoritmo é uma sequência de passos para realizar uma tarefa. Essa sequência deve ser *correta*, *completa* e *clara*.

A ideia de sequência é que os passos do algoritmo tem ordem para serem executados, e essa ordem deve ser preservada.

*Correta* significa que a sequência de passos deve, com certeza, atingir o objetivo. Um algoritmo é considerado correto se, após o último passo ser executado, chega-se ao resultado esperado.

*Completa* significa que a sequência não deve ter nenhum passo faltando. Todas as informações e instruções para chegar ao objetivo devem estar no passo-a-passo. Quem lê e executa os passos não deve ter que "inferir" nenhum passo, nem preencher nenhuma lacuna.

*Clara* significa que não pode haver ambiguidade em nenhum dos passos. As informações e instruções devem estar descritas de uma maneira que não gerem dúvidas: a natureza das informações deve ser específica e não pode haver duas maneiras distintas de executar uma instrução. Além disso, quem lê ou executa o algoritmo deve chegar ao resultado fazendo exatamente o que a sequência de passos define.

> Normalmente, quando aprendemos sobre algoritmo, os exemplos dizem que é como uma "receita de bolo". Isso definitivamente não é verdade! A analogia é utilizada porque as receitas possuem um "modo de fazer" sequencial, orientado por passos, mas algumas considerações precisam ser feitas.
Primeiro, as receitas não são claras: não existe padrão para as quantidades dos ingredientes. Uma xícara de chá não tem uma medida exata, assim como uma colher de sopa cheia não significa uma porção exata. Duas pessoas diferentes podem seguir a mesma receita com o material que possuem em casa e as quantidades não serão as mesmas. Além disso, passos como "bata as claras em neve" deixam ambiguidades: como? com qual instrumento? o que define "em neve"?
Segundo, as receitas não são completas: instruções como "pré-aqueça o forno" não traz todas as informações necessárias. Por quanto tempo deve-se pré-aquecer o forno? A qual temperatura?
Por fim, as receitas não são corretas pois existe um risco de seguir todos os passos, exatamente como descrito, na sequência, e não chegar ao resultado esperado.

### Níveis de Abstração

Para escrever um programa, é necessário utilizar uma linguagem que, ao mesmo tempo, seja compreendida pelo computador e pelo programador. Para que seja entendida pelo computador, essa linguagem necessita ter uma sintaxe precisa e instruções claras. Para que seja entendida pelo programador, é importante que ela tenha relação com a linguagem humana e seja de fácil compreensão.

Por isso, as linguagens de programação possuem diferentes níveis de abstração, ou seja, o quão detalhadas são as instruções em relação as operações básicas que um computador pode realizar.

Considere um algoritmo que ensina a trocar um pneu de um carro. Uma sequência de instruções como "pegue a chave de roda", "remova os parafusos da roda", "puxe a roda até que ela saia" parece suficiente. Entretanto, só seria útil para quem saber o que é uma chave de roda, e para quem sabe remover um parafuso.

Algumas pessoas precisariam de instruções mais exatas, como "encaixe a extremidade hexagonal da chave de roda no parafuso", "enquanto o parafuso não sair, gire a chave de roda no sentido anti-horário para desrosquear o parafuso".

O primeiro algoritmo possui um maior nível de abstração em relação ao segundo algoritmo. Em um contexto computacional, uma linguagem de baixo nível necessita de instruções específicas de alocação do espaço de memória e algumas chamadas do sistema operacional para exibir um texto na tela. Por outro lado, ao usar uma linguagem de alto nível, o programador necessita apenas usar um simples comando de impressão.

### Compilação x Interpretação
Ainda que uma linguagem de programação seja um meio intermediário entre o programador e o computador, ela em seu estado original não é adequada para as operações de baixo nível do sistema. Para que ela possa ser utilizada, é necessário converter o código escrito pelo programador em linguagem de máquina. Esse processo pode ser feito de duas formas distintas: compilação ou interpretação.

No processo de compilação, o código-fonte é convertido um arquivo executável que contém as instruções de baixo nível necessárias para execução do programa pelo computador. Note que não existe um processo simples para "descompilar" o programa, de modo que ter o arquivo executável não nos dá acesso ao código-fonte. Os programas usados em desktop normalmente são compilados.

No processo de interpretação, o código-fonte é convertido em instruções para o computador em tempo real. Isso permite um maior dinamismo para o programador enquanto ele trabalha, visto que ele pode ver de forma imediata as mudanças que ele faz no programa. Por outro lado, a velocidade de execução do programa tende a ser menor, visto que a cada execução é necessário fazer a conversão do código novamente para instruções de máquina. Vale notar que não existe um arquivo executável, então o programa é distribuído no formato de código-fonte.

## Javascript

O Javascript é a linguagem padrão para as páginas da web. É com ele que são implementados desde sites institucionais até sistemas complexos como o Google Drive. O browser possui dentro de si um interpretador da linguagem, que é responsável por executar os scripts presentes nas páginas.

### Variáveis
Ao programar, temos a possibilidade de armazenar valores na memória do programa e realizar operações com eles. Para isso, fazemos o uso de variáveis, que são espaços de memória que armazenam valores.

As variáveis são criadas utilizando a palavra chave **let**. O nome da variável é definido livremente pelo programador, desde que algumas regras sejam seguidas:

- Não pode conter caracteres especiais, como acentos, cedilhas ou til
- Não pode conter espaços
- Não pode começar com um número, mas pode conter números em outras posições

```
let salario;
```

Para armazenar um valor em uma variável, usamos o operador **=**.

```
let salario = 1000;
```

No caso do Javascript, a memória é individual para cada página, de forma que duas páginas exibidas em abas diferentes não compartilham valores de memória. Ao recarregar a página, limpa-se a memória e reinicia-se qualquer script que esteja presente na página.

Não podemos redeclarar uma variável, pois isso gera um erro de execução. Para alterar o valor de uma variável já, basta utilizar o operador **=** sem a necessidade da palavra **let**.

```
salario = 2000;
```

Perceba que toda linha é finalizada com um ponto-e-vírgula, que indica que a instrução finalizou.

> Finalizar instruções com ponto-e-vírgula é um requisito do Javascript, ainda que este possua um mecanismo que permita que ele tenha um certo nível de tolerâncias à essa omissão.

#### var x let x const

A versão nova do Javascript, lançou **let** e **const** para melhorar e corrigir algumas questões que o **var** tinha nas versões anteriores, o indicado é não usarmos mais var.

O const deve ser usado em casos onde a variável não precisa ser reatribuída, sobescrita. Ela bloqueia o valor, e se houver tentativa de mudar, irá mostrar um erro.
Já o let você pode usar para declarar variavéis e alterar o valor delas quando necessário. Lembrando que o valor dessa variavél é de acordo com o escopo em que se encontra. Se por exemplo, ela está dentro de uma função, o valor dela só valerá dentro daquela função.

### Tipos e Operações

No Javascript, o tipo da variável é definido pelo valor que esta atribuído a ela naquele momento. Os seguintes tipos estão presentes nas linguagem:

| TIPO    | DESCRIÇÃO  |
| --------|----------- |
| number  | valores numéricos, inteiro ou decimal |
| string  | texto |
| boolean | verdadeiro ou falso|
| object  | armazena diversos valores organizados em pares de chave e valor|
| *array  | armazena diversos valores organizados por posição|

> Array não é tecnicamente um tipo de variável, visto que o Javascript o identifica simplesmente como `object`. Porém, incluímos array nessa tabela por motivos didáticos.
> Apesar de citarmos os objetos e vetores entre os tipos de variável, sugerimos que eles não sejam exemplificados nem aprofundados nesse momento da aula.

O tipo de uma variável é importante pois ele determina o resultado de operações realizadas com ela, além de funcionalidades disponíveis. Podemos por exemplo, somar duas variáveis numéricas e obter o resultado da conta, porém se somamos duas variáveis do tipo *string*, o resultado é a união dos dois valores, o que é chamado de *concatenação*.

```
1 + 1 //resutado é 2
'1' + '1' //resultado é 11
```
Os seguintes operadores estão disponíveis em Javascript:

#### Operadores aritméticos
| Operador | Descrição |
|----------|---------- |
| = | atribui um valor à uma variável |
| + | adição ou concatenação, no caso de strings |
| - | subtração |
| * | multiplicação |
| / | divisão |
| ** | potenciação |
| ++ | incremento |
| - - | decremento |


Note que para armazenar o resultado de uma operação em uma variável, é necessário a utilização do operador **=**. Realizar a operação não altera o valor da variável por si.

```
let salario = 1000;
let aumento = 500;

salario + aumento; //resultado é descartado
salario = salario + aumento; //o resultado é armazenado na variável salário
```

#### Criando arquivos .js

Os scripts de uma página são geralmente escritos em arquivos separados com a extensão **.js**. Para que a página carregue esse script é necessário inserir dentro do seu HTML a seguinte tag:

`<script src="scripts.js" defer></script>`

É recomendável que essa tag seja inserida no **head** da página. Note a palavra **defer** na abertura da tag, que indica que o script só deve ser executado quando todo o restante da página já tiver sido carregado.

> Utilize esse momento para propor alguns exercícios simples com operações. Para isso, faça uso das funções *alert* para exibir os valores e *prompt* para obter valores do usuário.


### Conversão de valores
Muitas vezes é necessário converter o tipo de uma variável para utilizá-la de forma correta no contexto do que estamos programando. A função *prompt*, por exemplo, sempre retorna uma variável do tipo **string**, mesmo que o usuário tenha inserido um valor numérico. A tentativa de somar variáveis que foram obtidas pelo método prompt vai resultar na concatenação dos valores.

```
let idade = prompt('Digite sua idade'); //o usuário digitou 11 no popup

let idadeRelativa = idade + 20;

alert(idadeRelativa); //o resultado é 1120
```

Para converter tipos de variável, o Javascript possui as seguintes funções:

| Função | Descrição |
|--------|-----------|
| Number | Converte o valor em **number** |
| String | Converte o valor em **string** |
| Boolean | Converte o valor em **boolean** |

```
let idadeString = prompt('Digite sua idade'); //o usuário digitou 11 no popup
let idade = Number(idadeString); //converte a string em number

let idadeRelativa = idade + 20;

alert(idadeRelativa); //o resultado é 31
```

> Note que ao tentar converter um valor não numérico em Number, o resultado será *NaN*, que significa *Not a Number*. 


### Condicionais

Uma das capacidades presentes em todas as linguagens de programação é a capacidade de criar algoritmos para tomadas de decisão. A estrutura mais simples para definir o fluxo do programa de acordo à um valor é o **if**.

```
let palavra = prompt('Fale, amigo, e entre.');

if(palavra == 'mellon'){
  alert('Você pode passar!');
}
```   

No caso acima, o alert só será executado caso o valor da variável *palavra* seja igual a `mellon`. Veja que o operador **==** realiza a comparação dos dois valores, e retorna um valor booleano: *true* ou *false*.

Podemos também definir instruções que sejam executadas caso a condição lógica resulte em *false*:

```
let resposta = prompt('Qual a resposta para a vida, o universo e tudo mais?');

if(resposta == '42'){
  alert('Você está correto!');
}else{
  alert('Você errou...');
}
```  

Nesse caso, o alert com o texto *Você errou...* será executado toda vez que o valor inserido pelo usuário **seja diferente** de '42'.

#### Operadores Lógicos
Toda operação lógica resulta em um valor booleano, ou seja, `true` ou `false`;
| Operador | Descrição |
|----------|---------- |
| == | igual |
| != | diferente |
| ! | negação |
| > | maior |
| < | menor |
| >= | maior ou igual |
| <= | menor ou igual |


### Loops
Loops, ou laços, são estruturas de programação que são executadas um número pré determinado de vezes até que uma condição definida seja satisfeita. Essas estruturas são boas ferramentas para um programador pois permitem que você reduza o tamanho do seu código executando tarefas repetitivas com menos linhas, ou itere item a item em uma lista.

Em pseudocódigo nós usamos a palavra ENQUANTO, essa palavra indicava que os passos que estivessem descritos em seguida seriam repetidos até a nossa condição se tornar falsa. Qual condição? Não conseguimos simplesmente mandar o código se repetir sozinho, para esse laço acontecer é necessário existir uma condição para avaliar se o laço vai ser executado ou não, do mesmo jeito que fazemos com o SE/SENÃO. 

A estrutura básica seria:

    ENQUANTO CONDIÇÃO FOR VERDADEIRA FAÇA
        Instruções a serem repetidas

A sintaxe do for no javascript é:
  for(inicio; fim; passo){
    Código a ser repetido enquanto o critério de fim estiver válido
  } 

```
let lista = ["pessoa1", "pessoa2", "pessoa3", "pessoa4"];

for(let indice = 0 ; indice < lista.length; indice++){
  console.log(lista[indice])
}
```  

Nesse laço criamos uma variável chamada índice que é o nosso contador com o seu valor de início que é zero. No segundo valor indicamos que o nosso loop vai ser executado enquanto o valor do índice for menor que o tamanho da lista. E por fim, no último valor indicamos qual é o passo do nosso loop, neste caso é somado um ao índice no final de cada rodada do laço.

### Funções

Funções são fundamentais em JavaScript. Uma função é um procedimento de JavaScript - um conjunto de instruções que executa uma tarefa ou calcula um valor. Para usar uma função, você deve defini-la em algum lugar no escopo onde você quiser utilizá-la.

```
function mostrarMensagem() {
  alert('seja bem vindo');
}

mostrarMensagem();
``` 
Para executá-la, basta escrever o nome da função e colocar o parênteses
em sequência, preenchendo-os com conteúdo quando necessário.

#### Arrow Function
A estrutura conhecida como arrow function foi adicionada na última versão do JavaScript e tem duas grandes diferenças de uma função normal: ela é, entre outras coisas, uma forma mais compacta de declaração e tem o que chamam de contexto simplificado, assumindo regras diferentes de uma função comum do JavaScript.
Para criar uma dessas funções, primeiramente você precisa criar a variável que irá recebê-la. O nome da variável será o nome da sua função, que
você poderá utilizar para executá-la. 

```
const mostrarMensagem = () => {
  alert('seja bem vindo');
};

mostrarMensagem();

``` 

### Document Object Model

O document object model, ou DOM, é uma estrutura no JavaScript utilizada para interagir diretamente com os elementos HTML na página.

Essa estrutura é criada assim que uma página HTML é carregada por completo no navegador, e coloca cada um dos elementos desta como nós dentro de uma árvore de elementos acessíveis pelo JavaScript.

Podemos começar a requisitar elementos HTML, manipulá-los, criar novos e apagá-los utilizando a variável ‘document’. Abaixo temos uma lista das propriedades e funções mais comuns dessa variável:

| código | descrição |
|----------|---------- |
| querySelector() | retorna o primeiro elemento que for especificado como parâmetro, pode ser um classe, um id ou uma tag mesmo |
| querySelectorAll() | faz o mesmo do querySelector, mas ele pega todos os elementos |
| createElement() | cria um novo elemento HTML |

Uma boa prática ao criar seletores de JavaScript é atribuir seus valores à constantes ao invés de variáveis, garantindo que os elementos de HTML que estamos manipulando ao longo do código não serão alterados em nenhum momento. Assim que o elemento está selecionado e salvo, há diversas outras propriedades e funções que podem ser utilizadas para cumprir alguns objetivos.

```
const menuMobile = document.querySelector('.menu');

``` 

| código | descrição |
|----------|---------- |
| appendChild() | adiciona um elemento filho ao elemento atual |
| removeChild() | remove um elemento filho do elemento atual |
| innerHTML | Permite ler ou alterar o valor do conteúdo entre a abertura e o fechamento da tag do elemento |
| classList() | permite ler a classe atribuída ou adicionar/remover uma classe com o .add ou .remove |
| style | permite mexer no css do elemento |

### Eventos HTML
Em uma página web, nós utilizamos uma estrutura de programação orientada à eventos para adequar-se e responder às ações do usuário em nossa página. Para conseguirmos isso, a ideia é que várias funções sejam criadas para serem chamadas quando determinados eventos(como clique, uma passagem de mouse, etc) definidos pelo programador acontecerem. Podemos ver um exemplo disso na seguinte lógica:

Um botão de menu mobile precisa, ao ser clicado, mostrar a barra de navegação para que o usuário possa ir até onde deseja.
Nesse caso, podemos chegar às seguintes conclusões:
- Nosso elemento que recebe o evento é o menu mobile;
- Nosso evento atribuído é o clique;

A função que ele tem que executar é mostrar uma barra de nave-
gação que está atualmente oculta;

O primeiro passo dessa solução é selecionar o elemento HTML que
receberá o evento utilizando um ‘querySelector’. É necessário criar uma função que defina que o nossa barra de navegação vai adicionar uma classe caso ela não a tenha, e removê-la caso ela tenha, que é a forma como alteraremos o CSS. Por fim, precisamos atribuir essa função ao evento onclick do nosso botão, informando ao HTML que quando o usuário clicar nesse elemento, a função atribuída deverá ser executada.

Uma lista completa de eventos pode ser encontrada em:
https://www.w3schools.com/jsref/dom_obj_event.asp