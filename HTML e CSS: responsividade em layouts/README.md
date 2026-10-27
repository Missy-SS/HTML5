### Unidades de Medida no CSS

**Unidades Fixas e Unidades Relativas**

**Unidades Fixas**: Não se adaptam; pixels e centímetros;

**Unidades Relativas**: Permitem algum tipo de proporcionalidade, tornando-as relativas a algo. Exemplo de unidades relativas: %, em, rem, vh e vw.

**VH**: *View Height* (altura da visualização)

**VW**: *View Width* (largura de visualização)

div {
    width: 33%;
    height: 200px;
    display: inline-block;
    background: dodgerblue;
}


O navegador adiciona espaçamentos mínimos entre os elementos, e esse espaçamento é levado em consideração. Quando somamos os três elementos, eles podem ultrapassar 100%, fazendo com que uma **div** quebre para baixo.

#### Utilizando a unidade EM para tipografia

Geralmente usada como medida de tipografia, de fonte. É sempre relativa ao tamanho de fonte do elemento pai. Como uma div com um parágrafo dentro. A **div mantém o mesmo tamanho**, com width de 33%, height de 200, e display  como inline-block, mas com um font-size de 30.

Para o **parágrafo**, definimos o **font-size** como **1.5 EM**. Siginifica que, se a fonte do elemento pai é 30 pixels, **multiplicando** por 1.5, o font-size resultará em **45 pixels**.

 - *Usamos essa medida quando precisamos escalar o tamanho da fonte dentro de um contexto específico de um elemento.*


div p {
    font-size: 1.5em; /*=30 x 1.5 = 45px*/
}

#### Preferindo a unidade REM para evitar efeito cascata

Se definirmos font-size na div, na section e em outro elemento que contém a section, os tamanhos se acumularão, por isso, preferimos usar o **REM**, pois ele é relativo ao tamanho da fonte do root, ou seja, da raiz do nosso HTML.

Usamos o **REM** para padronizar a tipografia e espaçamentos, pois temos um único ponto de troca de tamanho de fonte.

html {
    *font-size: 16px;*
}
div {
    *width: 12.5rem;* /*12.5 * 16 = 200*/
}
div p {
    *font-size: 1.5rem;* /*16 * 1.5 = 24px*/
}

Declaramos que o HTML terá font-size de 16 pixels. Assim, ao declarar espaçamentos ou larguras em parágrafos, podemos usar a medida REM, que será um múltiplo desses 16 pixels. 
A div terá width de 12.5 REM, que é 12.5 vezes 16, resultando em 200 picels. Para o parágrafo, em vez de fixar em 24 picels, definimos 1.5 REM.

#### Unidades VW e VH para layouts responsivos

Caso mudemos de dispositivo, alteramos apenas o font-size do HTML. Se quisermos fontes maiores ajustamos o font-se do HTML para 18, e todas as outras medidas relativas escalarão automaticamente, sem precisar alterar cada elemento individualmente. 

**VW** é relativo ao viewport, ou seja, ao espaço de tela visível do dispositivo. Usamos essas unidades quando precisamos de um banner em tela cheia, em slides ou em layouts hero, onde todo o conteúdo deve estar visível antes de rolar a página.

* Um ponto de atenção é que pode haver rolagem extra em dispositivos móveis, especialmente ao abrir o teclado ou com a barra de navegação, mas isso é fácil de contornar.

div {
    width: 50vw;
    height: 100vh;
    display: inline-block;
}







