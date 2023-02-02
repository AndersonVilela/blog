---
Author: "Anderson Vilela"
Updated: "Jan 23, 2023"
Title: "Você sabe para que serve o UseEffect?"
tag: "react"
---



# O useEffect
È um hook do React que permite a execução de efeitos colaterais no seu código, como buscar dados de uma API, mudar a DOM ou configurar uma subscription. Ele é chamado passando duas funções como parâmetros: a primeira é a função que será executada, e a segunda é a dependência, que é um array de variáveis que, quando alteradas, farão com que a função seja chamada novamente.


## Exemplo
Para entender melhor o uso do useEffect, vamos dar um exemplo de como ele pode ser utilizado para mudar o título de uma página baseado no estado de uma variável. Veja o código abaixo:

```js{6-8} 
import { useState, useEffect } from 'react';

function Example() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    document.title = `Count: ${count}`;
  }, [count]);

  return (
    <>
      <h1>{count}</h1>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </>
  );
}
```
## Explicação exemplo 1
Nesse exemplo, estamos usando o useState para criar um estado chamado count, que começa com o valor 0. Depois, estamos usando o useEffect para mudar o título da página toda vez que o count for alterado. Dentro do useEffect, estamos passando uma função que muda o título da página para "Count: <valor de count />", e como dependência estamos passando o count. Isso significa que toda vez que o count mudar, a função dentro do useEffect será chamada novamente, atualizando o título da página.

É importante notar que, se não houvesse a dependência, a função dentro do useEffect só seria chamada uma vez, quando o componente é renderizado pela primeira vez. Dessa forma, sempre que quisermos que uma função seja chamada sempre que uma determinada variável for alterada, devemos passá-la como dependência do useEffect.

<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-4349091134125615"
     crossorigin="anonymous"></script>

<ins class="adsbygoogle"
     style="display:block; text-align:center;"
     data-ad-layout="in-article"
     data-ad-format="fluid"
     data-ad-client="ca-pub-4349091134125615"
     data-ad-slot="4031581483"
     >
     </ins>

<script>
     (adsbygoogle = window.adsbygoogle || []).push({});
</script>
## Exemplo 

```js{6-13}
import { useState, useEffect } from 'react';

function Example() {
  const [data, setData] = useState(null);

  useEffect(() => {
    async function fetchData() {
      const response = await fetch('https://minha-api.com/dados');
      const json = await response.json();
      setData(json);
    }
    fetchData();
  }, []);

  return (
    <>
      {data ? (
        <>
          <h1>Dados da API</h1>
          <ul>
            {data.map((item) => (
              <li key={item.id}>{item.name}</li>
            ))}
          </ul>
        </>
      ) : (
        <p>Carregando dados...</p>
      )}
    </>
  );
}

```

## Explicação exemplo 2 

Neste exemplo, estamos usando o useState para criar um estado chamado data, que começa como null. Em seguida, estamos usando o useEffect para buscar dados de uma API quando o componente é montado. Dentro do useEffect, estamos chamando uma função assíncrona fetchData que usa o fetch para buscar os dados da API e, em seguida, usa o setData para atualizar o estado com os dados retornados. Como dependência, estamos passando um array vazio, o que significa que essa função só será chamada uma vez, quando o componente é montado.

Dessa forma, quando o componente é renderizado pela primeira vez, a função dentro do useEffect é chamada, buscando os dados da API e atualizando o estado data, e a cada renderização subsequente, se o estado data tiver valor, ele é renderizado na tela, caso contrario é exibido uma mensagem de carregando dados.


Em resumo, o useEffect é um hook muito poderoso do React que permite a execução de efeitos colaterais no seu código, como buscar dados de uma API, mudar a DOM ou configurar uma subscription. Ele é chamado passando duas funções como parâmetros: a primeira é a função que será executada, e a segunda é a dependência, que é um array de variáveis que, quando alteradas, farão com que a função seja chamada.


## Sites que recomendo
vou deixar alguns sites que recomendo dar uma olhada para não só entender mas exercitar e dominar o uso do useEffect: 

A documentação oficial do React: https://pt-br.reactjs.org/docs/hooks-effect.html
A documentação da API de efeitos do React: https://pt-br.reactjs.org/docs/react-api.html#reconcile-effects
O site "Overreacted" do desenvolvedor do React, Dan Abramov: https://overreacted.io/
O site "React Training": https://reacttraining.com/
O site "Hooks" do React: https://react-hooks.netlify.app/

Além disso, existem muitos tutoriais e cursos online disponíveis que podem ajudá-lo a entender melhor o uso do useEffect e outros hooks do React. É importante praticar e experimentar com o uso do useEffect, para que você possa entender melhor como ele funciona e como pode ser útil em seus projetos.
