# statePedidos


### Pesquisa: Qual Design Patterns?

Padrões de Design / Padrões Comportamentais / State


### Veio para resolver qual problema? Propósito

State é um padrão de design comportamental que permite que um objeto altere seu comportamento quando seu estado interno muda. Parece que o objeto mudou de classe.


### Tem algum Problema?

O padrão State está intimamente relacionado ao conceito de uma máquina de estados finitos. A ideia principal é que, a qualquer momento, há um número finito de estados nos quais um programa pode estar. Dentro de qualquer estado único, o programa se comporta de maneira diferente, e o programa pode ser alternado de um estado para outro instantaneamente. No entanto, dependendo de um estado atual, o programa pode ou não alternar para alguns outros estados. Essas regras de comutação, chamadas de transições , também são finitas e predeterminadas.


### Solucao

O padrão State sugere que você crie novas classes para todos os estados possíveis de um objeto e extraia todos os comportamentos específicos de estado para essas classes.

Em vez de implementar todos os comportamentos por conta própria, o objeto original, chamado context , armazena uma referência a um dos objetos de estado que representa seu estado atual e delega todo o trabalho relacionado ao estado a esse objeto.


### Estrutura

1 - O contexto armazena uma referência a um dos objetos de estado concretos e delega a ele todo o trabalho específico do estado. O contexto se comunica com o objeto de estado por meio da interface de estado. O contexto expõe um setter para passar um novo objeto de estado.

2 - A interface State declara os métodos específicos do estado. Esses métodos devem fazer sentido para todos os estados concretos porque você não deseja que alguns de seus estados tenham métodos inúteis que nunca serão chamados.

3 - Os estados concretos fornecem suas próprias implementações para os métodos específicos de estado. Para evitar a duplicação de código semelhante em vários estados, você pode fornecer classes abstratas intermediárias que encapsulam algum comportamento comum. Objetos de estado podem armazenar uma referência inversa ao objeto de contexto. Por meio dessa referência, o estado pode buscar qualquer informação necessária do objeto de contexto, bem como iniciar transições de estado.

4 - Ambos os estados de contexto e concreto podem definir o próximo estado do contexto e realizar a transição de estado real substituindo o objeto de estado vinculado ao contexto.

