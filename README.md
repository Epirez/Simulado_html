

## Sobre este Simulado Dinâmico
Este simulado foi desenvolvido como parte do processo de estudo em **prompts para IA** com uma aplicação prática. A estrutura HTML e JavaScript utilizada permite a apresentação dinâmica de perguntas, controle de tempo e feedback imediato ao usuário.


### Funcionalidades principais:
- **Interface interativa** com perguntas de múltipla escolha.
- **Feedback automático** com explicações para cada resposta.
- **Controle de tempo** com contagem regressiva.
- **Cálculo de desempenho** ao final do simulado (acertos, erros e não respondidas).
- **Estilo visual simples e funcional**, com destaque para respostas corretas e incorretas

!ExemploSimulado_01

## Como adicionar diferentes tipos de perguntas ao simulado

O simulado dinâmico utiliza um array de objetos JavaScript para representar cada pergunta. Cada objeto segue uma estrutura padrão e pode ser facilmente adaptado para incluir novos conteúdos.

### Estrutura básica de uma pergunta

```js
{
  q: "Texto da pergunta",
  options: [
    "a) Alternativa A",
    "b) Alternativa B",
    "c) Alternativa C",
    "d) Alternativa D"
  ],
  answer: 1, // Índice da alternativa correta (começa em 0)
  explanation: "Explicação exibida após a resposta."
}
````

## Como configurar o tempo do simulado

O tempo total do simulado é definido em segundos na variável `totalTime`. Essa configuração controla quanto tempo o usuário terá para responder todas as perguntas antes que o simulado seja encerrado automaticamente.

### Localização no código

```js
// Timer
let totalTime = 40 * 60; // minutos (em segundos) - ajuste como quiser
let timeLeft = totalTime;
let timerInterval = null;
let quizStarted = false;
let quizEnded = false;
````
### Como alterar o tempo
A fórmula usada é:

````js
totalTime = MINUTOS * 60;
````

Por exemplo:
Para 30 minutos, use:
````js
let totalTime = 30 * 60;
````

Para 1 hora, use:
````js
let totalTime = 60 * 60;
````

### Comportamento do timer

O tempo restante é exibido na tela e atualizado a cada segundo.
Quando o tempo chega a zero, o simulado é finalizado automaticamente com a mensagem "Tempo esgotado!".
O tempo gasto também é mostrado no resultado final.




