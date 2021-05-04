<em>15 - Entrega: Oregon Trail</em>

<h1>Entrega - Oregon Trail</h1>

Revise como se cria um objeto de classe usando uma função construtora para instanciar propriedades e um método de protótipo de comportamento comum a todas as instâncias da classe. Aqui está um exemplo:

```
function Dog (name, breed, isGoodBoy) {
   this.name = name;
   this.breed = breed;
   this.isGoodBoy = isGoodBoy;
}

Dog.prototype = {
   constructor: Dog,
   sit: function () {
       // sitting code here
   },
   fetch: function () {
       // fetching code here
   }
}
```

Seguindo este exemplo, crie dois tipos diferentes de classes usando funções construtoras e métodos de protótipo: um Traveler (Viajante) e uma Wagon (Carroça).

Um Traveler (Viajante) tem algumas propriedades: * um name (nome) (string) que deve ser fornecido como parâmetro para o construtor. * uma quantidade de food (comida) (número) com valor inicial 1. * uma propriedade isHealthy (booleano) que indica se ele está doente com valor inicial true.

Uma Wagon (Carroça) também tem algumas propriedades: * uma capacity (capacidade) (número), que deve ser fornecida como parâmetro para o construtor, determina a quantidade máxima de passageiros que cabe na carroça. * uma lista de passageiros (array) que inicialmente está vazia.

<h1>Operações</h1>

Escreva os seguintes métodos de protótipo:

<h2>Traveler.prototype.hunt()</h2>
Aumenta a comida do viajante em 2.

<h2>Traveler.prototype.eat()</h2>
Consome 1 unidade da comida do viajante. Se o viajante não tiver comida para comer, ele deixa de estar saudável.

<h2>Wagon.prototype.getAvailableSeatCount()</h2>
Retorna o número de assentos vazios, determinado pela capacidade que foi estipulada quando a carroça foi criada comparado com o número de passageiros a bordo no momento.

<h2>Wagon.prototype.join(traveler)</h2>
Adicione o viajante à carroça se tiver espaço. Se a carroça já estiver cheia, não o adicione.

<h2>Wagon.prototype.shouldQuarantine()</h2>
Retorna true se houver pelo menos uma pessoa não saudável na carroça. Retorna false se não houver.

<h2>Wagon.prototype.totalFood()</h2>
Retorna o número total de comida de todos os ocupantes da carroça.

<h1>Teste</h1>
Insira o seguinte código no final do seu programa para verificar se ele está funcionando apropriadamente. (Não modifique este código!)

```
// Criar uma carroça que comporta 2 pessoas
let wagon = new Wagon(2);
// Criar três viajantes
let henrietta = new Traveler('Henrietta');
let juan = new Traveler('Juan');
let maude = new Traveler('Maude');

console.log(`${wagon.getAvailableSeatCount()} should be 2`);

wagon.join(henrietta);
console.log(`${wagon.getAvailableSeatCount()} should be 1`);

wagon.join(juan);
wagon.join(maude); // Não tem espaço para ela!
console.log(`${wagon.getAvailableSeatCount()} should be 0`);

henrietta.hunt(); // pega mais comida
juan.eat();
juan.eat(); // juan agora está com fome (doente)

console.log(`${wagon.shouldQuarantine()} should be true since juan is sick`);
console.log(`${wagon.totalFood()} should be 3`);
```

<h1>Envio</h2>

Faça o push do código para o seu repositório GitLab e implemente-o via GitLab pages. No Canvas, envie a url do seu Gitlab Pages (por exemplo https://username.gitlab.io/oregon-trail/). No GitLab, adicione ka-br-correcoes como membro do seu projeto com a permissão "Reporter".