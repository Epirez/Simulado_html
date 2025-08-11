

## Sobre este Simulado Dinâmico
Este simulado foi desenvolvido como parte do processo de estudo em **prompts para IA** com uma aplicação prática. A estrutura HTML e JavaScript utilizada permite a apresentação dinâmica de perguntas, controle de tempo e feedback imediato ao usuário.

 Estratégias conhecidas de engenharia de prompts utilizadas: 

| **Estratégia**         | **Descrição**                                                                     | **Como Aplicar na Geração do Quiz**                                                                                                    | **Exemplo Prático de Prompt para o Quiz** |  
|------------------------|-----------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------|  
| Chain of Thought       | Orienta o modelo a pensar passo a passo, detalhando o raciocínio.                 | Solicite que o modelo explique cada etapa do processo de criação do quiz, do planejamento ao código final.                            | "Descreva passo a passo como gerar um quiz interativo, incluindo estrutura de perguntas, lógica de respostas, timer e feedback visual." |  
| Role Play              | O modelo assume um papel específico.                                              | Peça para o modelo agir como um desenvolvedor front-end ou especialista em educação digital.                                          | "Finja que você é um desenvolvedor web especializado em quizzes educacionais. Como você criaria um quiz de segurança digital interativo?" |  
| Few-shot Prompting     | Exemplos são fornecidos para ilustrar como responder.                             | Apresente exemplos de perguntas formatadas antes de pedir ao modelo para criar novas seguindo o mesmo padrão.                          | "Aqui estão dois exemplos de perguntas para o quiz: {…}. Crie mais três seguindo esse formato." |  
| Zero-shot Prompting    | O modelo recebe apenas a tarefa, sem exemplos prévios.                            | Peça para o modelo criar perguntas ou o código do quiz apenas com a instrução básica, sem exemplos.                                   | "Crie um quiz de cinco perguntas sobre segurança digital com alternativas e feedback imediato." |  
| Instruction Prompting  | O modelo recebe instruções explícitas sobre como responder ou formatar.            | Dê instruções claras sobre estrutura do array de perguntas, funcionalidades e estilo desejado.                                        | "Gere um array JavaScript de perguntas para um quiz, cada uma com quatro alternativas, identificando a correta e incluindo explicação." |  
| Self-Consistency       | O modelo gera múltiplos raciocínios e escolhe a resposta mais comum/consistente.  | Peça para o modelo sugerir três abordagens de implementação do quiz e escolher a mais eficiente ou didática.                          | "Proponha três formas diferentes de implementar um quiz interativo em HTML/JS e selecione a mais didática para iniciantes." |  


### Funcionalidades principais:
- **Interface interativa** com perguntas de múltipla escolha.
- **Feedback automático** com explicações para cada resposta.
- **Controle de tempo** com contagem regressiva.
- **Cálculo de desempenho** ao final do simulado (acertos, erros e não respondidas).
- **Estilo visual simples e funcional**, com destaque para respostas corretas e incorretas

<p align="left">  
  <img src="Print01.png" alt="Exemplo Resultado Final" width="900">  
</p>  

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

<p align="left">  
  <img src="Print02.png" alt="Exemplo Simulado" width="300">  
</p>  



