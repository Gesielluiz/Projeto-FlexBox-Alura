Sabemos que a propriedade justify-content: space-between faz com que o espaço que sobrou no nosso elemento pai seja distribuído entre os filhos, porém é claro que esse não é o único valor da propriedade justify-content. Por exemplo, de que outras formas podemos distribuir esse espaço?

Qual o valor da propriedade justify-content para essas distribuições de espaço?

Opinião do instrutor

Podemos distribuir os elementos dentro do pai de diversas formas, podemos por exemplo:

Colocar todo espaço à esquerda, jogando o conteúdo para direita com justify-content: flex-end.

Colocar todo espaço à direita, jogando o conteúdo para esquerda com justify-content: flex-start (que é o padrão).

Colocar todo espaço à esquerda e à direita, jogando o conteúdo para o meio com justify-content: center.

Colocar todo espaço entre os elementos como vimos antes usando justify-content: space-between.

E uma possibilidade bem interessante também é colocar o espaço em volta dos elementos. Podemos usar o justify-content: space-around para isso.

*ATIVIDADE

Normalmente quando colocamos display: flex em algum elemento, os seus filhos ficam um do lado do outro. Porém existem casos em que queremos que os filhos fiquem um em baixo do outro, como podemos fazer isso?

R: Podemos colocar flex-direction: column no elemento pai

Podemos colocar flex-direction: column no pai, dessa forma ele muda o fluxo o qual o flexbox renderiza os elementos. Assim eles ficam um em baixo do outro.

* Terminando course grid
Dando um reload vemos que todos os objetos foram arrumados inclusive o primeiro:
Isso acontece pois o n do primeiro elemento equivale a 0, então, 4x0 + 1 = 1 e por isso ele é ajustado! No segundo item o n =1, assim, 4x1 + 1 = 5, no terceiro ícone n = 2, 4x2 + 1 = 9 e assim por diante.

Utilizando o nth, que é relativamente fácil de usar, solucionamos a questão da distribuição! O que fizemos foi um gride de caixas organizadamente posicionadas. O flex é capaz de fazer gride, ainda assim, não existe uma maneira fácil de espaçar os elementos. Foi preciso utilizar não apenas o nth mas também fazer contas com a largura e a margem para resolver o problema!

 * Começando o grid
 Agora precisamos começar um grid, para isso usaremos flex. Como ficaria o CSS, utilizando flexbox, para organizar ( pensando apenas em posicionamento ) o seguinte HTML?

<div class="grid">
  <div class="box">Ruby on Rails</div>
  <div class="box">Java</div>
  <div class="box">HTML</div>
  <div class="box">Python</div>
  <div class="box">Wordpress</div>
  <div class="box">Bootstrap</div>
  <div class="box">Java Web</div>
  <div class="box">MySQL</div>
</div>COPIAR CÓDIGO
Quando for realizar esse teste na sua máquina, lembre-se de colocar altura, largura e alguma cor para as div`s.

.box {
  height: 50px;
  width: 50px;
  background-color: green;
}COPIAR CÓDIGO
VER OPINIÃO DO INSTRUTOR
Opinião do instrutor

Para organizar esse código HTML e fazermos um grid ( pensando apenas em posicionamento ) podemos escrever o seguinte código CSS:

.grid {
  display: flex;
  flex-wrap: wrap;
}
Dessa forma todos os elementos filhos ficariam um do lado do outro e quando chegassem ao limite da página quebrariam para a linha de baixo, formando assim o grid.

Repare que não consertamos margins ainda, os elementos provavelmente ficariam colados.

* Como espaçar corretamente os elementos de um grid
Para espaçar corretamente os elementos de um grid temos que realmente fazer contas com a boa e velha margin e width.

Se temos 3 elementos por linha podemos fazer algo do tipo:

HTML:

<div class="grid">

  <!-- primeira linha -->
  <div class="course"></div>
  <div class="course"></div>
  <div class="course"></div>

  <!-- segunda linha -->
  <div class="course"></div>
  <div class="course"></div>
  <div class="course"></div>

  <!-- terceira linha -->
  <div class="course"></div>
  <div class="course"></div>
  <div class="course"></div>

  <!-- quarta linha -->
  <div class="course"></div>
  <div class="course"></div>

</div>COPIAR CÓDIGO
CSS:

.grid {
  display: flex;
  flex-wrap: wrap;
}

.course {
  width: 31.3%;
  margin: 1%;
}COPIAR CÓDIGO
VER OPINIÃO DO INSTRUTOR
Opinião do instrutor

Nesse caso teriamos 3 .course por linha, cada um com width: 31.3% e margin: 1%.

De width isso totaliza: 31.3 * 3 = 93.9%.

De margin isso totaliza: 6% (1% à esquerda e 1% à direita de cada elemento).

No total temos: 93.9% + 6% = 99.9% que dá pra arredondar para 100%.

* De desktop para mobile
Quando estamos desenvolvendo um site temos que aproveitar bem o espaço da tela, para desktop podemos encaixar elementos um do lado do outro para justamente aproveitar essa largura a mais. Quando temos que adaptar nossos sites para mobile, qual o fluxo que normalmente os elementos seguem para aproveitar melhor o espaço?

Como fazer com que esse fluxo seja seguido utilizando o flexbox?
 R: Para aproveitar o espaço precisamos colocar os elementos um em baixo do outro.

Para fazer isso devemos colocar flex-direction: column.

* Propriedades do flex container e dos flex items
- Quais são as propriedades que funcionam SOMENTE nos flex container e quais são as que funcionam nos flex items?

Existem diversos sites para consultar isso, como esse. 
R: flex container:

justify-content, align-items, flex-direction, flex-wrap

flex items:

order, flex-grow, flex-shrink

A propriedade display: flex pode ser usada nos dois. Se for usada em um flex item esse elemento será tanto um flex item quanto um flex container.


Alternativa correta.

O melhor a se fazer aqui é ter em mente que o ideal é sempre que necessário consultar a documentação através desse site.

Lá podemos ver claramente quais propriedades são aplicadas ao container e aos flex items, não há necessidade de ficar decorando, isso virá naturalmente com a prática.

Seguindo a documentação temos:

container:

display: flex
flex-direction
justify-content
flex-wrap
flex-flow
align-items
align-content
flex item:

order
flex-grow
flex-shrink
flex-basis
flex
align-self
Não foi desta vez! Tente novamente.

* Ordenando o nosso menu

O nosso menu no header do site tem um link para baixar o app do Alurinha. Quando o usuário abre o nosso site com um dispositivo móvel a última opção do menu é o app. Como podemos fazer para melhorar a experiência do usuário nesse caso?

R: 
O melhor seria mudar a ordem do menu, colocando o link de baixar o app em primeiro lugar.

Podemos fazer isso com flexbox utilizando a propriedade order.


É exatamente isso, o código ficaria assim.

.cabecalhoPrincipal-nav-link-app {
  order: -1;
}

Note que os filhos são as divs e neles já estão acrescentados os flex-Itens.

Vamos abrir o arquivo maisFlex.css para manusear estes itens. Então, adicionamos o .flexItem e nele o flex-grow: 1. O flex-grow serve para aumentar o tamanho dos objetos envolvidos e recebe sempre um valor numérico que varia de 1 a 1000:

.flexItem {
    flex-grow: 1;
}COPIAR CÓDIGO
Ao acrescentar isso os objetos ficam da seguinte maneira:



Observe que o espaço está igualmente distribuído entre os elementos! Mas, para compreendermos melhor o que acontece entre os elementos vamos deixá-los todos com o mesmo tamanho! Ou seja, 50 px:

.flexContainer:last-child { margin-top: 2em; }
body { margin: 0; padding: 0; }
div {height: 50 px; width: 50 px; }
div: nth-child(1) { backgroun-color: red; width: 50 px; height: 50 px;}

/*... */COPIAR CÓDIGO
Assim, os objetos terão as mesmas dimensões! Inspecionando os elementos temos a confirmação:



Agora, vamos tentar compreender quais são as contas que o flex-grow realiza, para isso é preciso retirar do código o flex-grow e dar um reload na página:



Note que existe um grande espaço à direita! O navegador pega o espaço total e divide ele igualmente entre as caixas coloridas, assim, elas ficam todas com o mesmo tamanho e isso ocorre pois todos os itens recebem uma fatia igual dessa divisão!

Vamos complicar um pouco, acrescentamos na classe .primeiro o flex-grow:2. Assim, temos o seguinte:

.flexItem {
    flex-grow: 1;
}

.primeiro {
    flex-grow: 2;
}COPIAR CÓDIGO
O resultado disso é:



Nós temos o primeiro item aumentado duas vezes mais que o segundo! Isso acontece pois o navegador entende que o primeiro elemento tem flex-grow: 2 e os demais flex-grow: 1. Assim, do espaço total disponível o primeiro objeto pega dois pedaços, enquanto ao restante cabe apenas uma parte! Portanto, a primeira caixa, em vermelho, possui uma div que pega dois pedaços do inteiro e por isso ela é maior do que o restante dos objetos.

Vamos trocar as proporções, colocaremos na primeira div o 3 e no restante 2:

.flexItem {
    flex-grow: 2;
}

.primeiro {
    flex-grow: 3;
}COPIAR CÓDIGO
E teremos o seguinte:



Isso ocorre, pois o navegador faz uma conta pegando o total do espaço e dividindo entre os flex-grow que existem. O primeiro elemento possui 3 flex-grow, o segundo, terceiro e quarto possuem apenas dois pedaços e isso soma nove pedaços (3 + 2 + 2 + 2 = 9).

Portanto, o flex-grow serve para aumentar objetos e seu padrão é flex-grow de valor 0.

Agora, vamos aprender mais sobre o flex-shrink que serve para diminuir os objetos. Para sua análise deixamos a tela do tamanho do celular, com a medida de 200 px. Retornando ao arquivo maisFlex.css podemos verificar que a largura dos itens, 50 px para cada, somam 200 px de largura.



Agora, se diminuirmos o tamanho da tela para 100 px os itens terão seu tamanho de largura diminuido para a metade, 25 px, e os quatro elementos somados passam a totalizar 100 px.

Se colocarmos no .flexItem o flex-shrink: 1 nada acontecerá, pois, por padrão o flex-shrink dos elementos já possui o valor 1. Podemos testar com o .primeiro acrescentado da propriedade flex-shrink: 2 e teremos:

.primeiro {
    /*flex-grow: 3;*/
    flex-shrink: 2;
}COPIAR CÓDIGO
Dessa forma, o primeiro item se tornará duas vezes menor:



Assim, através do Inspect podemos verificar que o primeiro elemento possui 10 px e os outros três possuem 30 px cada e que a tela na qual estamos trabalhando possui o valor total de 100 px. Vamos entender como os objetos chegam a esse tamanho! O valor do primeiro objeto é flex-shrink: 2 e do segundo, terceiro e quarto são flex-shrink: 1. Então, a soma desses elementos é 2 + 1 + 1 + 1 = 5. Como o total da tela é 100 px temos que dividir pela soma dos itens para descobrir o tamanho que cabe a cada objeto, 100 : 5 = 20 px. Portanto, cada objeto corresponde a um espaço de 20 px. O primeiro elemento possui flex-shrink com valor 2, então, os 20 px serão diminuídos duas vezes, 20 px x 2 = 40 px. Como cada elemento originalmente possuía o tamanho de 50 px, assim, devemos pegar o valor do objeto e diminuir o valor que ele é diminuído e teremos o valor que ele fica: 50 px - 40 px = 10 px . Por isso, o primeiro terá o tamanho de 10 px e os demais objetos terão um tamanho final que é igual ao valor inicial diminuído pelas vezes que os outros objetos foram diminuídos, ou seja, 50 px - 20 px = 30 px. Assim, todos os demais elementos possuem cada um o tamanho de 30 px.

E se colocarmos que o .flexItem possui um flex-shrink:0? O resultado é que os itens não vão aceitar diminuição! Todas as caixas ficam com 50 px cada uma, mesmo diminuindo a tela para 80 px vemos que os objetos acabam escapando das dimensões e ficam com as medidas iguais. O flex-shrink:0 mantém os elementos sempre com as mesmas medidas:



O último ponto é, se quisermos definir tanto o flex-shrink quanto o flex-grow juntos podemos utilizar o atalho do flex, por padrão o primeiro valor equivale ao grow e o segundo ao shrink:

flex: 1 1;COPIAR CÓDIGO
Uma última propriedade existente é o flex-basis que recebe o número absoluto da largura. Vamos definir o flex-grow como 0 e flex-basis como 200 px.

.flexItem {
    flex: 0 1;
    flex-basis: 200px;
}COPIAR CÓDIGO
Temos o seguinte:



Se redefinirmos o flex-basis para o valor de 25% teremos as caixas ocupando cada uma um quarto da tela:



Ainda, podemos inserir o flex-basis como terceiro argumento do flex; Então, teremos:

.flexItem {
    flex: 0 1 25%;
}COPIAR CÓDIGO
Essa aula foi dedicada a aprofundar e tirar dúvidas sobre o funcionamento do flex-grow e flex-shrink.

* Fazendo os elementos preencher o espaço vazio
Digamos que temos dois flex items e que precisamos que um desses elementos ocupe todo o espaço que está sobrando do flex container. Como podemos fazer isso?
 - Podemos usar a propriedade flex-grow. O código ficaria assim:

.flex-item {
  flex-grow: 1;
}

Para falar para um elemento / flex item crescer e ocupar todo o espaço que está sobrando dentro do flex container devemos usar a propriedade flex-grow.

Para fazê-lo crescer podemos escrever o seguinte código CSS:

.flex-item {
  flex-grow: 1;
}COPIAR CÓDIGO
Podemos colocar o valor 1 para que esse elemento ocupe todo o espaço. Mais a frente veremos como funciona direito esse valor.

* Contas no flex
A propriedade flex-grow vista no exercício anterior ajuda muito caso queiramos que um elemento ocupe toda a largura restante do flex container.

Por exemplo, se temos:

Elemento 1: 200 px.

Elemento 2: 200 px.

Espaço vazio que sobrou do flex container: 600 px.

Total: 1000 px.

Se colocamos flex-grow: 1 no primeiro elemento, ele passa a ter 800 px de largura, ou seja:

Espaço vazio + Elemento 1: 800 px.

E o segundo elemento continua tendo 200 px de largura.

Agora, se colocarmos flex-grow: 1 nos dois elementos, o que aconteceria? Qual tamanho ficaria o elemento 1? E o elemento 2?

VER OPINIÃO DO INSTRUTOR
Opinião do instrutor

O que aconteceria é o seguinte:

Considere o espaço vazio inicial: 600 px.

Como os dois elementos tem flex-grow: 1, a soma de flex-grow que temos vai dar 1 + 1 = 2.

O navegador pega esse espaço vazio e divide pelo número de flex-grow que temos: 600 px : 2 = 300 px.

Agora ele distribui esse espaço para cada um dos elementos que colocamos flex-grow.

Elemento 1: 300 px + 200 px = 500 px.

Elemento 2: 300 px + 200 px = 500 px.

* Mantendo o vídeo do mesmo tamanho

Imagine que no nosso site temos um video do Youtube, imagine que mesmo se o usuário diminuir a tela, o nosso video não deva diminuir de tamanho. Como podemos fazer isso?

Imagine que nosso vídeo é um flex item e que o código HTML é o que segue:

Podemos simplesmente colocar a propriedade flex-shrink no elemento, por exemplo:

.videoSobre-video {
  flex-shrink: 0
}

Perfeito! Simplesmente colocamos flex-shrink: 0 no nosso elemento que não queremos que diminua.

* Simplesmente colocamos flex-shrink: 0 no nosso elemento que não queremos que diminua, no caso o código ficaria assim:
.videoSobre-video {
  flex-shrink: 0;
}

- Diminuindo proporcionalmenteos elemsntos

Considere o código HTML abaixo.

<main class="flexContainer">        
  <div class="flexItem firstRow"></div>
  <div class="flexItem firstRow"></div>
  <div class="flexItem firstRow"></div>
  <div class="flexItem firstRow"></div>
</main>COPIAR CÓDIGO
Considere agora que estejamos em um contexto flex. E que cada flexItem tem 200 px de width.

CSS

.flexContainer {
  display: flex;
}
.flexItem {
  width: 200px;
}COPIAR CÓDIGO
1) Quando a largura da tela chega a 800 px, os elementos mantém 200 px de largura cada um preenchendo todo o espaço da tela, porém, o que acontece com a largura dos flexItem quando diminuímos a tela para por exemplo 600 px.

2) O que acontece com a largura deles também quando aplicamos o seguinte CSS no nosso código?

.flexItem:first-child {
  flex-shrink: 2;
}COPIAR CÓDIGO
Sugestão: Crie um arquivo HTML e CSS, escreva esse código e faça os testes, utilize também valores diferentes!

VER OPINIÃO DO INSTRUTOR
Opinião do instrutor

1) Quando diminuimos a tela para 600 px os flex-item diminuem seu tamanho igualmente entre si, ou seja, como a tela diminuiu 200 px e temos 4 flex items, cada um diminuiu 50 px. Sendo assim cada flex-item ficou com 150 px no fim.

2) Quando colocamos flex-shrink: 2 no primeiro, ele diminui de forma diferente do que os outros elementos. As contas que ocorrem são semelhantes as que ocorrem no flex-grow.

Primeiro de tudo o navegador pega o total de flex-shrink que nossos flex items tem, como temos por padrão flex-shrink: 1 nos flex items, a conta fica assim:

2 + 1 + 1 + 1 = 5. Isso pois o primeiro colocamos flex-shrink:2.

Como diminuímos 200 px do tamanho total, o navegador pega esse valor e divide pelo total de flex-shrink. Fica: 200 px : 5 = 40 px.

Dessa forma o navegador tira 2 partes do primeiro elemento 200px - 80px = 120px e tira 1 parte dos demais, ou seja: 200 px - 40 px = 160 px.

* A propriedade flex-basis serve para que?

A propriedade flex-basis serve para definir uma altura para o elemento caso o flex container esteja com flex-direction: column.

flex-basis: 500px;

Alternativa correta.

* Condensando flex-grow, shrink e basis
Qual é a propriedade que usamos para condensar as propriedades flex-grow, flex-shrink e flex-basis?


A propriedade é a propriedade flex.

  flex: 1 1 300px;
A ordem dos valores é:

flex-grow, flex-shrink, flex-basis.

* Invertendo a ordem de todos os elementos
O flex permite que nós possamos alterar muitas coisas nos elementos, seja distribuição dos espaços, tamanhos, direção de renderização e alinhamento. Além de tudo isso também podemos mudar o sentido nos quais os nossos elementos são renderizados. Faça o teste. Abra nossa página principal do site index.html, lembra do grid que fizemos? O CSS que usamos deve estar assim:

.conteudoPrincipal-cursos {
  display: flex;
  flex-wrap: wrap;
}COPIAR CÓDIGO
Mude agora o flex-wrap. Coloque flex-wrap: wrap-reverse.

.conteudoPrincipal-cursos {
  display: flex;
  flex-wrap: wrap-reverse;
}COPIAR CÓDIGO
Tudo que estava em baixo foi para cima! Ele inverteu a ordem das linhas!s

Tente agora:

.conteudoPrincipal-cursos {
  display: flex;
  flex-wrap: wrap;
  flex-direction: row-reverse;
}COPIAR CÓDIGO
Repare que agora ele inverteu a ordem dos elementos nas linhas.

Podemos usar também flex-direction: column-reverse nos casos em que usamos flex-direction: column. Ele inverterá a ordem!



