---
Etiqueta: 📑
Categoria:
  - obsidian pluguins
Tipo: Anotação
Subtipo: Artigo
Pluguin: Dataview
Função: 
Link: 
Ano: "2024"
tags:
  - Biblioteca
Gênero:
  - ""
Data: 2024/06/28
Capa: https://images.spiceworks.com/wp-content/uploads/2022/12/26124808/Mobile-Apps.jpg
---
#Biblioteca/Pluguins/Dataview 

```dataview
list
where contains(file.name, "Dataview")
```

```dataview
list
where contains(file.name, "Página")
```

- - -
# Dataview

[Ir para o conteúdo](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#query-types)

[![logotipo](https://blacksmithgu.github.io/obsidian-dataview/assets/obsidian.png)](https://blacksmithgu.github.io/obsidian-dataview/ "Dataview")

Dataview

Tipos de Consulta

 [GitHub

- 0.5.67
- 6.5k
- 389](https://github.com/blacksmithgu/obsidian-dataview "Ir para o repositório")

Dataview

- [Visão geral](https://blacksmithgu.github.io/obsidian-dataview/)
- Metadados
    
    - [](https://blacksmithgu.github.io/obsidian-dataview/annotation/add-metadata/)
    - [](https://blacksmithgu.github.io/obsidian-dataview/annotation/types-of-metadata/)
    - [](https://blacksmithgu.github.io/obsidian-dataview/annotation/metadata-pages/)
    - [](https://blacksmithgu.github.io/obsidian-dataview/annotation/metadata-tasks/)
    
- [DQL, JS e Inlines](https://blacksmithgu.github.io/obsidian-dataview/queries/dql-js-inline/)
- Referência da Linguagem de Consulta
    
    - [Estrutura de uma Consulta](https://blacksmithgu.github.io/obsidian-dataview/queries/structure/)
    - [Tipos de Consulta](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/)
    - [Comandos de Dados](https://blacksmithgu.github.io/obsidian-dataview/queries/data-commands/)
    - [Diferenças para SQL](https://blacksmithgu.github.io/obsidian-dataview/queries/differences-to-sql/)
    - [Fontes](https://blacksmithgu.github.io/obsidian-dataview/reference/sources/)
    - [Expressões](https://blacksmithgu.github.io/obsidian-dataview/reference/expressions/)
    - [Literais](https://blacksmithgu.github.io/obsidian-dataview/reference/literals/)
    - [Funções](https://blacksmithgu.github.io/obsidian-dataview/reference/functions/)
    
- Referência JavaScript
    
    - [](https://blacksmithgu.github.io/obsidian-dataview/api/intro/)
    - [](https://blacksmithgu.github.io/obsidian-dataview/api/data-array/)
    - [](https://blacksmithgu.github.io/obsidian-dataview/api/code-reference/)
    - [](https://blacksmithgu.github.io/obsidian-dataview/api/code-examples/)
    
- FAQ e Recursos
    
    - [](https://blacksmithgu.github.io/obsidian-dataview/resources/faq/)
    - [](https://blacksmithgu.github.io/obsidian-dataview/resources/examples/)
    - [](https://blacksmithgu.github.io/obsidian-dataview/resources/develop-against-dataview/)
    - [](https://blacksmithgu.github.io/obsidian-dataview/resources/resources-and-support/)
    
- [Amigos de Dataview](https://blacksmithgu.github.io/obsidian-dataview/friends/)
- [Changelog](https://blacksmithgu.github.io/obsidian-dataview/changelog/)

Índice

- [LISTA](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#list)
    
    - [Saída de informações adicionais](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#output-an-additional-information)
    - [Agrupamento](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#grouping)
    - [LISTA SEM ID](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#list-without-id)
    
- [TABELA](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#table)
    
    - [Cabeçalhos de colunas personalizadas](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#custom-column-headers)
    - [TABELA SEM ID](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#table-without-id)
    
- [TAREFA](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#task)
    
    - [Tarefas para crianças](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#child-tasks)
    
- [CALENDÁRIO](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#calendar)

# Tipos de consulta

O **Tipo de consulta** determina como é a saída da sua consulta de dataview. É o **primeiro e único obrigatório** especificação que você fornece a uma consulta de dataview. Existem quatro disponíveis: `LIST`, `TABLE`, `TASK` e `CALENDAR`.

O Tipo de Consulta também determina qual **nível de informação** uma consulta é executada em. `LIST`, `TABLE` e `CALENDAR` operar em **nível da página** considerando `TASK` as consultas operam no `file.tasks` nível. Mais sobre isso no `TASK` Tipo de Consulta.

Você pode combinar **cada Tipo de Consulta com todos disponíveis [Comandos de Dados](https://blacksmithgu.github.io/obsidian-dataview/queries/data-commands/)** para refinar seu conjunto de resultados. Leia mais sobre a interconexão entre Tipos de Consulta e Comandos de Dados [Como usar o Dataview](https://blacksmithgu.github.io/obsidian-dataview/#how-to-use-dataview) e o [página de estrutura](https://blacksmithgu.github.io/obsidian-dataview/queries/structure/).

Tipo de Consulta

O Tipo de Consulta determina o formato de saída de uma consulta. É a única informação obrigatória para uma consulta.

## LISTA

`LIST` as consultas geram uma lista de marcadores que consiste nos links do arquivo ou no nome do grupo, se você decidir [grupo](https://blacksmithgu.github.io/obsidian-dataview/queries/data-commands/#group-by). Você pode especificar até **mais uma informação** para saída ao lado de suas informações de arquivo ou grupo.

Tipo de Consulta `LIST`

`LIST`exibe uma lista de marcadores de links de página ou chaves de grupo. Você pode especificar uma informação adicional para mostrar para cada resultado.

A consulta LIST mais simples gera uma lista de marcadores de todos os arquivos no seu cofre:

` ```dataview  LIST ``` `

**Saída**

- [Cheesecake Clássico](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)
- [Noções básicas de Git](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)
- [Como corrigir Git Cheatsheet](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)
- [Liga das Lendas](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)
- [Pilares da Eternidade 2](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)
- [Vale Stardew](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)
- [Painel](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)

mas você pode, é claro, usar [comandos de dados](https://blacksmithgu.github.io/obsidian-dataview/queries/data-commands/) para restringir quais páginas você deseja listar:

` ```dataview LIST  FROM #games/mobas OR #games/crpg ``` `

**Saída**

- [Liga das Lendas](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)
- [Pilares da Eternidade 2](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)

### Saída de uma informação adicional

Para adicionar um **informações adicionais** para sua consulta, especifique-a logo após o `LIST` comando e antes de comandos de dados possivelmente disponíveis:

` ```dataview  LIST file.folder ``` `

**Saída**

- [Cheesecake Clássico](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#): Cozimento/Receitas
- [Noções básicas de Git](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#): Codificação
- [Como corrigir Git Cheatsheet](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#): Codificação/Cheatsheets
- [Liga das Lendas](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#): Jogos
- [Pilares da Eternidade 2](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#): Jogos
- [Vale Stardew](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#): Jogos/acabados
- [Painel](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#):

Você só pode adicionar **um** informações adicionais, não múltiplas. Mas você pode **especifique um valor calculado** em vez de um campo de meta dados simples, que pode conter informações de vários campos:

` ```dataview  LIST "File Path: " + file.folder + " _(created: " + file.cday + ")_" FROM "Games" ``` `

**Saída**

- [Liga das Lendas](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#): Caminho do arquivo: Jogos _(criado: May 13, 2021)_
- [Pilares da Eternidade 2](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#): Caminho do arquivo: Jogos _(criado: Februrary 02, 2022)_
- [Vale Stardew](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#): Caminho do arquivo: Jogos/acabados _(criado: Abril 04, 2021)_

### Agrupamento

A **lista agrupada** mostra suas chaves de grupo e apenas as chaves de grupo, por padrão:

` ```dataview  LIST GROUP BY type ``` `

**Saída**

- jogo
- conhecimento
- moc
- receita
- resumo

Um caso de uso comum em agrupado `LIST` consultas é adicionar os links de arquivo para a saída, especificando-os como as informações adicionais:

` ```dataview  LIST rows.file.link GROUP BY type ``` `

- jogo:
    - [Vale Stardew](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)
    - [Liga das Lendas](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)
    - [Pilares da Eternidade 2](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)
- conhecimento:
    - [Noções básicas de Git](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)
- moc: moc:
    - [Painel](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)
- receita:
    - [Cheesecake Clássico](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)
- resumo:
    - [Como corrigir Git Cheatsheet](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)

### LISTA SEM ID

Se você não quiser que o nome do arquivo ou a chave de grupo sejam incluídos no modo de exibição de lista, você pode usar `LIST WITHOUT ID`. `LIST WITHOUT ID` funciona da mesma forma que `LIST`, mas não gera o link do arquivo ou o nome do grupo se você adicionar uma informação adicional.

` ```dataview LIST WITHOUT ID ``` `

**Saída**

- [Cheesecake Clássico](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)
- [Noções básicas de Git](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)
- [Como corrigir Git Cheatsheet](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)
- [Liga das Lendas](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)
- [Pilares da Eternidade 2](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)
- [Vale Stardew](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)
- [Painel](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)

É o mesmo que `LIST`, porque não contém informações adicionais!

` ```dataview LIST WITHOUT ID type ``` `

**Saída**

- moc
- receita
- resumo
- conhecimento
- jogo
- jogo
- jogo

`LIST WITHOUT ID`pode ser útil se você quiser produzir valores calculados, por exemplo.

` ```dataview LIST WITHOUT ID length(rows) + " pages of type " + key GROUP BY type ``` `

**Saída**

- 3 Páginas do tipo jogo
- 1 Páginas de conhecimento do tipo
- 1 Páginas do tipo moc
- 1 Páginas do tipo receita
- 1 Páginas do tipo resumo

## MESA

O `TABLE` tipos de consulta geram dados de página como uma exibição tabular. Você pode adicionar zero a vários campos de meta dados ao seu `TABLE` consulta adicionando-os como um **lista separada por vírgulas**. Você pode não apenas usar campos de meta dados simples como colunas, mas especificar **cálculos** também. Opcionalmente, você pode especificar um **cabeçalho da tabela** através do `AS <header>` sintaxe. Como todos os outros tipos de consulta, você pode refinar seu conjunto de resultados para sua consulta com [comandos de dados](https://blacksmithgu.github.io/obsidian-dataview/queries/data-commands/).

`TABLE`Tipo de Consulta

`TABLE` as consultas renderizam uma exibição tabular de qualquer número de valores ou cálculos de meta dados. É possível especificar cabeçalhos de coluna via `AS <header>`.

` ```dataview TABLE ``` `

**Saída**

|Arquivo (7)|
|---|
|[Cheesecake Clássico](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)|
|[Noções básicas de Git](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)|
|[Como corrigir Git Cheatsheet](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)|
|[Liga das Lendas](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)|
|[Pilares da Eternidade 2](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)|
|[Vale Stardew](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)|
|[Painel](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)|

Alterar o nome do cabeçalho da primeira coluna

Pode alterar o nome do cabeçalho da primeira coluna (por predefinição "Arquivo" ou "Grupo") através das Definições Dataview em Definições da Tabela -> Nome da Coluna Primária /Nome da Coluna do Grupo. Se você quiser alterar o nome apenas para um específico `TABLE` consulta, dá uma vista de olhos `TABLE WITHOUT ID`.

Desativar a contagem de resultados

A primeira coluna sempre mostra a contagem de resultados. Se você não quiser exibi-lo, você pode desativá-lo nas configurações do Dataview ("Contagem de resultados de exibição", disponível desde 0.5.52).

Claro, a `TABLE` é feito para especificar uma a várias informações adicionais:

` ```dataview TABLE started, file.folder, file.etags FROM #games ``` `

**Saída**

|Arquivo (3)|começou|ficheiro.pasta|arquivo.etags|
|---|---|---|---|
|[Liga das Lendas](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)|16 De maio de 2021|Jogos|#jogos/moba|
|[Pilares da Eternidade 2](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)|21 De abril de 2022|Jogos|- #jogos/crpg|
|[Vale Stardew](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)|Abril 04, 2021|Jogos/acabados|- #jogos/simulação|

Campos implícitos

Curioso sobre `file.folder` e `file.etags`? Saiba mais sobre [campos implícitos nas páginas](https://blacksmithgu.github.io/obsidian-dataview/annotation/metadata-pages/).

### Cabeçalhos de Coluna Personalizados

Você pode especificar **cabeçalhos personalizados** para suas colunas usando o `AS` sintaxe:

` ```dataview TABLE started, file.folder AS Path, file.etags AS "File Tags" FROM #games ``` `

**Saída**

|Arquivo (3)|começou|Caminho|Tags de Arquivo|
|---|---|---|---|
|[Liga das Lendas](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)|16 De maio de 2021|Jogos|#jogos/moba|
|[Pilares da Eternidade 2](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)|21 De abril de 2022|Jogos|- #jogos/crpg|
|[Vale Stardew](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)|Abril 04, 2021|Jogos/acabados|- #jogos/simulação|

Cabeçalhos personalizados com espaços

Se você quiser usar um cabeçalho personalizado com espaços, como `File Tags`, você precisa envolvê-lo em aspas duplas: `"File Tags"`.

Isso é especialmente útil quando você deseja usar **cálculos ou expressões como valores de coluna**:

` ```dataview TABLE  default(finished, date(today)) - started AS "Played for",  file.folder AS Path,  file.etags AS "File Tags" FROM #games ``` `

**Saída**

|Arquivo (3)|Jogado para|Caminho|Tags de Arquivo|
|---|---|---|---|
|[Liga das Lendas](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)|1 Anos, 6 meses, 1 semanas|Jogos|#jogos/moba|
|[Pilares da Eternidade 2](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)|7 Meses, 2 dias|Jogos|- #jogos/crpg|
|[Vale Stardew](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)|4 Meses, 3 semanas, 3 dias|Jogos/acabados|- #jogos/simulação|

Cálculos e expressões

Saiba mais sobre a capacidade de calcular expressões e cálculos em [expressões](https://blacksmithgu.github.io/obsidian-dataview/reference/expressions/) e [funções](https://blacksmithgu.github.io/obsidian-dataview/reference/functions/).

### TABELA SEM ID

Se você não quiser a primeira coluna ("Arquivo" ou "Grupo" por padrão), você pode usar `TABLE WITHOUT ID`. `TABLE WITHOUT ID` funciona da mesma forma que `TABLE`, mas ele não gera o link do arquivo ou o nome do grupo como uma primeira coluna se você adicionar informações adicionais.

Você pode usar isso se, por exemplo, gerar outro valor de identificação:

` ```dataview TABLE WITHOUT ID steamid, file.etags AS "File Tags" FROM #games ``` `

**Saída**

|vapor (3)|Tags de Arquivo|
|---|---|
|560130|- #jogos/crog|
|-|#jogos/moba|
|413150|- #jogos/simulação|

Além disso, você pode usar `TABLE WITHOUT ID` se você quiser **renomeie a primeira coluna para uma consulta específica**.

` ```dataview TABLE WITHOUT ID file.link AS "Game", file.etags AS "File Tags" FROM #games ``` `

**Saída**

|Jogo (3)|Tags de Arquivo|
|---|---|
|[Liga das Lendas](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)|#jogos/moba|
|[Pilares da Eternidade 2](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)|- #jogos/crpg|
|[Vale Stardew](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#)|- #jogos/simulação|

Renomear a primeira coluna em geral

If you want to rename the first column in all cases, change the name in Dataviews settings under Table Settings.

## TASK

The `TASK` Query outputs **an interactive list of all tasks in your vault** that match the given [data commands](https://blacksmithgu.github.io/obsidian-dataview/queries/data-commands/) (if any). `TASK` queries are special compared to the other Query Types because they do give back **Tasks as results and not pages**. This implies that all [data commands](https://blacksmithgu.github.io/obsidian-dataview/queries/data-commands/) operate on **Task level** and makes it possible to granularly filter your tasks i.e. for their status or meta data specified on the task itself.

Also, `TASK` Queries are the only possibility to **manipulate your files through DQL**. Normally, Dataview does not touch the content of your files; however, if you check a task through a dataview query, it'll get **checked in its original file, too**. In the Dataview Settings under "Task Settings", you can opt-in to automatically set a `completion` meta data field when checking a task in dataview. Mind though that this only works if you check the task inside a dataview block.

`TASK` Query Type

`TASK` queries render an interactive list of all tasks in your vault. `TASK` Queries are executed on **task level**, not page level, allowing for task-specific filtering. This is the only command in dataview that modifies your original files if interacted with.

``` dataview 
TASK
limit 10
sort file.ctime desc
```


**Output**

- [ ] Buy new shoes #shopping
- [ ] Mail Paul about training schedule
- [ ] Finish the math assignment
    - [x] Finish Paper 1 [due:: 2022-08-13]
    - [ ] Read again through chapter 3 [due:: 2022-09-01]
    - [x] Write a cheatsheet [due:: 2022-08-02]
    - [ ] Write a summary of chapter 1-4 [due:: 2022-09-12]
- [x] Hand in physics
- [ ] Get new pillows for mom #shopping
- [x] Buy some working pencils #shopping

You can use [data commands](https://blacksmithgu.github.io/obsidian-dataview/queries/data-commands/) like for all other Query Types. Data Commands are executed on task level, making [implicit fields on tasks](https://blacksmithgu.github.io/obsidian-dataview/annotation/metadata-tasks/) directly available.

` ```dataview TASK WHERE !completed AND contains(tags, "#shopping") ``` `

**Output**

- [ ] Buy new shoes #shopping
- [ ] Get new pillows for mom #shopping

A common use case for tasks is to **group tasks by their originating file**:

` ```dataview TASK WHERE !completed GROUP BY file.link ``` `

**Output**

[2022-07-30](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#) (1)

- [ ] Finish the math assignment
    - [ ] Read again through chapter 3 [due:: 2022-09-01]
    - [ ] Write a summary of chapter 1-4 [due:: 2022-09-12]

[2022-09-21](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#) (2)

- [ ] Buy new shoes #shopping
- [ ] Mail Paul about training schedule

[2022-09-27](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/#) (1)

- [ ] Get new pillows for mom #shopping

Counting tasks with subtask

Noticing the (1) on the header of `2022-07-30`? Child tasks belong to their parent task and are not counted separately. Also, they **behave differently** on filtering.

### Child Tasks

A task is considered a **child task** if it is **indented by a tab** and is below an unindented task.

- [ ] clean up the house
    - [ ] kitchen
    - [x] living room
    - [ ] Bedroom [urgent:: true]

Childs of a bullet point item

While indented tasks under a bulleted list item are, strictly speaking, also child tasks, Dataview will handle them like normal tasks in most cases.

Child Tasks **belong to their parent**. This means if you're querying for tasks, you'll get child tasks as part of their parent back.

` ```dataview TASK ``` `

**Output**

- [ ] clean up the house
    - [ ] kitchen
    - [x] living room
    - [ ] Bedroom [urgent:: true]
- [ ] Call the insurance about the car
- [x] Find out the transaction number

This specifically means that child task will be part of your result set **as long as the parent matches the query** - even if the child task itself doesn't.

` ```dataview TASK WHERE !completed ``` `

**Output**

- [ ] clean up the house
    - [ ] kitchen
    - [x] living room
    - [ ] Bedroom [urgent:: true]
- [ ] Call the insurance about the car

Here, `living room` does **not match** the query, but is included anyway, because its parent `clean up the house` does match.

Mind that you'll get individual children tasks back, if the child matches your predicate but the parent doesn't:

` ```dataview TASK WHERE urgent ``` `

**Output**

- [ ] Bedroom [urgent:: true]

## CALENDAR

The `CALENDAR` Query outputs a monthly based calendar where every result is depicted as a dot on it referring date. The `CALENDAR` is the only Query Type that requires an additional information. This additional information needs to be a [date](https://blacksmithgu.github.io/obsidian-dataview/annotation/types-of-metadata/#date) (or unset) on all queried pages.

`CALENDAR` Query Type

The `CALENDAR` Query Types renders a calendar view where every result is represented by a dot on the given meta data field date.

` ```dataview CALENDAR file.ctime ``` `

**Output**

![](https://blacksmithgu.github.io/obsidian-dataview/assets/calendar_query_type.png)

Embora seja possível usar `SORT` e `GROUP BY` em combinação com `CALENDAR`, é, tem **nenhum efeito**. Além disso, a consulta de calendário não é renderizada se o campo de meta dados fornecido contiver algo além de um válido [data](https://blacksmithgu.github.io/obsidian-dataview/annotation/types-of-metadata/#date) (mas o campo pode estar vazio). Para garantir que você esteja levando em consideração apenas páginas válidas, você pode filtrar por valores de meta dados válidos:

` ```dataview CALENDAR due WHERE typeof(due) = "date" ``` `

Feito com [Material para MkDocs](https://squidfunk.github.io/mkdocs-material/)