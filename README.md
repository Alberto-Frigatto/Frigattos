# Biblioteca-Bufos
Biblioteca Front-end concebida em Sass

  CRÉDITOS

      Autor: Alberto Frigatto de Andrade ferreira
      Versão: 1.1.2
      Data: 14/09/2022
      Email: albertofrigatto.comercial@gmail.com
      Linkedin: https://www.linkedin.com/in/alberto-frigatto-a72022251
      Editor: Visual Studio Code
      Plataforma: Windows 10 21H2 64bit

   INSTALAÇÃO

      Inclua essa pasta dentro de css/.
      Instale as extensões:
         Live Sass Compiler (https://marketplace.visualstudio.com/items?itemName=glenn2223.live-sass)
         Sass (https://marketplace.visualstudio.com/items?itemName=syler.sass-indented)
      Adicione essa configuração ao settings.json de seu Visual Studio Code depois de ter instalado as extensões:

      CSS comprimido (.min.css)

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

      CSS expandido (.css)

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

   ARQUIVOS

      /style.sass - estilo geral
      /modules/_colors.sass - biblioteca de cores
      /modules/_fonts.sass - biblioteca de fontes
      /modules/_index.sass - intermédio das bibliotecas ao estilo geral
      /modules/_position.sass - biblioteca de funções de posições
      /modules/_pre-configs.sass - biblioteca de configurações iniciais
      /modules/_scrollbar.sass - biblioteca da barra de rolagem
      /modules/_utilities.sass - biblioteca com @mixin utilitários



      /style.sass

         Estilo geral.
         Aqui constará a formatação do projeto em específico.
         Inclui as bibliotecas por meio de "@use 'modules' as m" o que significa que o namespace das funções passa a ser 'm'



      /modules/_colors.sass

         Biblioteca de cores.
         Usa a biblioteca 'sass:color'
         Controla:
            Os valores de suas variáveis de cor;
            A criação de classes utilitárias para background e color com suas variáveis de cor;
            A criação de classes utilitárias para background e color inserindo tons mais claros e mais escuros
            para a cor fornecida pelo usuário.

         VARIÁVEIS

            $primary-dark: black !default
            $secondary-dark: #2b2b2b !default
            $primary-light: white !default
            $secondary-light: #c5c5c5 !default
            $dark-theme: #060018 !default
            $light-theme: white !default
            $accent-color: #002fff !default
            $accent-color-2: #ffe100 !default

         @mixin em /modules/_index.sass

            +colors.custom($colors...) - OPCIONAL

            Gera classes utilitárias para color e background com base no valor passado pelo usuário.
            As classes são geradas com base em tonalidades derivadas da cor original fornecidada pelo usuário.
            A sintaxe das classes segue .color-(nome da cor)--(nível de tonalidade) e .bg-(nome da cor)--(nível de tonalidade). O nível de
            tonalidade vai de 1 à 5, sendo 1 o tom mais claro e 5 o mais escuro.
            As níveis de tonalidade possuem os seguintes ajustes de $lightness:
               1: 20%
               2: 10%
               3: 0
               4: -10%
               5: -20%
            Exemplos: .bg-yellow--2, .color-purple--5

            ARGUMENTOS

               $colors... - list de 2 valores
               
               VALORES

                  $colors... - 1º valor: nome da cor, 2º valor: cor (nome, rgb(), rgba(), hsl(), hsla(), #hex)

         CLASSES UTILITÁRIAS

            COLOR

               .color-(nome das variáveis)

            BACKGROUND

               .bg-(nome das variáveis)
               .bg-(nome das variáveis)_hover - classe que quando está no estado :hover torna a cor mais clara ou mais escura de acordo com qual
               variável foi usada



      /modules/_fonts.sass

         Biblioteca de fontes.
         Controla quais fontes são incluídas no estilo com base na selecão do usuário.
         Usa fontes do Google Fonts (https://fonts.google.com).
         Fontes incluídas:
            Lato;
            Roboto;
            Poppins;
            Open Sans;
            Montserrat;
            Ubuntu;
            Dancing Script.

         @mixin em /modules/_index.sass

            +fonts.config($fonts...) - OPCIONAL

            ARGUMENTOS

               $fonts... - list de 1 valor

               VALORES

                  $fonts... - Lato, Roboto, Poppins, Opens-Sans, Montserrat, Ubuntu, Dancing-Script



      /modules/_index.sass

         Intermédio das bibliotecas ao estilo geral (/style.sass).
         Inclui todas as bibliotecas nele mesmo;

         NAMESPACES (úteis)

            colors - /modules/_colors.sass
            fonts - /modules/_fonts.sass
            scrollbar - /modules/_scrollbar.sass

         PREFIXOS

            pos-* - /modules/_position.sass
            ut-* - /modules/_utilities.sass



      /modules/_position.sass

         Biblioteca para @mixin de posição (position) para um elemento.
         Disponibiliza @mixin utilitários com base em 'position' e suas propriedades complementares 'top', 'right', 'bottom' e 'left'.
         Recebe o prefixo pos-* em /modules/_index.sass.

         @mixin em /style.sass

            +m.pos-t-l($position, $top: 0, $left: 0) - OPCIONAL
            +m.pos-t-r($position, $top: 0, $right: 0) - OPCIONAL
            +m.pos-b-l($position, $bottom: 0, $left: 0) - OPCIONAL
            +m.pos-b-r($position, $bottom: 0, $right: 0) - OPCIONAL

            ARGUMENTOS

               $position - determina o tipo de posição do elemento
               $top - define o espaço acima do elemento
               $right - define o espaço a direita do elemento
               $bottom - define o espaço abaixo do elemento
               $left - define o espaço a esquerda do elemento

               VALORES

                  $position: absolute, fixed, relative, static e sticky
                  $top - qualquer unidade de espaço (valor padrão 0)
                  $right - qualquer unidade de espaço (valor padrão 0)
                  $bottom - qualquer unidade de espaço (valor padrão 0)
                  $left - qualquer unidade de espaço (valor padrão 0)



      /modules/_pre-configs.sass

         Biblioteca com configurações iniciais genéricas para o estilo do documento.
         Usa a biblioteca /modules/_colors.sass.

         CONFIGURAÇÃO DE TEMA

            Se a tag <body> estiver sem class o documento utilizará o tema claro.
            Se a tag <body> estiver com a classe .dark-theme o documento utilizará o tema escuro.



      /modules/_scrollbar.sass

         Biblioteca para a inserção ou customização de uma barra de rolagem para o documento.
         Utiliza a biblioteca /modules/_colors.sass.
         Utiliza a biblioteca 'sass:color'.

         @mixin em /modules/_index.sass

            +scrollbar.config($width: 1rem, $color: colors.$accent-color, $track: colors.$light-theme) - OPCIONAL

            ARGUMENTOS

               $width - largura da barra de rolagem
               $color - cor da móvel
               $track - cor do traçado da barra

               VALORES

                  $width - qualquer unidade de espaço (valor padrão 1rem)
                  $color - cor (nome, rgb(), rgba(), hsl(), hsla(), #hex)
                  $track - cor (nome, rgb(), rgba(), hsl(), hsla(), #hex)



      /modules/_utilities.sass

         Biblioteca de @mixin utilitários.
         Recebe o prefixo ut-* em /modules/_index.sass.

         @mixin em /style.sass

            +m.ut-cut-img($width: 100%, $height: 100%, $fit: cover, $position: center)

               ARGUMENTOS

                  $width - largura da imagem
                  $height - largura da imagem
                  $fit - modo de corte
                  $position - posicão do corte

                  VALORES

                     $width - qualquer unidade de espaço (valor padrão 100%)
                     $height - qualquer unidade de espaço (valor padrão 100%)
                     $fit - valores de object-fit
                     $position - valores de object-position

            +m.ut-flexbox($justify-content: flex-start,$align-items: stretch,$direction: row)

               ARGUMENTOS

                  $justify-content - justifica os flex items
                  $align-items - alinha os flex items
                  $direction - direção do flex container

                  VALORES

                     $justify-content - valores de justify-content (valor padrão flex-start)
                     $align-items - valores de align-items (valor padrão stretch)
                     $direction - valores de flex-direction (valor padrão row)

            +m.ut-square($width, $color, $radius: 1rem)

               ARGUMENTOS

                  $width - largura do quadrado
                  $color - cor do quadrado
                  $radius - raio da borda

                  VALORES

                     $width - qualquer unidade de espaço
                     $color - cor (nome, rgb(), rgba(), hsl(), hsla(), #hex)
                     $radius - qualquer unidade de espaço (valor padrão 1rem)

Obrigado por usar minha biblioteca :)
