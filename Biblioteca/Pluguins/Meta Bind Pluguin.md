---
Etiqueta: 📑
Categoria: obsidian pluguins
Tipo: Anotação
Subtipo: Pluguins
Pluguin: Meta bind
Função: Anotações interativas
Link: https://www.youtube.com/watch?v=iAYS0254a7I
Ano: "2024"
tags:
  - Biblioteca
Gênero: ""
Capa: https://images.spiceworks.com/wp-content/uploads/2022/12/26124808/Mobile-Apps.jpg
---
#Biblioteca/Pluguins

# Tutorial Básico
**Tutorial do Plugin Obsidian Meta Bind**

**Introdução**

O Obsidian Meta Bind é um plugin para o aplicativo de anotações Obsidian que permite vincular metadados a blocos de texto. Isso permite que você crie links rápidos, organize anotações e adicione contexto extra ao seu conteúdo.

**Configuração**

1. **Instale o plugin:** Vá para o diretório de plugins do Obsidian e instale o plugin "Meta Bind".
2. **Crie um arquivo de metadados:** Crie um novo arquivo de anotação chamado ".obsidian-metadata" na raiz do seu cofre Obsidian.

**Uso**

**Vinculando Metadados a Blocos de Texto**

1. **Selecione o texto:** Selecione o bloco de texto ao qual deseja vincular metadados.
2. **Abra o painel Meta Bind:** Pressione `Ctrl` + `M` (Windows) ou `Cmd` + `M` (Mac) para abrir o painel Meta Bind.
3. **Adicione metadados:** Insira os metadados desejados na caixa de texto do painel. Você pode adicionar vários pares de metadados separados por vírgulas.
4. **Salve as alterações:** Clique em "Salvar" para vincular os metadados ao texto selecionado.

**Acessando Metadados**

1. **Passe o mouse sobre o texto:** Passe o mouse sobre o texto vinculado para visualizar os metadados em uma dica de ferramenta.
2. **Use a pesquisa:** Use a barra de pesquisa do Obsidian para pesquisar metadados específicos.
3. **Use o Dataview:** Integre o Meta Bind com o plugin Dataview para criar consultas e visualizações personalizadas com base em metadados.

**Exemplos de Aplicações**

- **Links rápidos:** Vincule URLs, e-mails e números de telefone a blocos de texto para acesso rápido.
- **Organização de anotações:** Atribua tags, categorias e rótulos a anotações para facilitar a organização e a recuperação.
- **Contexto adicional:** Adicione informações de contexto, como fontes, autores e datas, a blocos de texto para referência futura.
- **Gerenciamento de conhecimento:** Crie um sistema de anotações interconectadas vinculando metadados relacionados entre diferentes anotações.
- **Análise de dados:** Use o Dataview para analisar e visualizar metadados, identificando padrões e insights em seu conteúdo.

**Recursos Adicionais**

- **Suporte para vários tipos de metadados:** O Meta Bind suporta vários tipos de metadados, incluindo texto, números, URLs e datas.
- **Exportação e importação:** Exporte e importe metadados para facilitar o compartilhamento e a colaboração.
- **Integração com outros plugins:** O Meta Bind se integra a outros plugins populares do Obsidian, como o Outliner e o Table of Contents.

Lembre-se de que o arquivo ".obsidian-metadata" é essencial para o funcionamento do Meta Bind. Não o exclua ou mova.
# Meta Bind Video
Video explicativo:

# [Obsidian - Meta Bind - Input Fields and Calculators](https://www.youtube.com/watch?v=iAYS0254a7I)
<iframe width="300" height="213" src="https://www.youtube.com/embed/iAYS0254a7I?feature=oembed" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen title="Obsidian - Meta Bind - Input Fields and Calculators"></iframe>
Meta Bind é um plugin para [Obsidiana](https://obsidian.md/) para tornar suas anotações interativas!

Meta Bind permite que você crie **campos de entrada**, **exibição de metadados (ver campos)**, e **botões**. Os campos de entrada e exibição podem ser vinculados às propriedades frontmatter, o que os mantém sincronizados com essas propriedades frontmatter, permitindo que você edite e visualize suas propriedades frontmatter dentro de suas anotações.

Por exemplo, você pode criar uma alternância dentro de sua nota, que está vinculada a uma propriedade frontmatter nomeada `done`, com este simples bloco de código inline `INPUT[toggle:done]`. Quando você clica na alternância, o `done` a propriedade irá alternar entre `true` e `false`.

## Características

- **Campos de Entrada** - Insira e edite propriedades frontmatter de qualquer lugar dentro de suas anotações. As propriedades serão atualizadas em tempo real.
- **Ver Campos** Exibir propriedades frontmatter dentro de suas notas. O valor exibido será atualizado em tempo real quando as propriedades exibidas mudarem.
- **Botões** - Crie botões dentro de suas anotações que podem acionar ações ao clicar. Um sucessor espiritual para o descontinuado [Botões Plugin](https://github.com/shabegom/buttons).
- **Meta Bind Incorporação** - Incorpore perfeitamente uma nota dentro de outra nota. A nota incorporada será renderizada como se fosse parte da nota em que está incorporada.

## Começando

Primeiro você precisará instalar o plugin a partir do [Plugins da Comunidade](obsidian://show-plugin?id=obsidian-meta-bind-plugin) guia em configurações Obsidianilitols. Você pode encontrar vários guias sobre como usar o plugin na seção Guias na barra lateral.

Se você quiser ver todos os campos de entrada possíveis em ações, você pode executar o `Open Meta Bind Playground` comando dentro Obsidian. Se você está procurando exemplos, você pode explorar o [exemplo de cofre](https://github.com/mProjectsCode/obsidian-meta-bind-plugin/tree/master/exampleVault) que eu uso para testes.

## Erros, Erros ou Comportamento Inesperado?

Por favor, abra um relatório de bug sobre os plugins [Repositório github](https://github.com/mProjectsCode/obsidian-meta-bind-plugin/issues).

# Botões

Botão estão bem... Botões, dentro de suas notas. Eles podem ser configurados para fazer uma variedade de coisas, como abrir um arquivo, executar um comando ou até mesmo executar um arquivo JavaScript.

Nota

Uma lista de ações de botão, suas propriedades necessárias e exemplos podem ser encontrados na barra lateral abaixo `Reference -> Button Actions`.

## Criando um botão

Dica

Os botões podem ser facilmente criados usando o `Open Button Builder` comando.

Para criar um botão, você precisa criar um bloco de código com o idioma definido como `meta-bind-button`. O interior do bloco de código pertence à configuração no formato YAML para o botão.

O botão de exemplo a seguir é exibido `Meta Bind Help` e abre a página de FAQ do meta bind.

````
```meta-bind-buttonstyle: primarylabel: Meta Bind Helpaction:  type: command  command: obsidian-meta-bind-plugin:mb-open-faq```
````

## Botões Inline

Botões embutidos são botões que são exibidos em linha com o texto. Eles são criados usando blocos de código inline começando com `BUTTON`. Os botões embutidos devem fazer referência a um bloco de código de botão definido em outro lugar no **mesma nota** através de ids correspondentes.

Botões declarados nas configurações do plugin’ em `Button Templates` pode ser referenciado por botões em linha em cada nota.

O botão de exemplo a seguir faz referência ao botão de bloco de código com o `help-button` id abaixo dele. Ao fazer referência ao bloco de código do botão, o botão em linha terá a mesma configuração que o botão de bloco de código. O botão de bloco de código pode ser escondido definindo o `hidden` Propriedade YAML para `true`.

````
Meta Bind has an in plugin help page. `BUTTON[help-button]` Isn't that cool?
```meta-bind-buttonstyle: primarylabel: Meta Bind Helpid: help-buttonaction:  type: command  command: obsidian-meta-bind-plugin:open-faq```
````

## Grupos de Botões

Os botões em linha podem exibir vários botões em uma linha. Para isso, vários ids de botão separados por vírgulas precisam ser passados para o `BUTTON` bloco de código inline.

O exemplo a seguir exibe um grupo de botões de dois botões.

````
Theme Switcher: `BUTTON[light-mode, dark-mode]`
```meta-bind-buttonstyle: destructivelabel: Light Modeid: light-modehidden: trueactions:  - type: command    command: theme:use-light```
```meta-bind-buttonstyle: primarylabel: Dark Modeid: dark-modehidden: trueactions:  - type: command    command: theme:use-dark```
````

## Configuração do Botão

### Propriedades do Botão

A configuração YAML de um botão deve seguir a seguinte interface TypeScript.

```
interface ButtonConfig {  label: string; // The text displayed on the button  icon?: string; // An optional lucide icon to display on the button  style: 'default' | 'primary' | 'destructive' | 'plain'; // The style of the button  class?: string; // Optional CSS classes to add to the button. Multiple classes can be separated by spaces  tooltip?: string; // Optional tooltip to display when hovering over the button. If not set, the label is used  id?: string; // The optional id of the button, used for referencing the button in inline buttons  hidden?: boolean; // Whether this button should be hidden, useful when only using the button in inline buttons  action?: ButtonAction; // The action to perform when the button is clicked  actions?: ButtonAction[]; // Optionally multiple actions can be performed when the button is clicked}
```

`action` e `actions` são mutuamente exclusivos, o que significa que apenas um deles pode ser usado.

## Ações Botão

As ações de botão podem exigir várias propriedades dependendo do tipo de ação, mas cada ação tem um `type` propriedade, pela qual é identificada.

Uma lista de ações de botão e suas propriedades necessárias pode ser encontrada na barra lateral abaixo `Reference -> Button Actions`.
## Tem uma ideia para um novo recurso?

Solicitações de recursos e contribuições são sempre bem-vindas. Se você tiver uma ideia, sinta-se à vontade para abrir uma solicitação de recurso sob o [guia de problemas no GitHub](https://github.com/mProjectsCode/obsidian-meta-bind-plugin/issues) ou até mesmo criar uma solicitação pull.

# Alvos Vinculados

Bind Targets é um conceito central do Meta Bind. Eles são uma maneira baseada em texto para apontar o plugin em uma propriedade frontmatter específica. Este tutorial irá ensinar-lhe como usá-los.

Limitações

Os alvos vinculados são **estática**, o que significa que eles não podem ser alterados depois de terem sido criados.

Isso significa que você pode **não** tenha uma propriedade que controle para onde um destino de vinculação aponta, sem usar JavaScript. Ver [Exemplos Avançados](https://www.moritzjung.dev/obsidian-meta-bind-plugin-docs/guides/advancedusecases/).

## Sintaxe

Os alvos vinculados consistem em três partes.

```
storageType^storagePath#property
```

O `storageType` e `storagePath` pode ser omitido, fazendo com que eles tenham o padrão em seus valores padrão.

O seguinte destino de vinculação sempre usará o tipo de armazenamento padrão `frontmatter`, o que significa que aponta para uma propriedade frontmatter.

```
storagePath#property
```

Os seguintes destinos de vinculação sempre usarão o arquivo contendo como caminho de armazenamento. Contendo arquivo significa que o arquivo do destino ou campo de vinculação, do qual o destino de vinculação faz parte, está em.

```
property
storageType^property
```

### Exemplo de Valores Padrão

Isso significa que os seguintes alvos de ligação são **equivalente**, supondo que o arquivo atual seja `Test Note`.

```
property
frontmatter^Test Note#property
```

### 1. O Tipo Armazenamento

O tipo de armazenamento informa ao plugin para onde o caminho de armazenamento está apontando. Existem quatro tipos de armazenamento diferentes. O padrão é `frontmatter` e será usado se você especificar um tipo de armazenamento.

|Tipo de Armazenamento|Descrição|
|---|---|
|`frontmatter`(padrão)|O caminho de armazenamento aponta para um arquivo e a propriedade para um campo frontmatter.|
|`memory`|O caminho de armazenamento aponta para um arquivo e a propriedade para um campo na memória.|
|`globalMemory`|O caminho de armazenamento não é permitido e a propriedade aponta para um campo na memória.|
|`scope`|O caminho de armazenamento não é permitido e a propriedade estende outro destino de ligação.|

#### `frontmatter`

Isto refere-se ao frontmatter Obsidian’ que é um bloco YAML na parte superior de um arquivo.

#### `memory`

A memória é um armazenamento na memória que é **escopo** mas não salvo em nenhum arquivo. Isso significa que os valores que você escreve em um caminho de arquivo no cache **será perdido** quando nada usa o caminho do arquivo por um tempo, ou você reinicia Obsidian.

#### `globalMemory`

A Memória Global é um armazenamento na memória que é **não escopo** e não salvo em nenhum arquivo. A Memória Global é compartilhada entre todas as notas e **será perdido** quando reiniciar o Obsidian.

### 2. O Caminho do Armazenamento

O caminho de armazenamento geralmente aponta para um arquivo. Se omitido, o padrão é o arquivo contendo. Contendo arquivo significa que o arquivo do destino ou campo de vinculação, do qual o destino de vinculação faz parte, está em.

#### Exemplo

Letilitis imaginar que estamos em uma nota chamada `Overview` e queremos que nossa alternância não altere este status de conclusão do noteilits, mas o status da nossa nota de tarefa chamada `Task A`. Isso também é possível. Só precisamos dizer ao plugin para mudar `completed` em nota `Task A`. Fazemos isso vinculando-nos a `Task A#completed` (`file_name#frontmatter_field`).

A declaração do campo de entrada agora se parece com isso.

```
INPUT[toggle:Task A#completed]
```

Se você tiver várias notas com o mesmo nome, simplesmente especificar o nome não será suficiente, pois o plugin pode descobrir a qual você está se referindo. Nesse caso, você precisa especificar o caminho completo relativo à raiz do vault.

```
INPUT[toggle:path/to/Task A#completed]
```

### 3. A Propriedade

A propriedade é o nome do campo ao qual você deseja vincular. Para o tipo de armazenamento padrão `frontmatter`, este é o nome da propriedade frontmatter.

#### Propriedades com Espaços e Propriedades Aninhadas

O plugin usa sintaxe semelhante a JavaScript para acessar o frontmatter. Isso significa que, a fim de se ligar a um campo frontmatter com caracteres especiais, como espaços, você precisa usar a sintaxe do suporte JavaScript.

Isso vai **não** trabalho.

```
INPUT[toggle:is completed]
```

Mas isso vai.

```
INPUT[toggle:["is completed"]]
```

Para acessar campos frontmatter aninhados, você pode usar um simples `.` ou sintaxe de suporte. Os dois exemplos seguintes são **equivalente**.

```
INPUT[toggle:this.is.nested]
```

```
INPUT[toggle:this["is"].nested]
```
### Argumentos Permitidos

Os seguintes argumentos de campo de entrada são permitidos para o `date` campo de entrada.

- [`class`](https://www.moritzjung.dev/obsidian-meta-bind-plugin-docs/reference/inputfieldarguments/class/)
- [`defaultValue`](https://www.moritzjung.dev/obsidian-meta-bind-plugin-docs/reference/inputfieldarguments/defaultvalue/)
- [`showcase`](https://www.moritzjung.dev/obsidian-meta-bind-plugin-docs/reference/inputfieldarguments/showcase/)
- [`title`](https://www.moritzjung.dev/obsidian-meta-bind-plugin-docs/reference/inputfieldarguments/title/)

[Anterior](https://www.moritzjung.dev/obsidian-meta-bind-plugin-docs/guides/obsidianpublish/)
# Selecionador de Data

|   |   |
|---|---|
|Identificador|`datePicker`|
|Permitido no Bloco de Código|`true`|
|Permitido Inline|`true`|

A _selecionador de data_ o campo de entrada é um selecionador de dados simples que trata `null` como nenhuma data definida.

### Argumentos Permitidos

Os seguintes argumentos de campo de entrada são permitidos para o `datePicker` campo de entrada.

- [`class`](https://www.moritzjung.dev/obsidian-meta-bind-plugin-docs/reference/inputfieldarguments/class/)
- [`defaultValue`](https://www.moritzjung.dev/obsidian-meta-bind-plugin-docs/reference/inputfieldarguments/defaultvalue/)
- [`showcase`](https://www.moritzjung.dev/obsidian-meta-bind-plugin-docs/reference/inputfieldarguments/showcase/)
- [`title`](https://www.moritzjung.dev/obsidian-meta-bind-plugin-docs/reference/inputfieldarguments/title/)
# itor

|   |   |
|---|---|
|Identifier|`editor`|
|Allowed in Code Block|`true`|
|Allowed Inline|`false`|

An _editor_ input field is similar to a [`textArea`](https://www.moritzjung.dev/obsidian-meta-bind-plugin-docs/reference/inputfields/textarea/), but with full markdown support.

### Allowed Arguments

The following input field arguments are allowed for the `editor` input field.

- [`class`](https://www.moritzjung.dev/obsidian-meta-bind-plugin-docs/reference/inputfieldarguments/class/)
- [`defaultValue`](https://www.moritzjung.dev/obsidian-meta-bind-plugin-docs/reference/inputfieldarguments/defaultvalue/)
- [`showcase`](https://www.moritzjung.dev/obsidian-meta-bind-plugin-docs/reference/inputfieldarguments/showcase/)
- [`title`](https://www.moritzjung.dev/obsidian-meta-bind-plugin-docs/reference/inputfieldarguments/title/)

# Image List Suggester

|   |   |
|---|---|
|Identifier|`imageListSuggester`|
|Allowed in Code Block|`true`|
|Allowed Inline|`false`|

An _image list suggester_ input field allows for multiple selections from a gallery of images.

Images can be moved and deleted from the list by right-clicking on the image (or long-pressing on mobile) and selecting the appropriate action.

### Allowed Arguments

The following input field arguments are allowed for the `imageListSuggester` input field.

- [`class`](https://www.moritzjung.dev/obsidian-meta-bind-plugin-docs/reference/inputfieldarguments/class/)
- [`defaultValue`](https://www.moritzjung.dev/obsidian-meta-bind-plugin-docs/reference/inputfieldarguments/defaultvalue/)
- [`option`](https://www.moritzjung.dev/obsidian-meta-bind-plugin-docs/reference/inputfieldarguments/option/)
- [`optionQuery`](https://www.moritzjung.dev/obsidian-meta-bind-plugin-docs/reference/inputfieldarguments/optionquery/)
- [`showcase`](https://www.moritzjung.dev/obsidian-meta-bind-plugin-docs/reference/inputfieldarguments/showcase/)
- [`title`](https://www.moritzjung.dev/obsidian-meta-bind-plugin-docs/reference/inputfieldarguments/title/)

# Exemplos

multiseleção

```meta-bind
INPUT[multiSelect(option(Passar_Pano), option(Lavar_prato), option(Limpar_frente), option(molhar_plantas), option(Banheiro), option(Lavar_roupas), option(Tirar_pó), option(organizar), option(anki), option(Mondley), option(Duolingo), option(Trabalhar), option(Estudar), option(Limpar_fogão_pia)):tags]
```