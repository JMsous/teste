---
Categoria:
  - Manual
Tipo:
  - Anotação
Título: Manual Dataview
tags:
  - MinhasNotas
Etiqueta: 💭
Ano: "2024"
Gênero:
  - ""
Subtipo: Manual
Capa: https://guiadoestudante.abril.com.br/wp-content/uploads/sites/4/2020/11/criatividade-1.jpg?quality=100&strip=info&w=1024
---
#Biblioteca/anotações/manualdataview 
# Resumo Dataview
o dataview é um aplicativo poderoso e com ele dá para fazer muitas coisas segue o resumo:
Obs: substitua a plavra exemplo pelo termo que você quer pesquisar:
## Listas

### Lista simples
```dataview
list(se apagar o trecho em parenteses será criada uma notas de tudo que tem no cofre)
```

### Lista simples por pasta

```dataview
list
from "exemplo"
```

### Lista simples por tag

```dataview
list
from "exemplo"
```
### Lista simples por propriedade

```dataview
list
from "exemplo"
where contains(exemplo, "valor")
```
### ### Lista simples por mês de criação

```dataview
list
from "exemplo"
where month = exemplo
```

### ### Lista simples por mês na nota diária

```dataview
list
from "#exemplo"
where contains(file.name, "ano-mês")
```

### ### Lista simples por  link

```dataview
list
from [[exemplo]]
```

### lista simples de pesquisa por Menções feitas

entrada

```dataview
list
from [[Yoga MOC]]
```

Ou sair _de_ uma nota:

```dataview
list
from outgoing([[yoga MOC]])
```
### Lista complexa usando mais de um dado

- `list from #A and #B`
- `list from "University" or "Work"`
- `list from -#Personal`
- `list from [[CSS]] and -#HTML`

### Lista complexa com concatenação
(use os metadados para filtrar e o último é a informação extra pode escrever o que quiser)
```dataview
list "File Path: " + file.path + " :)"
from #Limpeza
```
### Listas complexas de outras listas

A `list`também pode exibir sublistas recortada de metadados:
```dataview
list Autor
from #Biblioteca/livros/tudoério or #Biblioteca/livros/leidaatraçãoeopoderdopensamento 
```
### Descobrir

```dataview 
LIST rows.c 
WHERE typeof(Francês) = "array" AND contains(Francês, "true") 
SORT length(Francês) 
FLATTEN Francês as c 
SORT link(c).age ASC 
```
```dataview 
LIST rows.c 
WHERE contains(file.name, "2024-06")
SORT file.link ASC 
group by Tipo
```

```dataview 
LIST WITHOUT ID length(rows) + " paginas do tipo " + key 
GROUP BY Categoria
limit 10
```

## Tabelas
### Tabela simples
(os itens anteriores das listas se aplicam aqui também)

```dataview
table Título, Autor, Classificação
from #Biblioteca/livros/tudoério 
```

### Tabela agrupada por valor de uma propriedade

```dataview
table intensity, rows.Status
from #Biblioteca/livros/tudoério OR #Biblioteca/livros/vidaliquida
group by file.name
```

### Tabela complexa por menção fala todas as notas em que aquela nota foi mencionada

```dataview
table file.inlinks AS "Menções"
FROM #Biblioteca/livros/leidaatraçãoeopoderdopensamento 
````

### pesquisa com nome de arquivo + simbolo
```dataview
list " Francês Status ❌" + without.Francês
from "Agenda/Diário"
where Francês = false
where contains(file.name, "2024-07")
```
### campos para testes

```dataview
list
from [[exemplo]]
```


```dataview
list
from [[exemplo]]
```


```dataview
list
from [[exemplo]]
```


```dataview
list
from [[exemplo]]
```


```dataview
list
from [[exemplo]]
```


```dataview
list
from [[exemplo]]
```


```dataview
list
from [[exemplo]]
```

# Tipos de pesquisa DATAVIEW

### Lista
Lists all pages in your vault as a bullet point list 

```dataview 
LIST 
limit 5
``` 
### Tarefas
Lists all tasks (completed or not) in your vault
```dataview 
TASK 
limit 5
```
### Calendário

Renders a Calendar view where each page is represented as a dot on its creation date. 
```dataview
CALENDAR file.cday 
``` 

### Tags
Shows a table with all pages of your vault, their field value of due, the files' tags and an average of the values of multi-value field working-hours 

```dataview 
TABLE due, file.tags AS "tags"
limit 5
```

## Dataview Inline

> [!note] um mostra os arquivo recentes e o outro mostra o número de arquivos na pasta
>- 📑[[Biblioteca]] |📁  `$=dv.pages('"Biblioteca"').length`
>`$=dv.list(dv.pages('"Biblioteca"').sort(f=>f.file.mtime.ts,"desc").limit(4).file.link)`
 
 - soma  de valores
`where sum(Peso) < 60`
- Nome do arquivo atual para aparecer outro utilize referência [[]]
`= this.file.name` 
- Mostra data e hora atual
`= this.file.mtime`
- Soma dos metadados (ainda não descobrir como usar)
`= this.someMetadataField`
- Apenas o nome do arquivo
`= [[2024-06]].file.name` 

- Data de modificação da página

`= [[2024-06]].file.mtime` `= [[secondPage]].someMetadataField` 

- ir para arquivos por Datas:
 📆 `$= '[['+ moment().format("YYYY-MM-DD") +'|Hoje]]'` 📆 `$= '[['+ moment().format("YYYY-MM") +'|Este mês]]'` 📆 `$= '[['+ moment().format("YYYY") +'|Este Ano]]'` 
 
 - inserir botão
  `BUTTON[pesquisa]`
# [Dataview](https://blacksmithgu.github.io/obsidian-dataview/#/functions)
  
O Dataview é um mecanismo de consulta e índice ativo em sua base de conhecimento pessoal. Você pode [**adicionar metadados**](https://blacksmithgu.github.io/obsidian-dataview/annotation/add-metadata/) às suas anotações e **consultá-las** com a [**Dataview Query Language**](https://blacksmithgu.github.io/obsidian-dataview/queries/structure/) para listar, filtrar, classificar ou agrupar seus dados. O Dataview mantém suas consultas sempre atualizadas e torna a agregação de dados muito fácil.

Você pode

- Controlar seu sono registrando-o em anotações diárias e criar tabelas semanais automaticamente com seu cronograma de sono.
- Coletar automaticamente links para livros em suas anotações e processá-los classificados por classificação.
- Coletar automaticamente páginas associadas à data de hoje e exibi-las em sua anotação diária.
- Encontrar páginas sem tags para acompanhamento ou exibir visualizações agradáveis de páginas com tags específicas.
- Criar visualizações dinâmicas que exibem aniversários ou eventos futuros registrados em suas anotações

e muito mais.

O Dataview oferece uma maneira rápida de pesquisar, exibir e operar em dados indexados em seu cofre!
O Dataview é altamente genérico e de alto desempenho, escalando para centenas de milhares de anotações anotadas sem problemas.
Se a [linguagem de consulta](https://blacksmithgu.github.io/obsidian-dataview/query/queries/) incorporada for insuficiente para sua finalidade, você pode executar um JavaScript arbitrário na [API do Dataview](https://blacksmithgu.github.io/obsidian-dataview/api/intro/) e criar qualquer utilitário que possa precisar em suas anotações.
O Dataview é para exibir, não para editar
O Dataview serve para exibir e calcular dados. Ele não deve editar suas anotações/metadados e sempre os deixará intactos [... exceto se você estiver marcando uma [tarefa](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#task-queries) via Dataview.]
## Uma Introdução ao [Dataview](https://publish.obsidian.md/hub/02+-+Community+Expansions/02.05+All+Community+Expansions/Plugins/dataview)

Esta é uma versão reformatada e compatível com a web do primeiro [Web Talk](https://publish.obsidian.md/hub/01+-+Community/Events/Obsidian+Community+Talks) da [Comunidade Obsidian](https://publish.obsidian.md/hub/01+-+Community/Events/Obsidian+Community+Talks), uma visão geral do plugin [Dataview](https://publish.obsidian.md/hub/02+-+Community+Expansions/02.05+All+Community+Expansions/Plugins/dataview), realizada pelo [SkepticMystic](https://publish.obsidian.md/hub/01+-+Community/People/SkepticMystic).

Os slides originais podem ser encontrados [aqui](https://publish.obsidian.md/hub/04+-+Guides%2C+Workflows%2C+%26+Courses/Guides/An+Introduction+to+Dataview+Slides) e são melhor visualizados com o plugin Obsidian e Advanced [Slides](https://publish.obsidian.md/hub/02+-+Community+Expansions/02.05+All+Community+Expansions/Plugins/obsidian-advanced-slides) ou [convertidos](https://publish.obsidian.md/hub/02+-+Community+Expansions/02.05+All+Community+Expansions/Auxiliary+Tools/revealjs) para [revelarjs](https://publish.obsidian.md/hub/02+-+Community+Expansions/02.05+All+Community+Expansions/Auxiliary+Tools/revealjs) com [Pandoc](https://publish.obsidian.md/hub/04+-+Guides%2C+Workflows%2C+%26+Courses/Community+Talks/YT+-+Pandoc+and+Obsidian+-+Create+slideshows%2C+PDFs+and+Word+documents). Certifique-se também de dar uma olhada no [vídeo do YouTube](https://publish.obsidian.md/hub/04+-+Guides%2C+Workflows%2C+%26+Courses/Community+Talks/YT+-+An+Introduction+to+Dataview) para explicações detalhadas.

Por [CéticoMystic](https://publish.obsidian.md/hub/01+-+Community/People/SkepticMystic)

## Visão geral

1. [Ampla introdução ao Dataview](https://publish.obsidian.md/hub/04+-+Guides%2C+Workflows%2C+%26+Courses/Guides/An+Introduction+to+Dataview#Introduction)
2. [Metadados](https://publish.obsidian.md/hub/04+-+Guides%2C+Workflows%2C+%26+Courses/Guides/An+Introduction+to+Dataview#Metadata)
3. [Perguntas de Dataview](https://publish.obsidian.md/hub/04+-+Guides%2C+Workflows%2C+%26+Courses/Guides/An+Introduction+to+Dataview#Dataview Queries)
    - [Lista](https://publish.obsidian.md/hub/04+-+Guides%2C+Workflows%2C+%26+Courses/Guides/An+Introduction+to+Dataview#List)
    - [A partir de](https://publish.obsidian.md/hub/04+-+Guides%2C+Workflows%2C+%26+Courses/Guides/An+Introduction+to+Dataview#From)
    - [Onde é o caso](https://publish.obsidian.md/hub/04+-+Guides%2C+Workflows%2C+%26+Courses/Guides/An+Introduction+to+Dataview#Where)
    - [Tarefa](https://publish.obsidian.md/hub/04+-+Guides%2C+Workflows%2C+%26+Courses/Guides/An+Introduction+to+Dataview#Task)
    - [Tabela](https://publish.obsidian.md/hub/04+-+Guides%2C+Workflows%2C+%26+Courses/Guides/An+Introduction+to+Dataview#Table)
    - [Ordenar](https://publish.obsidian.md/hub/04+-+Guides%2C+Workflows%2C+%26+Courses/Guides/An+Introduction+to+Dataview#Sort)
    - [Aplainudida](https://publish.obsidian.md/hub/04+-+Guides%2C+Workflows%2C+%26+Courses/Guides/An+Introduction+to+Dataview#Flatten)
    - [Grupo por](https://publish.obsidian.md/hub/04+-+Guides%2C+Workflows%2C+%26+Courses/Guides/An+Introduction+to+Dataview#Group by)

## Introdução

[Dataview](https://publish.obsidian.md/hub/02+-+Community+Expansions/02.05+All+Community+Expansions/Plugins/dataview) é um plugin que permite consultar dados do seu cofre. A _documentação oficial_ que você pode usar para referência está disponível aqui:

[https://blacksmithgu.github.io/obsidian-dataview](https://blacksmithgu.github.io/obsidian-dataview)

## Metadados

### O que é isso?

Os metadados fornecem informações _sobre_ seus dados.  
É uma informação _extra_ que já é _inerente aos_ seus dados ou informações que você **adiciona manualmente**.

### Exemplos de metadados

#### Fotografias

- Data e hora ?
- Localização ?
- Pessoas ? ? ?

Minha imagem de exibição tem os seguintes _inherent_metadados inerentes:

![SkepticMystic Mandala dp](https://i.imgur.com/UrwAWzI.jpg)

![Image metadata](https://i.imgur.com/dWmowLU.png)

Mas também pode ser dada outras propriedades:

![Edit image metadata](https://i.imgur.com/YPT6Gzb.png)

#### Notas de Markdown

Também podemos adicionar metadados às **notas Markdown** usando um idioma chamado _YAML_.

- YAML é um**Estruturada**A maneira de adicionar_Arbitrário_metadados para um arquivo.

### Adicionando os metadados YAML

1. No **topo** da sua nota, adicione 3 traços `---`
2. Abaixo disso, você pode começar a adicionar pares de chave-valor no formulário `key: value`
3. Para terminar o bloco de metadados, feche-o com 3 traços novamente `---`- A . (í a , , , , , ínte , .

No exemplo da foto, isso seria o seguinte:

```yaml
---
dimensions: 1200x1200
bit depth: 24
title: "Mandala Display Picture"
rating: 5
---
```

#### Listas de YAML

Você pode adicionar mais de um `value`para cada um `key`usando _listas_.

Existem duas notações que você pode usar:

##### 1. Inline em linha

```yaml
foods: [apples, pears, oranges]
```

##### 2. Recuado

```yaml
foods:
  - apples
  - pears
  - oranges
```

**Observe o espaçamento!**

### Os tipos de metadados

Você pode encontrar essas informações na [página de referência Dataview](https://blacksmithgu.github.io/obsidian-dataview/#/README).

```yaml
number: 3.6
string: "Foo all the bars"
list:
  - 1
  - -2
  - 3.5
  - 1.61803

date:
  - 2021-04
  - "2021-04-09"
  - 2021-04-09T12:12:54

link: [[2021-04-09 Daily Note]]
```

### Metadados Implícitos em todas as notas

| Imóvel de Propriedade | Valor de um valor                                        | Tipo de tipo |
| --------------------- | -------------------------------------------------------- | ------------ |
| `file.name`           | **Título do** arquivo                                    | `string`     |
| `file.path`           | **Caminho** de arquivo completo                          | `string`     |
| `file.link`           | **Link** para o arquivo                                  | `link`       |
| `file.size`           | **Tamanho** (em bytes) do arquivo                        | `number`     |
| `file.ctime`          | Data em que o arquivo foi **criado**                     | `date`       |
| `file.mtime`          | Data em que o arquivo foi **modificado** pela última vez | `date`       |
| `file.day`            | A **data** contida no título da nota                     | `date`       |
| `file.tags`           | An `array`de todas as **tags** na nota.                  | `array`      |

As subtags são divididas por cada nível, então `#Tag/1/A`será armazenado no array como `[#Tag, #Tag/1, #Tag/1/A]`

## Perguntas de Dataview

### `List`

Cria uma _lista_ das notas especificadas

```dataview
list
from #Agenda/lembrete 
```

### `From`

Determina **onde** obter notas_from_.

#### A partir de ?Tag

Você pode obter todas as notas _de_ uma **tag especificada:**

```dataview
list
from #MOC
```

#### De "Pão do Solta"

Todas as notas de uma **pasta:**

```dataview
list
from "Pesquisa"
```

#### A partir de [[Links]]

E até todas as notas com links entrando _em_ uma nota:

```dataview
list
from [[Yoga MOC]]
```

Ou sair _de_ uma nota:

```dataview
list
from outgoing([[yoga MOC]])
```

- Essa sintaxe pode mudar em um próximo lançamento.

#### Combinando fontes

Você pode usar os 3 operadores lógicos básicos para criar mais complexos `from`consultas:

- `list from #A and #B`
- `list from "University" or "Work"`
- `list from -#Personal`
- `list from [[CSS]] and -#HTML`

#### Concatenação de cordas

Nos resultados de a `list`, você pode incluir campos de metadados unidos com strings

```dataview
list "File Path: " + file.path + " :)"
from #Limpeza
```

#### Listas de listas

A `list`também pode exibir sublistas recortada de metadados:

```dataview
list Autor
from #Biblioteca/livros/tudoério or #Biblioteca/livros/leidaatraçãoeopoderdopensamento 
```

### `Task`

`Task`Pesquisas para todas as caixas de seleção `- [ ]` em seu cofre.

Ele retorna uma lista de todas as tarefas, agrupadas por sua nota de pai

```dataview
task 
from #Agenda/Notadiária/2024-06/2024-06-29  
```

### `Where`

Depois de escolher _quais_ notas usar, você pode restringir ainda mais a lista usando um `where`Bloco.  
Isso permite usar os vários _operadores de comparação_ nos campos de metadados em suas anotações.

`>`,, , - `>=`,, , - `<`,, , - `<=`,, , - `=`,, , - `!=`

`where {condition}`

#### Exemplos de dados

- `where file.size > 1000`
    
- `where file.name != "2021-04-09 Daily Note"`
    
- `where file.mtime >= date(today) - dur(1 day)`
    
- `where !complete`
    

### `Table`

`Table`pode mostrar-lhe uma _tabela_ de vários campos de metadados ligados a cada nota.

`Table {field 1}, {field 2}, ...`

#### Exemplos de dados

```dataview
table intensity
from #JMS/Meta 
```


![Dataview table](https://i.imgur.com/OnEoP7J.png)

```dataview
table Título, Autor, Classificação
from #Biblioteca/livros/tudoério 
```

```dataview
table file.tags
from #Biblioteca/livros/tudoério 
```

### `Sort`

Você pode usar `sort`definir qual ordem deve listar os resultados, e quais `field`para ordenar por:

`sort field asc/desc`

Dê vários campos para decidir os laços

`sort field1 asc/desc, field2 asc/desc, ...`

### `Flatten`

Uso `flatten`listas de "unroll" em suas próprias linhas.

```dataview
table Título, Autor, Classificação 
from #Biblioteca/livros/tudoério OR #Biblioteca/livros/vidaliquida
```


versus

```dataview
table Título, Autor, Classificação 
from #Biblioteca/livros/tudoério OR #Biblioteca/livros/vidaliquida
flatten Autor
```


### `Group by`

`Group by`Vamos reunir resultados com base no valor de um campo.

Você pode agrupar:

- As tarefas por`completed`
- Jogos por`rating`
- As atribuições por`intensity`

Primeiro, reúna todas as atribuições:

`from #Uni/2021/Asg`

Em seguida, o grupo por `intensity`:

`group by intensity`

#### `rows`Objecto

Ao agrupar as notas, criamos um **novo objeto**.

Esta é uma **lista aninhada** de todas as atribuições agrupadas por intensidade.  
Algo como:

```js
[[A1, A2, A6], // Green 
[A3, A4], // Yellow
[A5, A7], // Red 
] 
```

Para acessar esta nova lista, usamos o `rows`O objeto.

- Obter o nome do arquivo de cada nota no array:`rows.file.name`
- Receba a data de vencimento de cada nota:`rows.dueDate`

```dataview
table intensity, rows.Status
from #Biblioteca/livros/tudoério OR #Biblioteca/livros/vidaliquida
group by file.name
```

#### Grupo por etiquetas

```dataview
table rows.file.tags, rows.file.link
from #Limpeza
group by file.tags
```

##### Limitações

Ele só considerará duas notas no mesmo grupo se tiverem **exatamente as mesmas tags**.

- Então, mesmo que duas notas tenham`#Note/Author`, se um tem uma etiqueta que o outro não faz, eles não serão agrupados.

## Funções

### `Contains()`

Usado para ver se:

- a`string` _Contém_uma substring
- a`list` _Contém_um valor

`where contains(file.name, "Daily Note")`  
`where contains(authors, "Robert Lamb")`

### `Length()`

Retorna o _comprimento_ de uma `string`ou a `list`

`where length(file.name) > 10`

### `Sum()`

Retorna a _soma_ dos números em um `list`

`where sum(minutesStudied) < 60`

### Muitas outras funções

Para mais informações sobre funções implementadas, vá para [a documentação oficial](https://blacksmithgu.github.io/obsidian-dataview/#/functions).

## Exemplos de Neat

As pessoas têm vindo com um monte de maneiras interessantes de alavancar o Dataview. Muitos foram compartilhados no Central [Dataview Snippet Showcase](https://forum.obsidian.md/t/dataview-plugin-snippet-showcase/13673) no Fórum Obsidian.

### Notas não marcadas

Por exemplo, encontrar todas as notas não marcadas no seu cofre é tão simples como:
```dataview
list 
where length(file.tags) = 0 
```


### Aniversários de A

Se você acompanhar ?Pessoas em notas separadas e adicionar seu aniversário como uma propriedade de dataview, você pode compilar uma lista de todos cujo aniversário é hoje assim:

```dataview
list from #People
where Dates.Birthday = "<% tp.date.now(format = "YYYY-MM-DD") %>"
```
## Como usar o  Dataview
- - -
  
O Dataview consiste em dois grandes blocos de construção: **Indexação de Dados** e **Consulta de Dados**.

Mais detalhes nas páginas de documentação vinculadas

As seções a seguir devem fornecer uma visão geral do que você pode fazer com o Dataview e como fazê-lo. Não deixe de visitar as páginas vinculadas para saber mais sobre cada parte.

### Indexação de Dados

O Dataview opera em metadados em seus arquivos Markdown. Ele não pode ler tudo em seu cofre, mas apenas dados específicos. Parte do seu conteúdo, como tags e marcadores (incluindo tarefas), estão [disponíveis automaticamente](https://blacksmithgu.github.io/obsidian-dataview/annotation/add-metadata/#implicit-fields) no Dataview. Você pode adicionar outros dados por meio de **campos**, seja em cima de seu arquivo [por YAML Frontmatter](https://blacksmithgu.github.io/obsidian-dataview/annotation/add-metadata/#frontmatter) ou no meio de seu conteúdo com [Campos Inline](https://blacksmithgu.github.io/obsidian-dataview/annotation/add-metadata/#inline-fields) por meio da sintaxe `keyvalue`. O Dataview _indexa_ esses dados para disponibilizá-los para sua consulta.

O Dataview indexa [certas informações](https://blacksmithgu.github.io/obsidian-dataview/annotation/add-metadata/#implicit-fields) como tags e itens de lista e os dados que você adiciona por meio de campos. Somente dados indexados estão disponíveis em uma consulta do Dataview!

Por exemplo, um arquivo pode ser parecido com isto:

```
---
author: "Edgar Allan Poe"
published: 1845
tags: poems---# The Raven

Once upon a midnight dreary, while I pondered, weak and weary,
Over many a quaint and curious volume of forgotten lore—

```

Ou assim:

```
#poems# The Raven

From [author:: Edgar Allan Poe], written in (published:: 1845)

Once upon a midnight dreary, while I pondered, weak and weary,
Over many a quaint and curious volume of forgotten lore—

```

Em termos de metadados indexados (ou o que você pode consultar), eles são idênticos e diferem apenas no estilo de anotação. A forma como você deseja [anotar seus metadados](https://blacksmithgu.github.io/obsidian-dataview/annotation/add-metadata/) depende de você e de sua preferência pessoal. Com este arquivo, você teria o **campo de metadados** `author` disponível e tudo o que o Dataview lhe fornece [automaticamente como campos implícitos](https://blacksmithgu.github.io/obsidian-dataview/annotation/metadata-pages/), como a tag ou o título da nota.

Os dados precisam ser indexados

No exemplo acima, você _não tem_ o próprio poema disponível no Dataview: é um parágrafo, não um campo de metadados e não é algo que o Dataview indexa automaticamente. Não faz parte do índice do Dataview, portanto, você não conseguirá consultá-lo

### Consulta de Dados

Você pode acessar **dados indexados** com a ajuda de **Consultas**.

Há **três maneiras diferentes** de escrever uma Consulta: com a ajuda da [Dataview Query Language](https://blacksmithgu.github.io/obsidian-dataview/queries/dql-js-inline/#dataview-query-language-dql), como uma [declaração inline](https://blacksmithgu.github.io/obsidian-dataview/queries/dql-js-inline#inline-dql) ou da forma mais flexível, mas mais complexa: como uma [Consulta JavaScript](https://blacksmithgu.github.io/obsidian-dataview/queries/dql-js-inline#dataview-js).

A **Dataview Query Language** (**DQL**) fornece um conjunto de ferramentas amplo e poderoso para consultar, exibir e operar seus dados. Uma [**consulta inline**](https://blacksmithgu.github.io/obsidian-dataview/queries/dql-js-inline#inline-dql) permite que você exiba exatamente um valor indexado em qualquer lugar da sua nota. Você também pode fazer cálculos dessa forma. Com **DQL** à disposição, você provavelmente conseguirá se virar sem nenhum JavaScript em sua jornada de dados.

Uma Consulta DQL consiste em várias partes:

- Exatamente um [**Tipo de Consulta**](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/) que determina como será a Saída da consulta
- Nenhuma ou uma [**declaração FROM**](https://blacksmithgu.github.io/obsidian-dataview/queries/data-commands#from) para escolher uma tag ou pasta específica (ou outra [fonte](https://blacksmithgu.github.io/obsidian-dataview/reference/sources/)) para analisar
- De nenhum a vários [**outros Comandos de Dados**](https://blacksmithgu.github.io/obsidian-dataview/queries/data-commands/) que ajudam a filtrar, agrupar e classificar a saída desejada

Por exemplo, uma Consulta pode se parecer com isto:

que lista todos os arquivos em seu cofre.

Tudo menos o Tipo de Consulta é opcional

A única coisa necessária para uma Consulta DQL válida é o Tipo de Consulta (e em [CALENDÁRIOS](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types#calendar-queries), um campo de data).

Uma Consulta mais restrita pode se parecer com isto:

````dataview
LIST
FROM "Biblioteca/Livros" 
WHERE Autor = "Carla Madeira"
````

que lista todos os arquivos em seu cofre que têm a tag `#poems` e um [campo](https://blacksmithgu.github.io/obsidian-dataview/annotation/add-metadata/) chamado `author` com o valor `Edgar Allan Poe`. Esta consulta encontraria nossa página de exemplo acima.

`LIST` é apenas um entre quatro [Tipos de Consulta](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/) que você pode usar. Por exemplo, com uma `TABLE`, podemos adicionar mais algumas informações à nossa saída:

```dataview
table file.inlinks AS "Menções"
FROM #Biblioteca/livros/leidaatraçãoeopoderdopensamento 
````


Isto lhe retornará um resultado como:

| Arquivo (3)    | Autor           | Publicado | Menções                                                    |
| -------------- | --------------- | --------- | ---------------------------------------------------------- |
| Os Sinos       | Edgar Allan Poe | 1849      |                                                            |
| O Novo Colosso | Emma Lazarus    | 1883      | - [Poemas Favoritos](app://obsidian.md/Poemas%20Favoritos) |
| O Corvo        | Edgar Allan Poe | 1845      | - [Poemas Favoritos](app://obsidian.md/Poemas%20Favoritos) |

Mas não é aí que acabam as capacidades do Dataview. Você também pode **operar em seus dados** com a ajuda de [**funções**](https://blacksmithgu.github.io/obsidian-dataview/reference/functions/). Lembre-se de que essas operações são feitas apenas dentro de sua consulta - seus **dados em seus arquivos permanecem inalterados**.

````dataview
TABLE Autor, date(now).year - Data_publicação AS "Age in Yrs", length(file.inlinks) AS "Counts of Mentions"
FROM #Biblioteca/livros
````


Retorna isto:

| Arquivo (3)    | Autor           | Age in Yrs | Count of Mentions |
| -------------- | --------------- | ---------- | ----------------- |
| Os Sinos       | Edgar Allan Poe | 173        | 0                 |
| O Novo Colosso | Emma Lazarus    | 139        | 1                 |
| O Corvo        | Edgar Allan Poe | 177        | 1                 |

Como você pode ver, o Dataview não só permite que você agregue seus dados de forma rápida e sempre atualizada, mas também pode ajudá-lo com operações para fornecer novos insights sobre seu conjunto de dados. Navegue pela documentação para descobrir mais sobre como interagir com seus dados.

Divirta-se explorando seu cofre de novas maneiras!

## Recursos e Ajuda

Esta documentação não é o único lugar que pode ajudá-lo em sua jornada de dados. Dê uma olhada em [Recursos e Suporte](https://blacksmithgu.github.io/obsidian-dataview/resources/resources-and-support/) para uma lista de páginas e vídeos úteis.[https://blacksmithgu.github.io/obsidian-dataview/#/functions](https://blacksmithgu.github.io/obsidian-dataview/#/functions)

🔎

# Mais dicas e informações dataview

# Consultas de Lista Básica[¶](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20List%20Queries/#basic-list-queries "Link permanente")

### Básico[¶](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20List%20Queries/#basic "Link permanente")

**Lista de páginas de uma pasta**

`LIST FROM "10 Example Data/games"`

**Lista de páginas de uma tag**

`LIST FROM #type/books` 

**Combine várias tags**

`LIST FROM #dvjs/el OR #dv/min` 

**Combine várias pastas**

`LIST FROM "10 Example Data/books" OR "10 Example Data/games"`

**Combine tags e pastas**

`LIST FROM "10 Example Data/games" AND #genre/action`  

**Liste todas as páginas**

Adicionar `dataview` para bloquear código

A saída disso é bastante longa. Se você quiser ver, adicione `dataview` para o bloco de código - como nos exemplos acima!  
Atenção: É preciso haver um **espaço** atrás `LIST` para ver os resultados!

`LIST` 

## Variantes[¶](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20List%20Queries/#variants "Link permanente")

### Lista de páginas de um determinado autor[¶](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20List%20Queries/#list-pages-from-a-certain-author "Link permanente")

`LIST FROM #type/books  WHERE author = "Conrad C"`

### Liste páginas e mostre um campo de meta dados[¶](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20List%20Queries/#list-pages-and-show-a-meta-data-field "Link permanente")

Apenas uma informação adicional

Para listas, você só pode adicionar **um** saída adicional. Para mais, você precisa usar um [mesa](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20Table%20Queries/) ou [crie uma saída personalizada](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/How%20to%20create%20custom%20outputs%20in%20queries/).

`LIST author FROM #type/books`

### Liste valores de meta dados em vez das páginas[¶](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20List%20Queries/#list-meta-data-values-instead-of-the-pages "Link permanente")

ou seja, liste os links de origem de suas receitas:

`LIST WITHOUT ID source FROM "10 Example Data/food" WHERE source`

### Elementos da lista de grupos[¶](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20List%20Queries/#group-list-elements "Link permanente")

![O que é #^new-id-after-grouping](https://s-blu.github.io/obsidian_dataview_example_vault/00%20Meta/Vault%20Infos/What%20is/#new-id-after-grouping)

`LIST rows.file.link FROM "10 Example Data/books" GROUP BY author`

### Classificar elementos da lista[¶](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20List%20Queries/#sort-list-elements "Link permanente")

`LIST author FROM "10 Example Data/books" SORT author`

Uso avançado

Quer ver exemplos mais avançados? Dirija-se ao [Visão geral do Tipo de Consulta](https://s-blu.github.io/obsidian_dataview_example_vault/30%20Dataview%20Resources/31%20Query%20Overviews/Queries%20by%20Type/#list) para ver todas as consultas LIST disponíveis no cofre!

[

AnteriorConsultas Inline Básicas



](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20Inline%20Queries/)[

PróximoConsultas Básicas de Tabela

](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20Table%20Queries/)

Feito com [Material para MkDocs](https://squidfunk.github.io/mkdocs-material/) [Privacidade](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20List%20Queries/00%20Meta/privacy/)

[Ir para o conteúdo](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20Table%20Queries/#basic-table-queries)

[![logotipo](https://s-blu.github.io/obsidian_dataview_example_vault/assets/logo.png)](https://s-blu.github.io/obsidian_dataview_example_vault/ "Exemplo de Vault Dataview")

Exemplo de Vault Dataview

Consultas Básicas de Tabela

 [GitHub

- 548
- 61](https://github.com/s-blu/obsidian_dataview_example_vault "Ir para o repositório")

Exemplo de Vault Dataview

- [Cofre de Exemplo Obsidiano para Consultas Dataview](https://s-blu.github.io/obsidian_dataview_example_vault/)
- [Índice de Tag](https://s-blu.github.io/obsidian_dataview_example_vault/tagindex/)
- 00 Meta
- 10 Exemplos de Dados
- 20 Consultas Dataview
    
    - [Adicione um NaNoWriMon ao seu cofre](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Add%20a%20NaNoWriMon%20to%20your%20vault/)
    - [Consultas Básicas de Calendário](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20Calendar%20Queries/)
    - [Consultas Inline Básicas](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20Inline%20Queries/)
    - [Consultas de Lista Básica](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20List%20Queries/)
    - [Consultas Básicas de Tabela](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20Table%20Queries/)
    - [Consultas Básicas de Tarefas](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20Task%20Queries/)
    - [Calcular a soma das horas de trabalho para um projeto](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Calculate%20Sum%20of%20working%20hours%20for%20a%20project/)
    - [Calcule durações e comprimentos de ciclo](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Calculate%20cycle%20lengths%20and%20durations/)
    - [Calcule a fase de vigília com acordar e ir para os horários de sono](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Calculate%20waking%20phase%20with%20wake%20up%20and%20go%20to%20sleep%20times/)
    - [Tarefas de código de cores baseadas em meta dados](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Colorcode%20tasks%20based%20on%20meta%20data/)
    - [Exibir imagens em uma tabela de visualização de dados](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Display%20images%20in%20a%20dataview%20table/)
    - [Exibir valores de meta dados como uma nuvem de tags](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Display%20meta%20data%20values%20as%20a%20tag%20cloud/)
    - [Exibir metadados de uma semana como emjois (rastreamento de hábito)](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Display%20metadata%20of%20a%20week%20as%20emjois%20%28habit%20tracking%29/)
    - [Exibir ou ocultar consultas de visualização de dados com base em uma seleção de tarefa](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Display%20or%20hide%20dataview%20queries%20based%20on%20a%20task%20selection/)
    - [Exibir imagens aleatórias de um caminho](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Display%20random%20images%20from%20a%20path/)
    - [Exemplo de consultas FLATTEN](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Example%20FLATTEN%20Queries/)
    - [Exemplo GROUP BY Queries](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Example%20GROUP%20BY%20Queries/)
    - [Visão geral do Frontmatter](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Frontmatter%20Overview/)
    - [Obter um link para o diário anterior (não necessariamente ontem)](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Get%20a%20link%20to%20the%20previous%20daily%20%28not%20necessarily%20yesterday%29/)
    - [Obtenha as tarefas abertas mais recentes](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Get%20latest%20open%20tasks/)
    - [Agrupar campos de meta dados duplicados após a ordem no arquivo](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Group%20duplicated%20meta%20data%20fields%20after%20their%20order%20in%20file/)
    - [Agrupar arquivos por meta dados](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Group%20files%20by%20meta%20data/)
    - [Lista de grupos de arquivos por metadados](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Group%20list%20of%20files%20by%20metadata/)
    - [Como criar saídas personalizadas em consultas](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/How%20to%20create%20custom%20outputs%20in%20queries/)
    - [Limite os meta dados a uma quantidade máxima](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Limit%20meta%20data%20to%20a%20maximal%20amount/)
    - [List all files with missing category tag or empty meta data field](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/List%20all%20files%20with%20missing%20category%20tag%20or%20empty%20meta%20data%20field/)
    - [List all list items containing a certain tag](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/List%20all%20list%20items%20containing%20a%20certain%20tag/)
    - [List all list items with a certain word](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/List%20all%20list%20items%20with%20a%20certain%20word/)
    - [List all meta data available in your vault](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/List%20all%20meta%20data%20available%20in%20your%20vault/)
    - [List all not referenced attachments](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/List%20all%20not%20referenced%20attachments/)
    - [List all open projects with a emoji age indicator](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/List%20all%20open%20projects%20with%20a%20emoji%20age%20indicator/)
    - [List all tasks with a custom status](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/List%20all%20tasks%20with%20a%20custom%20status/)
    - [List bullet points from dailies of a specific date without year](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/List%20bullet%20points%20from%20dailies%20of%20a%20specific%20date%20without%20year/)
    - [List contacts with a person](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/List%20contacts%20with%20a%20person/)
    - [List files or metadata starting with a certain letter](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/List%20files%20or%20metadata%20starting%20with%20a%20certain%20letter/)
    - [List most recent meta data value that contains a certain phrase](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/List%20most%20recent%20meta%20data%20value%20that%20contains%20a%20certain%20phrase/)
    - [List non existing, linked pages](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/List%20non%20existing%2C%20linked%20pages/)
    - [List pages that share a meta data value with the current page](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/List%20pages%20that%20share%20a%20meta%20data%20value%20with%20the%20current%20page/)
    - [List pages with due date and color those overdue](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/List%20pages%20with%20due%20date%20and%20color%20those%20overdue/)
    - [List tasks that are due today or a specific day](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/List%20tasks%20that%20are%20due%20today%20or%20a%20specific%20day/)
    - [List tasks under a heading](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/List%20tasks%20under%20a%20heading/)
    - [List the last contact with every person](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/List%20the%20last%20contact%20with%20every%20person/)
    - [Make a holiday planning with a bullet point list and the calendar view](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Make%20a%20holiday%20planning%20with%20a%20bullet%20point%20list%20and%20the%20calendar%20view/)
    - [Mark all days in a calendar where you spent a certain amount of money](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Mark%20all%20days%20in%20a%20calendar%20where%20you%20spent%20a%20certain%20amount%20of%20money/)
    - [Mark days that have unfinished todos](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Mark%20days%20that%20have%20unfinished%20todos/)
    - [Multivalue YAML Frontmatter Field](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Multivalue%20YAML%20Frontmatter%20Field/)
    - [Plot a Category Series DQL query](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Plot%20a%20Category-Series%20DQL%20query/)
    - [Plot a Series Category Value DQL Query](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Plot%20a%20Series-Category-Value%20DQL%20Query/)
    - [Query meta files to construct information out of a folder structure](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Query%20meta%20files%20to%20construct%20information%20out%20of%20a%20folder%20structure/)
    - [Remove a suffix from listed file names](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Remove%20a%20suffix%20from%20listed%20file%20names/)
    - [Render a progress bar](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Render%20a%20progress%20bar/)
    - [Render a year overview for your data](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Render%20a%20year%20overview%20for%20your%20data/)
    - [Render multiple tables with tab like buttons](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Render%20multiple%20tables%20with%20tab-like%20buttons/)
    - [Render song information and embed a video](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Render%20song%20information%20and%20embed%20a%20video/)
    - [Search for words in your files content across your vault](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Search%20for%20words%20in%20your%20files%20content%20across%20your%20vault/)
    - [Show a Goals Overview with progress bars for included projects and overall progress](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Show%20a%20Goals%20Overview%20with%20progress%20bars%20for%20included%20projects%20and%20overall%20progress/)
    - [Show a calendar with all days you've prayed](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Show%20a%20calendar%20with%20all%20days%20you%27ve%20prayed/)
    - [Show a meta data value for every day of the week](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Show%20a%20meta%20data%20value%20for%20every%20day%20of%20the%20week/)
    - [Show a sum row for numeric values and durations](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Show%20a%20sum%20row%20for%20numeric%20values%20and%20durations/)
    - [Show all birthdays for this month](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Show%20all%20birthdays%20for%20this%20month/)
    - [Show all list items containing a specific metadata value](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Show%20all%20list%20items%20containing%20a%20specific%20metadata%20value/)
    - [Show all list items under a specific heading with a metadata field](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Show%20all%20list%20items%20under%20a%20specific%20heading%20with%20a%20metadata%20field/)
    - [Show all list items under a specific heading](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Show%20all%20list%20items%20under%20a%20specific%20heading/)
    - [Show all list items with a certain word as a table](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Show%20all%20list%20items%20with%20a%20certain%20word%20as%20a%20table/)
    - [Show all photos of the week in a grid](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Show%20all%20photos%20of%20the%20week%20in%20a%20grid/)
    - [Mostrar uma linha média em tabelas para valores numéricos ou durações](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Show%20an%20average%20row%20on%20tables%20for%20numeric%20values%20or%20durations/)
    - [Mostrar itens de lista como tabela com seus metadados e seções](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Show%20list%20items%20as%20table%20with%20their%20metadata%20and%20sections/)
    - [Mostrar itens de lista contendo uma determinada tag](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Show%20list%20items%20containing%20a%20certain%20tag/)
    - [Mostrar datas de arquivo modificadas em uma exibição de calendário](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Show%20modified%20file%20dates%20in%20a%20calendar%20view/)
    - [Mostrar projetos concluídos em um mês ou ano específico](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Show%20projects%20finished%20in%20a%20specific%20month%20or%20year/)
    - [Mostrar dois campos de meta dados na mesma coluna da tabela](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Show%20two%20meta%20data%20fields%20in%20same%20table%20column/)
    - [Classificar uma tabela com uma ordem de classificação personalizada](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Sort%20a%20table%20with%20a%20custom%20sort%20order/)
    - [Estilo de colunas da tabela de visualização de dados](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Style%20dataview%20table%20columns/)
    - [Transformar dados meta de data para cálculos](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Transform%20date%20meta%20data%20for%20calculations/)
    - [Use nomes de arquivos diários como datas reais](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Use%20daily%20file%20names%20as%20real%20dates/)
    
- 30 Recursos do Dataview

Tabela de conteúdo

- [Básico](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20Table%20Queries/#basic)
- [Variantes](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20Table%20Queries/#variants)
    
    - [Mostrar páginas de um determinado autor](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20Table%20Queries/#show-pages-from-a-certain-author)
    - [Mostrar páginas e informações adicionais](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20Table%20Queries/#show-pages-and-additional-information)
    - [Mostrar apenas informações de meta dados e nenhum link de arquivo](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20Table%20Queries/#show-only-meta-data-information-and-no-file-link)
    - [Elementos da lista de grupos](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20Table%20Queries/#group-list-elements)
    - [Personalizar cabeçalhos de tabela](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20Table%20Queries/#customize-table-headers)
    - [Classificar tabelas](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20Table%20Queries/#sort-tables)
    

[dv/tabela](https://s-blu.github.io/obsidian_dataview_example_vault/tagindex/#dvtable) [dv/de](https://s-blu.github.io/obsidian_dataview_example_vault/tagindex/#dvfrom) [dv/onde](https://s-blu.github.io/obsidian_dataview_example_vault/tagindex/#dvwhere) [dv/classificação](https://s-blu.github.io/obsidian_dataview_example_vault/tagindex/#dvsort) [dv/groupby](https://s-blu.github.io/obsidian_dataview_example_vault/tagindex/#dvgroupby)

[](https://github.com/s-blu/obsidian_dataview_example_vault/tree/master/20%20Dataview%20Queries/Basic%20Table%20Queries.md "Edite esta página")

Mostrar sintaxe básica de consultas TABLE

# Consultas Básicas de Tabela[¶](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20Table%20Queries/#basic-table-queries "Link permanente")

## Básico[¶](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20Table%20Queries/#basic "Link permanente")

**Mostrar páginas de uma pasta como tabela**

`TABLE FROM "10 Example Data/games"`

**Mostrar páginas de uma tag como tabela**

`TABLE FROM #type/books` 

**Combine várias tags**

`TABLE FROM #dvjs/el OR #dv/min` 

**Combine várias pastas**

`TABLE FROM "10 Example Data/books" OR "10 Example Data/games"`

**Combine tags e pastas**

`TABLE FROM "10 Example Data/games" AND #genre/action`  

**Liste todas as páginas**

Adicionar `dataview` para bloquear código

A saída disso é bastante longa. Se você quiser ver, adicione `dataview` para o bloco de código - como nos exemplos acima!  
Atenção: É preciso haver um **espaço** atrás `TABLE` para ver os resultados!

`TABLE` 

## Variantes[¶](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20Table%20Queries/#variants "Link permanente")

### Mostrar páginas de um determinado autor[¶](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20Table%20Queries/#show-pages-from-a-certain-author "Link permanente")

`TABLE FROM #type/books  WHERE author = "Conrad C"`

### Mostrar páginas e informações adicionais[¶](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20Table%20Queries/#show-pages-and-additional-information "Link permanente")

`TABLE author, pagesRead, totalPages FROM #type/books`

### Mostrar apenas informações de meta dados e nenhum link de arquivo[¶](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20Table%20Queries/#show-only-meta-data-information-and-no-file-link "Link permanente")

`TABLE WITHOUT ID source, time, ingredients FROM "10 Example Data/food" WHERE source`

### Elementos da lista de grupos[¶](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20Table%20Queries/#group-list-elements "Link permanente")

![O que é #^new-id-after-grouping](https://s-blu.github.io/obsidian_dataview_example_vault/00%20Meta/Vault%20Infos/What%20is/#new-id-after-grouping)

**Sem colunas adicionais**

`TABLE  FROM "10 Example Data/books" GROUP BY author`

**Com colunas adicionais**

```dataview
TABLE rows.file.link, rows.Páginas 
FROM "Biblioteca/Livros" 
GROUP BY Autor
limit 5
```


### Personalizar cabeçalhos de tabela[¶](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20Table%20Queries/#customize-table-headers "Link permanente")

**De colunas adicionais**

`TABLE contacts.phone AS "Phone Number", contacts.mail AS "E-Mail" from "10 Example Data/people"`

**Do primeiro cabeçalho (link/group) sem agrupamento**

`TABLE WITHOUT ID file.link AS "Game", developer, price FROM "10 Example Data/games"`

**Do primeiro cabeçalho (link/group) com agrupamento**

`TABLE WITHOUT ID key AS "Author", rows.file.link AS "Books" FROM "10 Example Data/books" GROUP BY author`

### Classificar tabelas[¶](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20Table%20Queries/#sort-tables "Link permanente")

`TABLE author FROM "10 Example Data/books" SORT author`

Uso avançado

Quer ver exemplos mais avançados? Dirija-se ao [Visão geral do Tipo de Consulta](https://s-blu.github.io/obsidian_dataview_example_vault/30%20Dataview%20Resources/31%20Query%20Overviews/Queries%20by%20Type/#table) para ver todas as consultas TABLE disponíveis no cofre!

[

AnteriorConsultas de Lista Básica



](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20List%20Queries/)[

PróximoConsultas Básicas de Tarefas

](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20Task%20Queries/)

Feito com [Material para MkDocs](https://squidfunk.github.io/mkdocs-material/) [Privacidade](https://s-blu.github.io/obsidian_dataview_example_vault/20%20Dataview%20Queries/Basic%20Table%20Queries/00%20Meta/privacy/)

#### tarefas por cores

```// define pages
const pages = dv.pages('"10 Example Data/projects"')

// OPEN TASKS
const tasks = pages.file.tasks.where(t => t.priority && !t.completed)

// priorities color
const red = "<span style='border-left: 3px solid red;'>&nbsp;</span>"
const orange = "<span style='border-left: 3px solid orange;'>&nbsp;</span>"
const green = "<span style='border-left: 3px solid rgb(55 166 155);'>&nbsp;</span>"

// regex to remove the field priority in text
const regex = /\[priority[^\]]+\]/g

// assign colors according to priority
for (let task of tasks){
    task.visual = "";

    if (task.priority === "high") {
        task.visual = red
    } else if (task.priority === "medium") {
        task.visual = orange
    } else if (task.priority === "low") {
        task.visual = green
    }
    task.visual += task.text.replace(regex, "");
}

// render open tasks sorted after priority
const order = [ "low", "medium", "high"]
dv.taskList(tasks.sort((a, b) => order.indexOf(b.priority) - order.indexOf(a.priority)), false)
```


`= await dv.view("Biblioteca/Livros", {values: dv.pages('"Biblioteca/Livros"').where(p => p.Autor).Autor}) `
Mostrar hábitos como emoji

```dataview
TABLE choice(Francês, "💚", "➖") AS Francês, choice(Cíngulo, "💚", "➖") AS Cíngulo, choice(Treino, "💚", "➖") AS "Treino", choice(Ler, "💚", "➖") AS "Agradecer"
FROM "Agenda/Diário/2024"
WHERE date(file.day) = 2024-06-30
```

# pesquisar Status

```dataview
list without id length(rows) + " Metas com Status " + key
from "JMS" or "Biblioteca"
where contains(Subtipo, "Metas")
group by Status
```
#pesquisarstatus 