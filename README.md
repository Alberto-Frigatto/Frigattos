# Frigatto's Library

Frigatto's Library é uma biblioteca Front-End que te ajuda a escrever seu estilo em ***SASS***

<br>

## Créditos

**Autor:** Alberto Frigatto de Andrade Ferreira

**Versão:** 1.2

**Data:** 19/10/2022

**Email:** albertofrigatto.comercial@gmail.com

**Linkedin:** [Clique aqui](https://www.linkedin.com/in/alberto-frigatto-a72022251)

<br>

## Tópicos

- [Instalação](#instalacao)
- [Arquivos](#arquivos)
	- [/style.sass](#style) - estilo geral
	- [/modules/_colors.sass](#colors) - módulo de cores
	- [/modules/_fonts.sass](#fonts) - módulo de fontes
	- [/modules/_index.sass](#index) - hub dos módulos
	- [/modules/_position.sass](#position) - módulo de funções de posições
	- [/modules/_pre-configs.sass](#pre-configs) - módulo de configurações iniciais
	- [/modules/_radius.sass](#radius) - módulo de arradondamento de borda
	- [/modules/_scrollbar.sass](#scrollbar) - módulo da barra de rolagem
	- [/modules/_utilities.sass](#utilities) - módulo com @mixin utilitários

<br>

## Instalação<span id="instalacao"></span>

Inclua essa pasta dentro de `css/`.

Instale as extensões em seu Visual Studio Code:
- Live Sass Compiler - [Instalar](https://marketplace.visualstudio.com/items?itemName=glenn2223.live-sass)
- Sass - [Instalar](https://marketplace.visualstudio.com/items?itemName=syler.sass-indented)

Adicione essa configuração ao `settings.json` de seu Visual Studio Code depois de ter instalado as extensões com base em sua preferência de compilação:

- CSS comprimido (.min.css)

 ```json
 "liveSassCompile.settings.formats":[
    {
       "format": "compressed",
       "extensionName": ".min.css",
       "savePath": "~/.."
    }
 ],
 "liveSassCompile.settings.autoprefix": [
    "> 1%",
    "last 2 versions"
 ]
 ```

- CSS expandido (.css)

```json
"liveSassCompile.settings.formats":[
  {
     "format": "expanded",
     "extensionName": ".css",
     "savePath": "~/.."
  }
],
"liveSassCompile.settings.autoprefix": [
  "> 1%",
  "last 2 versions"
]
```

<br>

## Arquivos<span id="arquivos"></span>

- [/style.sass](#style) - estilo geral
- [/modules/_colors.sass](#colors) - módulo de cores
- [/modules/_fonts.sass](#fonts) - módulo de fontes
- [/modules/_index.sass](#index) - hub dos módulos
- [/modules/_position.sass](#position) - módulo de funções de posições
- [/modules/_pre-configs.sass](#pre-configs) - módulo de configurações iniciais
- [/modules/_radius.sass](#radius) - módulo de arradondamento de borda
- [/modules/_scrollbar.sass](#scrollbar) - módulo da barra de rolagem
- [/modules/_utilities.sass](#utilities) - módulo com @mixin utilitários

<br>

### Configuração

---

Ao incluir a biblioteca em seu projeto, você poderá configurá-la para atender as suas necessidades por meio de funções de configuração em [_index.sass](#index):

<br>

### 1. Cores<span id="custom-colors"></span>

Caso queira criar classes de cores personalizadas basta chamar a função:

```sass
+colors.custom-colors($colors...)
```

`$colors...` é o parâmetro à ser preenchido para incluir as cores customizadas

Deve ser preenchido com 2 valores:

1. Nome para as classes. Exemplo: `myPink`
2. Valor da cor desejada. Exemplo: `#f1505f`

#### Exemplo

- Adicionando uma cor

```sass
+colors.custom-colors(myPink #f5015f)
```

- Adicionando mais de uma cor

```sass
+colors.custom-colors(blue #0020ff, my-green rgb(0, 255, 0))
```

<br>

> :warning: Se o valor da cor tiver menos do que 30% ou mais de 70% de brilho, a função gerará um erro

<br>

A função criará classes utilitárias para `color` e `background` e com efeito de `:hover` para a cor fornecida e para tonalidades dela (mais claras e mais escuras).

Tonalidades:

- --1 - cor 20% mais clara
- --2 - cor 10% mais clara
- --3 - cor original
- --4 - cor 10% mais escura
- --5 - cor 20% mais escura

Classes com hover

`.nomeDaClasse_hover`

#### Exemplo

**_index.sass**
```sass
+colors.custom-colors(myPink #f5015f)
```
**style.css**
```css
.color-myPink, .color-myPink_hover {
  color: #f5015f;
  -webkit-transition: 0.2s;
  transition: 0.2s;
}
.color-myPink_hover:hover {
  color: #d10151;
}

.bg-myPink, .bg-myPink_hover {
  background: #f5015f;
  -webkit-transition: 0.2s;
  transition: 0.2s;
}
.bg-myPink_hover:hover {
  background: #d10151;
}

.color-myPink--1, .color-myPink--1_hover {
  color: #fe5e9c;
  -webkit-transition: 0.2s;
  transition: 0.2s;
}
.color-myPink--1_hover:hover {
  color: #ffa0c4;
}

.bg-myPink--1, .bg-myPink--1_hover {
  background: #fe5e9c;
  -webkit-transition: 0.2s;
  transition: 0.2s;
}
.bg-myPink--1_hover:hover {
  background: #ffa0c4;
}

.color-myPink--2, .color-myPink--2_hover {
  color: #fe2b7c;
  -webkit-transition: 0.2s;
  transition: 0.2s;
}
.color-myPink--2_hover:hover {
  color: #fe3a86;
}

.bg-myPink--2, .bg-myPink--2_hover {
  background: #fe2b7c;
  -webkit-transition: 0.2s;
  transition: 0.2s;
}
.bg-myPink--2_hover:hover {
  background: #fe3a86;
}

/* ... Até a tonalidade --5 */
```

<br>

> A biblioteca também oferece cores padrão. Caso queira ver e alterar elas <a href="#colors">Clique aqui</a>

<br>

### 2. fontes<span id="include-fonts"></span>

Caso queira incluir fontes ao seu projeto basta chamar a função:

```sass
+fonts.config($fonts...)
```

`$fonts...` é o parâmetro à ser preenchido para incluir as fontes.

Os valores aceitos referentes as fontes válidas são:
- **lato** - para a fonte [Lato](https://fonts.google.com/specimen/Lato)
- **roboto** - para a fonte [Roboto](https://fonts.google.com/specimen/Roboto)
- **poppins** - para a fonte [Poppins](https://fonts.google.com/specimen/Poppins)
- **open-sans** - para a fonte [Open Sans](https://fonts.google.com/specimen/Open+Sans)
- **montserrat** - para a fonte [Montserrat](https://fonts.google.com/specimen/Montserrat)
- **ubuntu** - para a fonte [Ubuntu](https://fonts.google.com/specimen/Ubuntu)
- **dancing-script** - para a font [Dancing Script](https://fonts.google.com/specimen/Dancing+Script)
- **roboto-mono** - para a fonte [Roboto Mono](https://fonts.google.com/specimen/Roboto+Mono)
- **noto-sans** - para a fonte [Noto Sans](https://fonts.google.com/noto/specimen/Noto+Sans)
- **ibm-plex-mono** - para a fonte [IBM Plex Mono](https://fonts.google.com/specimen/IBM+Plex+Mono)

#### Exemplo

- Incluindo uma fonte:

```sass
+fonts.config(poppins)
```

- Incluindo mais de uma fonte:

```sass
+fonts.config(lato, ibm-plex-mono)
```
<br>

> :warning: Ao incluir uma ou mais fontes, a primeira será a fonte padrão do projeto

<br>

A função também gerará classes utilitárias referentes a(s) fonte(s) incluída(s) bem como seus pesos.

#### Exemplo

**_index.sass**
```sass
+fonts.config(ubuntu)
```

**style.css**

```css
* {
  font-family: Ubuntu, Arial, Helvetica, sans-serif;
}

.ubuntu--300 {
  font-family: Ubuntu;
  font-weight: 300;
}

.ubuntu--400 {
  font-family: Ubuntu;
  font-weight: 400;
}

.ubuntu--500 {
  font-family: Ubuntu;
  font-weight: 500;
}

.ubuntu--700 {
  font-family: Ubuntu;
  font-weight: 700;
}
```

<br>

### 3. Scrollbar (barra de rolagem)<span id="include-scrollbar"></span>

Caso queira personalizar a barra de rolagem do seu projeto basta chamar a função:

```sass
+scrollbar.config($width: 1rem, $color: colors.$accent-color, $track: colors.$light-theme)
```

- `$width` - parâmetro que dita a largura da barra de rolagem
  - Qualquer unidade de espaço (Valor padrão `1rem`)
- `$color` - parâmetro que dita a cor da parte móvel da barra de rolagem
  - cores - `#hex`, `rgb()`, `rgba()`, `hsl()` ou `name` (valor: padrão `colors.$accent-color` (cor de destaque padrão do módulo [_colors.sass](#colors)))
- `$track` - parâmetro que dita a cor dao traçado da barra de rolagem
  - cores - `#hex`, `rgb()`, `rgba()`, `hsl()` ou `name` (valor: padrão `colors.$accent-color` (cor de destaque padrão do módulo [_colors.sass](#colors)))

### Exemplo

função sem alteração de parâmetros

```sass
+scrollbar.config
```

função com parâmetros personalizados

```sass
+scrollbar.config(10px, red, green)
```

<br>

### style.sass<span id="style"></span>

---

Estilo geral. Aqui que você escreverá o estilo do seu projeto em específico

Inclui os módulos em:

```sass
@use 'modules' as fg
```

### Funções acessíveis dos módulos:

- [_position.sass](#position)
- [_radius.sass](#radius)
- [_utilities.sass](#utilities)

### variáveis acessíveis

- Variáveis das cores padrão do módulo de cores [_colors.sass](#colors)

<br>

### _colors.sass<span id="colors"></span>

---

Módulo que controla as cores da biblioteca. Gera classes utilitárias para para `color` e `background` com base nas cores padrão (ver abaixo) e na função de cores customizadas

 ### Variáveis padrão
 
```sass
$primary-dark:    black   !default
$secondary-dark:  #2b2b2b !default
$primary-light:   white   !default
$secondary-light: #c5c5c5 !default
$dark-theme:      #060018 !default
$light-theme:     white   !default
$accent-color:    #002fff !default
$accent-color--2: #ffe100 !default
```

### Semântica

Semanticamente as variáveis devem ser usadas para:

- `$primary-dark` - cor escura principal
- `$secondary-dark` - cor escura secundária
- `$primary-light` - cor clara principal
- `$secondary-light` - cor clara secundária
- `$dark-theme` - cor para o tema escuro do projeto
- `$light-theme` - cor para o tema claro do projeto
- `$accent-color` - cor  de destaque principal
- `$accent-color--2` - cor  de destaque secundária 

### Classes utilitárias

#### Color

```sass
.color-(nome das variávies)
.color-(nome das variávies)_hover // a cor fica mais clara ou mais escura com base em seu brilho
```

#### Exemplo

```sass
.color-primary-dark
```

<br>

#### Background

```sass
.bg-(nome das variávies)
.bg-(nome das variávies)_hover // a cor fica mais clara ou mais escura com base em seu brilho
```

#### Exemplo

```sass
.bg-accent-color_hover
```

#### Exemplo de variável em [style.sass](#style)

```sass
fg.$primary-dark
```

### Alterando as variáveis

Para alterar o valor das variáveis basta ir até o módulo [_index.sass](#index), adicionar a instrução with na linha `@forward 'colors'` e fornecer o nome da variável a ser mudada e o novo valor

#### Exemplo

```sass
@forward 'colors' with ($dark-theme: #050505, $accent-color--2: #f5015f)
```

### Função para cores customizadas

Para ver como usar a função para cores customizadas [Clique aqui](#custom-colors)

### Namespace em [_index.sass](index)

`colors.`

<br>

### _fonts.sass<span id="fonts"></span>

---

Módulo que controla as fontes incluídas no projeto. Define a fonte padrão do documento e gera classes utilitárias com base nas fontes incluídas e seus pesos

As fontes são pegas do [Google Fonts](https://fonts.google.com)

### Incluir fontes ao projeto

Para incluir fontes ao teu projeto [Clique aqui](#include-fonts)

### Namespace em [_index.sass](#index)

`fonts.`

<br>

### _index.sass<span id="index"></span>

---

Hub dos módulos

Todos os módulos são incluídos nele

### Namespaces para funções de configuração

- `colors.` - [_colors.sass](#colors)
- `fonts.` - [_fonts.sass](#fonts)
- `scrollbar.` - [_scrollbar.sass](#scrollbar)

### Prefixos para funções utilitárias

- `pos-*` - [_position.sass](#position)
- `radius-*` - [_radius.sass](#radius)

<br>

### _position.sass<span id="position"></span>

---

Módulo que disponibiliza funções utilitárias que giram em torno da propriedade `position` e suas propriedades satélites: `top`, `bottom`, `left` e `right`

### Prefixo em [_index.sass](#index)

`pos-*`

### Funções em [style.sass](#style)

```sass
+fg.pos-t-l($position, $top: 0, $left: 0)

+fg.pos-t-r($position, $top: 0, $right: 0)

+fg.pos-b-l($position, $bottom: 0, $left: 0)

+fg.pos-b-r($position, $bottom: 0, $right: 0)
```

#### Parâmetros das funções

- `$position` - determina o tipo de posição do elemento
  - Valores de `position`
- `$top` - define o espaço acima do elemento
  - Qualquer unidade de espaço (valor padrão 0)
- `$right` - define o espaço a direita do elemento
  - Qualquer unidade de espaço (valor padrão 0)
- `$bottom` - define o espaço abaixo do elemento
  - Qualquer unidade de espaço (valor padrão 0)
- `$left` - define o espaço a esquerda do elemento
  - Qualquer unidade de espaço (valor padrão 0)

<br>

### _pre-configs.sass<span id="pre-configs"></span>

---

Módulo com configurações iniciais genéricas para o projeto

### Configuração de tema do projeto

Se a tag `<body>` estiver sem classe o documento utilizará o tema claro (cor do tema claro: `colors.$light-theme` (variável de cor em [_colors.sass](#colors)))
	
Se a tag `<body>` estiver com a classe `.dark-theme` o documento utilizará o tema escuro (cor do tema escuro: `colors.$dark-theme` (variável de cor em [_colors.sass](#colors)))

<br>

### _radius.sass<span id="radius"></span>

---

Módulo que oferece funções utilitárias para arredondamento de borda

### Funções em [style.sass](#style)

```sass
+fg.radius-top($radius: .5rem)

+fg.radius-bottom($radius: .5rem)

+fg.radius-left($radius: .5rem)

+fg.radius-right($radius: .5rem)
```

### Parâmetros

- `$radius` - arredondamento de borda
  - Qualquer unidade de espaço (valor padrão `.5rem`)

<br>

### _scrollbar.sass<span id="scrollbar"></span>

---

Módulo que disponibiliza a inclusão e customização de uma barra de rolagem para o projeto

### Cutomização da barra de rolagem

Para inserir a barra de rolagem ao teu projeto [Clique aqui](#include-scrollbar)

### Namespace em [_index.sass](#index)

`scrollbar.`

<br>

### _utilities.sass<span id="utilities"></span>

---

Módulo para funções utilitárias diversas em [style.sass](#style)

### Cortar imagem

```sass
+fg.cut-img($width: 100%, $height: 100%, $position: center)
```

#### Parâmetros

- `$width` - largura da imagem
  - Qualquer unidade de espaço (valor padrão `100%`)
- `$height` - largura da imagem
  - Qualquer unidade de espaço (valor padrão `100%`)
- `$position` - posicão do corte
  - Valores de `object-position`

<br>

### Flexbox

```sass
+fg.flexbox($justify-content: flex-start,$align-items: stretch,$direction: row)
```

#### Parâmetros

- `$justify-content` - justifica os flex items
  - Valores de `justify-content` (valor padrão `flex-start`)
- `$align-items` - alinha os flex items
  - Valores de `align-items` (valor padrão `stretch`)
- `$direction` - direção do flex container
  - Valores de `flex-direction` (valor padrão `row`)

<br>

### Quadrado

```sass
+fg.square($width, $color, $radius: .4rem)
```

#### Parâmetros

- `$width` - largura do quadrado
  - Qualquer unidade de espaço
- `$color` - cor do quadrado
  - cores - `#hex`, `rgb()`, `rgba()`, `hsl()` ou `name`
- `$radius` - raio da borda
  - Qualquer unidade de espaço (Valor padrão `.4rem`)

<br>

### Círculo

```sass
+fg.circle($width, $color)
```

#### Parâmetros

- `$width` - largura do círculo
  - Qualquer unidade de espaço
- `$color` - cor do círculo
  - cores - `#hex`, `rgb()`, `rgba()`, `hsl()` ou `name`

<br>

### Obrigado por usar minha biblioteca :)
