---
Author: "Anderson Vilela"
Updated: "Feb 09, 2023"
Title: "Criando um efeito de escrita com html css e javascript"
tag: "css"
---


# Criando um efeito no texto
## html
para começar vamos criar um h1 que vai acontecer o efeito, após isso criamos uma div e colocamos a label e o input para determinar a velociade do efeito.

```html
 <body>
    <h1 id="text">Starting...</h1>
    <div>
      <label for="speed">Speed:</label>
      <input 
      type="number" 
      name="speed" 
      value="1"
      id="speed"
      min="1"
      max="10"
      step="1"
      >
    </div>
    <script type="module" src="/main.js"></script>
  </body>
```
- type: determina  tipo do input então definindo number o input só vai aceitar números.
- name: o nome do input.
- value: valor inicial desse input.
- id: nome de referência podendo ser usado tanto no css como no javascript.
- min: valor minimo a ser permitido.
- max: valor máximo a ser permitido.
- step: quantidade de passos por vez.

após isso temos o link de referência ao local do nosso javascript.
## css
Agora Vamos partir para o css não vou explicar o css para explicar melhor o javascript.

```css
@import url('https://fonts.googleapis.com/css2?family=Roboto:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

body {
  background-color: darksalmon;
  font-family: 'Roboto', sans-serif;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
  overflow: hidden;
  margin: 0;
}

div {
  position: absolute;
  bottom: 20px;
  background: rgba(0, 0, 0, 0.1);
  padding: 10px 20px;
  font-size: 18px;
}

input {
  width: 50px;
  padding: 5px;
  font-size: 18px;
  background-color: darksalmon;
  border: none;
  text-align: center;
  color: black;
}

input:focus {
  outline: none;
}

```
## javascript

```js
// importando meu css 
import "./style.css"

//pegando o elemento html através do id' 
const textElement = document.getElementById('text')
// o mesmo acontece com esse elemento
const speedElement = document.getElementById('speed')
// criando uma variavel string contendo o texto que quero fazer  efeito
const text = 'Hello World'
// variavel responsavel por cada letra que aparece
let id_x = 1
// variavel que determina a velocidade do efeito
let speed = 300 / speedElement.value

// execução da função write
write()

// função responsavel pelo efeito
function write() {
  // slice corta o texto pela quantidade de existente em id_x 
  textElement.innerHTML = text.slice(0 , id_x)
  // soma 1 + 1 para que outra letra apareça
  id_x++

  // verifica se o id_x é maior que a quantidade de letras existentes em nosso texto
  // caso isso seja verdade o valor de id_x vai resetar a ser 1 dando looping ao nosso efeito
  if(id_x > text.length) {
    id_x = 1
  }

// executa varias vezes a função write de acordo com o tempo especificado que no caso
// é o valor de speed
  setTimeout(write, speed)
}
// cria um evento no input para que o valor de speed seja alterado assim que o usuario
  // acrescente o diminua o input tipo number contigo no html
speedElement.addEventListener('input', (e) => speed = 300 / e.target.value)

```



