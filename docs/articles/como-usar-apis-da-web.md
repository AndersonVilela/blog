---
Author: "Anderson Vilela"
Updated: "Feb 08, 2023"
Title: "Como usar Apis da web"
tag: "javascript"
---
# Oque é uma api
APIs são mecanismos que permitem que dois componentes de software se comuniquem usando um conjunto de definições e protocolos. Por exemplo, o sistema de software do instituto meteorológico contém dados meteorológicos diários. A aplicação para a previsão do tempo em seu telefone “fala” com esse sistema por meio de APIs e mostra atualizações meteorológicas diárias no telefone.

## Usar API's para conectar sistemas e aplicativos 
È uma forma rápida e segura de criar soluções tecnológicas. API significa “Application Programming Interface”, que é uma interface de programação de aplicações que possibilita a comunicação de dois sistemas diferentes. As API's requerem um conjunto de padrões, rotinas e instruções de programação para permitir que os softwares ou aplicativos se conectem.

## Em termos praticos, 
API's permitem que dois computadores entendam as instruções um do outro e gerem novas instruções a serem realizadas. Além disso, API's também permitem que softwares diferentes com linguagens diferentes se conectem para realizarem uma nova tarefa.

## Quando se fala em API's 
Também se fala em API's de integração. Estas API's permitem integrar mais rápido e seguro sistemas que usam linguagens diferentes, a fim de juntos realizarem uma nova tarefa.

## ma API tem a função de.. 
evitar que um desenvolvedor precise criar e instalar diferentes recursos para que sistemas ou aplicativos diferentes possam “conversar” entre si. Por meio de uma API é possível reduzir o tempo de integração e liberar o uso da solução muito mais rápido, além disso, uma API também possibilita a otimização de processos, uma vez que permite gerar gatilhos para que uma ação se inicie tão logo outra seja finalizada.

## Existem diferentes tipos de API's 
Alguns com fins financeiros, outros de ERP, CRM, etc. Alguns exemplos de API's públicas são Google Maps, Twitter e Facebook. Já as API's privadas são aquelas que só podem ser acessadas e utilizadas pelas empresas para a qual foi desenvolvida.

API's podem ser usadas em diferentes situações para aprimorar sistemas já existentes e otimizar tarefas. O resultado deste uso é o aumento da produtividade e a entrega de resultados melhores e mais rápidos.


## Exemplo de código
```js
function listPokemons() {
  fetch('https://pokeapi.co/api/v2/pokemon?limit=20')
  .then((rest) => rest.json())
  .then((data) => console.log(data.results))
}
```
## Explicação  
No código acima, é um exemplo real de busca de dados de uma api, neste exemplo estou buscando 20 pokemons e listando os no console.log, fiquem avontade para testar, e quem sabe criar um site mostrando cards de pokemons na tela.
