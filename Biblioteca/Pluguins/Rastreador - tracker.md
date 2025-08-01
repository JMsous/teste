---
Etiqueta: 📑
Categoria:
  - obsidian pluguins
  - gráficos
Tipo:
  - Anotação
Subtipo: Pluguins
Pluguin: Tracker
Função: criar gráficos
Link: https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Concepts.md
tags:
  - Biblioteca
Ano: "2024"
Gênero: 
Capa: https://images.spiceworks.com/wp-content/uploads/2022/12/26124808/Mobile-Apps.jpg
---
#Biblioteca/Pluguins/tracker
# Tutorial básico

## **Introdução**

O Obsidian Tracker é um plugin para o aplicativo de anotações Obsidian que permite rastrear e gerenciar tarefas, projetos e hábitos dentro do seu fluxo de trabalho de anotações. Ele fornece uma interface intuitiva e recursos poderosos para ajudá-lo a manter o controle de suas tarefas e atingir seus objetivos.

**Configuração**

1. **Instale o plugin:** Vá para o diretório de plugins do Obsidian e instale o plugin "Tracker".
2. **Crie uma nova pasta:** Crie uma nova pasta no seu cofre Obsidian para armazenar seus dados de rastreamento.
3. **Configure as configurações:** Vá para Configurações > Plugins e configure as configurações do Tracker de acordo com suas preferências.

**Uso**

**Criando Tarefas**

1. Crie um novo arquivo de anotação na pasta do Tracker.
2. No início da anotação, digite "## Tarefa" seguido do nome da tarefa.
3. Adicione os seguintes campos de metadados à anotação (opcional):
    - **Prazo:** "deadline: YYYY-MM-DD"
    - **Prioridade:** "priority: alta | média | baixa"
    - **Projeto:** "project: Nome do Projeto"
    - **Contexto:** "context: Local | Atividade | Pessoas"

**Rastreamento de Tarefas**

1. **Marque tarefas como concluídas:** Para marcar uma tarefa como concluída, adicione um "x" no início da linha da tarefa.
2. **Programe tarefas:** Para programar uma tarefa, adicione um símbolo de relógio "clock:" seguido da data e hora da programação no início da linha da tarefa.
3. **Rastreie o tempo gasto:** Use os comandos "start" e "stop" para rastrear o tempo gasto em uma tarefa. O plugin calculará automaticamente a duração total.

**Gerenciamento de Projetos**

1. **Crie projetos:** Crie um arquivo de anotação em sua pasta do Tracker para cada projeto.
2. **Organize tarefas por projeto:** Use o campo de metadados "project:" para atribuir tarefas a projetos específicos.
3. **Visualize o progresso do projeto:** O Tracker fornecerá uma visão geral do andamento de cada projeto, incluindo tarefas concluídas, em andamento e atrasadas.

**Rastreamento de Hábitos**

1. **Crie hábitos:** Crie um arquivo de anotação para cada hábito que deseja rastrear.
2. **Monitore sua frequência:** Use os comandos "log" e "skip" para registrar ou pular a conclusão do hábito.
3. **Analise seu progresso:** O Tracker fornecerá estatísticas e gráficos para ajudá-lo a analisar seu progresso e identificar áreas de melhoria.

**Recursos Adicionais**

- **Visualizações Kanban e de lista:** Altere a visualização de suas tarefas e hábitos como listas ou cartões Kanban para maior flexibilidade.
- **Agrupamentos:** Agrupe tarefas por prazo, prioridade, projeto ou contexto para facilitar a organização.
- **Pesquisas:** Pesquise rapidamente suas tarefas, projetos e hábitos usando palavras-chave e filtros.
- **Integração com outros plugins:** O Tracker se integra a outros plugins populares do Obsidian, como o Calendar e o Dataview.

**Exemplos de Aplicações**

- **Gerenciamento de tarefas:** Rastreie tarefas diárias, projetos de longo prazo e compromissos pessoais.
- **Gestão de Projetos:** Divida projetos grandes em tarefas menores, gerencie dependências e monitore o progresso.
- **Rastreamento de Hábitos:** Monitore hábitos saudáveis, como exercícios, alimentação ou leitura.
- **Planejamento de Tempo:** Rastreie o tempo gasto em diferentes tarefas e atividades para melhorar a eficiência.
- **Análise de Dados:** Analise o progresso das tarefas, identifique padrões e melhore seu fluxo de trabalho
# Conceitos

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Concepts.md#concepts)

Este plugin foi projetado para ler blocos de código em [Formato YAML](https://en.wikipedia.org/wiki/YAML). Os pares chave-valor nos blocos de código dizem ao plugin quais dados coletar e como representar o resultado.

[Aqui](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/InputParameters.md) são todos os parâmetros (pares chave-valor) definidos neste plugin. Eles são usados para coletar dados, avaliar alvos, pré-processamento de dados e renderização de saída.

### Coleta de Dados

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Concepts.md#collecting-data)

Fornecendo parâmetros `searchType` e `searchTarget` é o requisito mínimo para uma coleta de dados bem-sucedida. `searchType` pode ser `tag`, `frontmatter`, `wiki`, `dvField`, `table`, `fileMeta`, `task`, ou `text`. Então a cooresponding `searchTarget` deve ser fornecido de acordo com o tipo especificado.

### Avaliação do Alvo

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Concepts.md#target-evaluation)

Depende do `searchType` e o `searchTarget` você forneceu, a avaliação de um alvo seria diferente. Simplificando, você pode rastrear as ocorrências de um alvo ou o valor anexado/incorporado nele.

Para ver os detalhes sobre a avaliação de destino, verifique o documento [Avaliação do Alvo](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/TargetEvaluation.md).

### Saída de Renderização

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Concepts.md#rendering-output)

Atualmente, o rastreador de obsidiana fornece cinco tipos de saída de renderização: `line`, `bar`, `summary`, `bullet`, `month` e `pie`. Você tem que fornecer pelo menos um parâmetro de saída em um bloco de código.

Com tipo de saída definido para `line` ou `bar`, plugin Tracker irá gerar um gráfico personalizável. Esses gráficos são muito bons em ver a variação do número coletado nas notas.

Com o tipo de saída `summary`, um bloco de texto baseado no seu '**modelo**' parâmetro será criado. Você pode usar [expressões](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Expressions.md) como '{{sum()}}' ou '{{maxStreak()}}' no parâmetro modelo, para obter um resumo estatístico dos dados coletados.

Tipo de saída `bullet` cria um [gráfico de bala](https://en.wikipedia.org/wiki/Bullet_graph) e poderia servir como um indicador que mostra o status (nível, desempenho, progresso) de um conjunto de dados.

Tipo de saída `month` cria uma visualização de mês com datas circuladas que excedem o limite e faixas que mostram quanto tempo persistiu.

Tipo de saída `pie` cria um gráfico de pizza. O `data` o parâmetro deve ser aplicado para setores circulares que você deseja adicionar. Parâmetro `label` e `extLabel` são usados para exibir etiquetas e `dataName` é usado para os nomes diplay na legenda.

Descrição detalhada para todos os parâmetros dos tipos de saída pode ser encontrada [aqui](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/InputParameters.md).

# Comandos

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Commands.md#commands)

Para suavizar o processo de criação de rastreadores, o obsidian-tracker fornece três comandos (Haverá mais na versão futura), "Add Line Chart Tracker", "Add Bar Chart Tracker" e "Adicionar Rastreador de Resumo". Basta digitar Ctrl/Cmd+P para ativar a paleta de comandos e, em seguida, digitar "Tracker" para pesquisar esses comandos.

Depois que um comando for executado, um bloco de código será adicionado à próxima linha abaixo da posição do cursor para você. O bloco de código adicionado conterá as chaves usadas com mais frequência. Para ver a lista completa de parâmetros de entrada e descrição, verifique [este documento](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/InputParameters.md).

##   
Tabela de Casos de Uso

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/docs/Examples.md#table-of-use-cases)

Verifique onde (Localização) e o que (Alvo para Rastrear) é o seu alvo e encontre as configurações (Rastreador) que você precisa.

| Localização   | Alvo para Rastrear                                                                                                                                | Rastreador                                                                                                                                                                        | Obter (O)corrências/(V)alues |
| :------------ | :------------------------------------------------------------------------------------------------------------------------------------------------ | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :--------------------------: |
| conteúdo      | #meditação                                                                                                                                        | searchType: tag  <br>searchTarget: meditação                                                                                                                                      |              O               |
| frontmatter   | ---  <br>tags: meditação  <br>---                                                                                                                 | searchType: tag  <br>searchTarget: meditação                                                                                                                                      |              O               |
| conteúdo      | #peso: 60,5 kg                                                                                                                                    | searchType: tag  <br>searchTarget: peso                                                                                                                                           |              V               |
| conteúdo      | #finanças/banco1/transferência: 100USD                                                                                                            | searchType: tag  <br>searchTarget: finanças/banco1/transferência                                                                                                                  |              V               |
| conteúdo      | #finanças/banco1/transferência: 100USD  <br>#finanças/banco1/renda: 80USD  <br>#finanças/banco1/resultado:-120USD                                 | searchType: tag  <br>searchTarget: finanças/banco1                                                                                                                                |              V               |
| conteúdo      | #pressão sanguínea: 180/120                                                                                                                       | searchType: tag  <br>searchTarget: blood-pressure[0], blood-pressure[1]                                                                                                           |              V               |
| content       | dvTarget:: 20.5                                                                                                                                   | searchType: dvField  <br>searchTarget: dvTarget                                                                                                                                   |              V               |
| content       | dvTarget:: 20.5/30.5                                                                                                                              | searchType: dvField  <br>searchTarget: dvTarget[0], dvTarget[1]                                                                                                                   |              V               |
| content       | dvTarget:: 20.5, 30.5                                                                                                                             | searchType: dvField  <br>searchTarget: dvTarget[0], dvTarget[1]  <br>separator: 'comma'                                                                                           |              V               |
| frontmatter   | ---  <br>mood: 10  <br>---                                                                                                                        | searchType: frontmatter  <br>searchTarget: mood                                                                                                                                   |              V               |
| frontmatter   | ---  <br>bp: 184.4/118.8  <br>---                                                                                                                 | searchType: frontmatter  <br>searchTarget: bp[0], bp[1]                                                                                                                           |              V               |
| frontmatter   | ---  <br>bp: 184.4, 118.8  <br>---                                                                                                                | searchType: frontmatter  <br>searchTarget: bp[0], bp[1]  <br>separator: 'comma'                                                                                                   |              V               |
| frontmatter   | ---  <br>bp: [184.4, 118.8]  <br>---                                                                                                              | searchType: frontmatter  <br>searchTarget: bp[0], bp[1]                                                                                                                           |              V               |
| frontmatter   | ---  <br>entrada do relógio: 10:45  <br>clock-out: 20:51  <br>---                                                                                 | searchType: frontmatter  <br>searchTarget: clock-in, clock-out                                                                                                                    |              V               |
| conteúdo      | [[jornal]]                                                                                                                                        | searchType: wiki  <br>searchTarget: diário                                                                                                                                        |              O               |
| conteúdo      | ⭐                                                                                                                                                 | searchType: texto  <br>searchTarget: ⭐                                                                                                                                            |              O               |
| conteúdo      | amor                                                                                                                                              | searchType: texto  <br>searchTarget: amor                                                                                                                                         |              O               |
| conteúdo      | [e-mail: test@gmail.com](mailto:test@gmail.com)  <br>[e-mail: test@hotmail.com](mailto:test@hotmail.com)                                          | searchType: texto  <br>serchTarget: '.+\@.+\..+'                                                                                                                                  |              O               |
| conteúdo      | #levantamento de peso: 50                                                                                                                         | searchType: texto  <br>searchTarget: levantamento de peso: (?<value>[\-]?[0-9]+[\.][0-9]+\|[\-]?[0-9]+)'                                                                          |              V               |
| conteúdo      | Eu andei 10000 passos hoje.                                                                                                                       | searchType: text  <br>searchTarget: 'walked\s+(?<value>[0-9]+)\s+steps'                                                                                                           |              V               |
| content       | myvalues 1/2/3                                                                                                                                    | searchType: text  <br>searchTarget: 'myvalues\s+(?<value>[0-9]+)/([0-9]+)/([0-9]+), myvalues\s+([0-9]+)/(?<value>[0-9]+)/([0-9]+), myvalues\s+([0-9]+)/([0-9]+)/(?<value>[0-9]+)' |              V               |
| table content | { a table filled with dates and values }  <br>[example table](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/data/Tables.md) | searchType: table  <br>searchTarget: filePath[0][0], filePath[0][1]                                                                                                               |              V               |
| table content | { a table filled with dates and values }  <br>[example table](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/data/Tables.md) | searchType: table  <br>searchTarget: filePath[1][0], filePath[1][1][0], filePath[1][1][1]                                                                                         |              V               |
| file meta     | meta data from files  <br>(size, cDate, mDate, numWords, numChars, numSentences)                                                                  | searchType: fileMeta  <br>searchTarget: size                                                                                                                                      |              V               |
| content       | - [x] Say love  <br>- [ ] Say love                                                                                                                | searchType:task  <br>searchTarget: Say love                                                                                                                                       |              O               |
| content       | - [x] Say love                                                                                                                                    | searchType:task.done  <br>searchTarget: Say love                                                                                                                                  |              O               |
| content       | - [ ] Say love                                                                                                                                    | searchType: task.notdone  <br>searchTarget: Say love                                                                                                                              |              O               |
# exemplo rastreador finanças

searchType: tag
searchTarget: finance/bank1
folder: diary
accum: true
line:
    title: Bank1
    yAxisLabel: USD

``` tracker
searchType: tag
searchTarget:tarefas
folder: Agenda/Tarefas
startDate:2024-06-01
endDate:2024-06-23
summary:
    template: "Average value of tagName is {{average()}}"
    style: "color:white;"
```

```tracker
searchType: frontmatter
searchTarget: Santander
folder: Agenda/Mensal
accum: true
line:
    title: Santander
    yAxisLabel: USD
```




# Exemplo rastreador de hábitos

searchType: tag
searchTarget: exercise-pushup
folder: diary
endDate: 2021-01-31
line:
    title: PushUp
    yAxisLabel: Count
    lineColor: "#d65d0e"
    
searchType: tag
searchTarget: meditation
folder: diary
accum: true
penalty: -1
line:
    title: Meditation
    yAxisLabel: Count

### Log de trabalho

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/HabitTracker.md#work-log)

```
searchType: tag
searchTarget: work_log
folder: diary
accum: true
startDate: 2021-01-01
line:
    title: Work Log
    yAxisLabel: Count
    pointSize: 5
    pointColor: white
    pointBorderWidth: 2
    pointBorderColor: "#d65d0e"
```
# Rastreador de estrelas
searchType: text
searchTarget: ⭐
folder: diary
summary:
    template: "I have {{sum()}} stars in total."
    style: "font-size:20px;color:yellow;margin-left: 50px;margin-top:00px;"

``` tracker
searchType: text
searchTarget: 😃,🙂, 😐, 🙁, 😭 
folder: Agenda/Diário
summary:
    template: "Excelente {{sum()}}, Bom {{sum()}}, Regular {{sum()}}, Ruim {{sum()}}, Pessímo {{sum()}}."
    style: "font-size:20px;color:yellow;margin-left: 50px;margin-top:00px;"
```
# rastreador emoji

searchType: dvfield
searchTarget: Physical
folder: diary
startDate: 2023-06-04
endDate: 2023-06-11
textValueMap:
    😀: 5
    🙂: 4
    😐: 3
    🙁: 2
    😞: 1
datasetName: 🚹 Physical
line:
	lineColor: orange
	lineWidth: 3
	showLegend: true
	legendPosition: right

``` tracker
searchType: frontmatter
searchTarget: Água, Ler
folder: Agenda/Diário
startDate: 2024-06-01
endDate: 2024-06-23
textValueMap:
    😀: 5
    🙂: 4
    😐: 3
    🙁: 2
    😭: 1
datasetName: 💧água, 📖Ler
line:
	lineColor: green, yellow
	lineWidth: 3
	showLegend: true
	legendPosition: right

```

# Rastreador de período
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
startDate: 2021-01-01
endDate: 2021-01-03
summary:
    template: 'Maximum value: {{10 + 10::i}} <-- should be 20'


# Contas numéricas
# Expressão de Teste

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestExpression.md#test-expression)

Todos os exemplos aqui usando o tipo de saída `summary`. Para ver exemplos de `bullet` e `pie`, por favor, verifique [exemplos de bala](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestBullet.md) e [exemplos de pizza](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestPieChart.md).

## Operadores

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestExpression.md#operators)

### número e número

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestExpression.md#number-and-number)

número + número --> número

```
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
startDate: 2021-01-01
endDate: 2021-01-03
summary:
    template: 'Maximum value: {{10 + 10::i}} <-- should be 20'
```

### Conjunto de dados e número

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestExpression.md#dataset-and-number)

Conjunto de dados + número --> Conjunto de dados

```
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
startDate: 2021-01-01
endDate: 2021-01-03
summary:
    template: 'Maximum value: {{max() + 10::i}} <-- should be 48 + 10'
```

Conjunto de dados - número --> Conjunto de dados

```
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
startDate: 2021-01-01
endDate: 2021-01-03
summary:
    template: 'Maximum value: {{max() - 2::i}} <-- should be 48 - 2'
```

Conjunto de dados * número --> Conjunto de dados

```
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
startDate: 2021-01-01
endDate: 2021-01-03
summary:
    template: 'Maximum value: {{max() * 2::i}} <-- should be 48 * 2'
```

Conjunto de dados / número --> Conjunto de dados

```
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
startDate: 2021-01-01
endDate: 2021-01-03
summary:
    template: 'Maximum value: {{max() / 2::i}} <-- should be 48 / 2'
```

Conjunto de dados % number --> Conjunto de dados

```
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
startDate: 2021-01-01
endDate: 2021-01-03
summary:
    template: 'Maximum value: {{max() % 5::i}} <-- should be 48 % 5'
```

### Conjunto de dados e Conjunto de dados

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestExpression.md#dataset-and-dataset)

Dataset1 + Dataset2 --> Dataset ==> Dataset[i] = Dataset1[i] + Dataset2[i]

```
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
startDate: 2021-01-01
endDate: 2021-01-03
summary:
    template: 'Maximum value: {{max(dataset(0) + dataset(0))::i}} <-- should be 48 + 48'
```

## Funções

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestExpression.md#functions)

**Se o conjunto de dados de entrada estiver ausente, ele usará o primeiro conjunto de dados Y disponível encontrado.**

### Funções Aceitar Conjunto de Dados e Retornar um Valor

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestExpression.md#functions-accept-dataset-and-return-a-value)

min(Dataset): número

```
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
endDate: 2021-01-03
summary:
    template: 'Minimum value: {{min()::i}} <-- should be 12'
```

minDate(Dataset): Data

```
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
endDate: 2021-01-03
summary:
    template: 'Latest date of minimum value: {{minDate()}} <-- should be 2021-01-03'
```

max(Dataset): número

```
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
endDate: 2021-01-03
summary:
    template: 'Maximum value: {{max()::i}} <-- should be 48'
```

maxDate(Dataset): Data

```
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
endDate: 2021-01-03
summary:
    template: 'Latest date of maximum value: {{maxDate()}} <-- should be 2021-01-01'
```

startDate(Dataset): Data

```
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
endDate: 2021-01-03
summary:
    template: 'Start date: {{startDate()}} <-- should be 2021-01-01'
```

endDate(Dataset): Data

```
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
endDate: 2021-01-03
summary:
    template: 'End date: {{endDate()}} <-- should be 2021-01-03'
```

sum(Dataset): número

```
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-04
summary:
    template: 'Sum: {{sum()::i}} <-- should be 3'
```

numTargets(Dataset): número

```
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-04
summary:
    template: 'Number of targets: {{numTargets()::i}} <-- should be 3'
```

numDays(Dataset): número

```
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-04
summary:
    template: 'Number of days: {{numDays()::i}} <-- should be 4'
```

numDaysHavingData(Dataset): número

```
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-04
summary:
    template: 'Number of days having data: {{numDaysHavingData()::i}} <-- should be 3'
```

maxStreak(Dataset): numero

```
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-09
summary:
    template: 'Maximum streak: {{maxStreak()::i}} <-- should be 5'
```

maxStreakStart(Dataset): Data

```
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-09
summary:
    template: 'The start date of maximum streak: {{maxStreakStart()}} <-- should be 2021-01-02'
```

maxStreakEnd(Dataset): Data

```
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-09
summary:
    template: 'The end date of maximum streak: {{maxStreakEnd()}} <-- should be 2021-01-06'
```

maxBreaks(Dataset): número

```
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-09
summary:
    template: 'Maximum breaks: {{maxBreaks()::i}} <-- should be 2'
```

maxBreaksStart(Dataset): Data

```
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-09
summary:
    template: 'The start date of maximum breaks: {{maxBreaksStart()}} <-- should be 2021-01-07'
```

maxBreaksEnd(Dataset): Data

```
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-09
summary:
    template: 'The end date of maximum breaks: {{maxBreaksEnd()}} <-- should be 2021-01-08'
```

currentStreak(Dataset): number

```
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-24
summary:
    template: 'Latest streak: {{currentStreak()::i}} <-- should be 1'
```

currentStreakStart(Dataset): Data

```
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-24
summary:
    template: 'The start date of current streak: {{currentStreakStart()}} <-- should be 2021-01-24'
```

currentStreakEnd(Dataset): Data

```
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-24
summary:
    template: 'The end date of current streak: {{currentStreakEnd()}} <-- should be 2021-01-24'
```

currentBreaks(Dataset): número

```
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-22
summary:
    template: 'Current breaks: {{currentBreaks()::i}} <-- should be 1'
```

currentBreaksStart(Dataset): number

```
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-22
summary:
    template: 'The start date of current breaks: {{currentBreaksStart()}} <-- should be 2021-01-22'
```

currentBreaksEnd(Dataset): Data

```
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-22
summary:
    template: 'The end date of current breaks: {{currentBreaksEnd()}} <-- should be 2021-01-22'
```

average(Dataset): número (48+25+12)/3 = 28,33

```
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
endDate: 2021-01-03
summary:
    template: 'Average value: {{average()::.2f}} <-- should be 28.33'
```

median(Dataset): número

```
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
endDate: 2021-01-03
summary:
    template: 'Median value: {{median()::i}} <-- should be 25'
```

variância(Dataset): número [https://mathworld.wolfram.com/SampleVariance.html](https://mathworld.wolfram.com/SampleVariance.html)

```
searchType: dvField
searchTarget: dataviewTarget
folder: /diary
endDate: 2021-01-03
summary:
    template: 'Variance value: {{variance()::.2f}} <-- should be 332.33'
```

### Funções Aceitar Conjunto de Dados e Retornar um Conjunto de Dados

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestExpression.md#functions-accept-dataset-and-return-a-dataset)

normalize(Dataset): Conjunto de dados

```
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-04
summary:
    template: 'Set missing values to -1, do normalization then do summation: {{sum( normalize( setMissingValues(dataset(0), -1) ) )::i}} <-- should be 3'
```

setMissingValues(Dataset): Conjunto de dados

```
searchType: tag
searchTarget: meditation
folder: /diary
endDate: 2021-01-04
summary:
    template: 'Set missing values to -1 then do summation: {{sum( setMissingValues( dataset(0), -1 ) )::i}} <-- should be 2'
```

# Tamanho de arquivos
# Teste FileMeta

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestFileMeta.md#test-filemeta)

Acompanhe a variação de tamanho dos diários

```
searchType: fileMeta
searchTarget: size
folder: diary
endDate: 2021-01-31
line:
    title: File Size Variation
    yAxisLabel: Size
    yAxisUnit: bytes
```

Use datas criadas por arquivo (cDate) como valores x

```
searchType: fileMeta, dvField
searchTarget: cDate, dataviewTarget
xDataset: 0
folder: data
line:
    fillGap: true
```

Use datas modificadas por arquivo (mDate) como valores x

```
searchType: fileMeta, dvField
searchTarget: mDate, dataviewTarget
xDataset: 0
folder: data
line:
    fillGap: true
```

Por favor, verifique também os alvos de pesquisa em arquivos de marcação na pasta 'diário' e 'dados'.

# propriedades

# Teste Frontmatter

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestFrontmatter.md#test-frontmatter)

## Valores Profundos

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestFrontmatter.md#deep-values)

deepValue: muito: muito: muito: muito: muito: profundidade: 27,4

```
searchType: frontmatter
searchTarget: deepValue.very.very.very.very.very.deep
folder: diary
endDate: 2021-01-31
line:
    title: Deep Values
```

## Múltiplos Valores

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestFrontmatter.md#multiple-values)

pressão arterial: 184,4/118,8

```
searchType: frontmatter
searchTarget: bloodpressure[0], bloodpressure[1]
datasetName: systolic, diastolic
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: Blood Pressures
    yAxisLabel: BP
    yAxisUnit: mmHg
    lineColor: yellow, red
    showLegend: true
    legendPosition: bottom
```

## Várias Tags na Matéria Frontal

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestFrontmatter.md#multiple-tags-in-front-matter)

Extrair dados de uma tag de várias tags O separador padrão nas tags de matéria frontal é vírgula (,)

```
searchType: tag
searchTarget: work_log
folder: diary
accum: true
startDate: 2021-01-01
endDate: 2021-01-31
line:
    title: Work Log
    yAxisLabel: Count
    pointSize: 5
    pointColor: white
    pointBorderWidth: 2
    pointBorderColor: "#d65d0e"
```

Use os dados de duas tags O separador padrão nas tags de matéria frontal é vírgula (,)

```
searchType: tag
searchTarget: work_log, work_log2
folder: diary
datasetName: Work1, Work2
month:
    initMonth: 2021-01
```

Por favor, verifique também os alvos de pesquisa em arquivos de marcação em pasta 'diário'.

```
searchType: frontmatter, dvField
searchTarget: date, count
xDataset: 0
folder: "data"
bullet:
	title: Total Counts
	value: "{{sum()}}"
	range: 1,5,10,20
	rangeColor: darkRed, lightBlue, lightGreen, blue
	showMarker: true
	markerValue: 2
	markerColor: red
```

# Humor

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestTextValueMap.md#test-textvaluemap)

## Humor

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/TestTextValueMap.md#mood)

```
searchType: frontmatter
searchTarget: "mood"
folder: diary
endDate: 2021-01-31
textValueMap:
    😀: 5
    🙂: 4
    😐: 3
    🙁: 2
    😞: 1
line:
    title: "Mood"
    yAxisLabel: Mood
    lineColor: "#d65d0e"
    yAxisTickInterval: 1
    yAxisTickLabelFormat: i
    yMin: 0
```

# Rastreador Peso

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/WeightTracker.md#weight-tracker)

```
searchType: tag
searchTarget: weight
folder: diary
startDate: 2021-01-01
endDate: 2021-01-31
aspectRatio: 20:9
fitPanelWidth: 1
line:
    title: Weight Log
    yAxisLabel: Weight
    yAxisUnit: kg
    lineColor: yellow
```

## Resumo

[](https://github.com/pyrochlore/obsidian-tracker/blob/master/examples/WeightTracker.md#summary)

```
searchType: tag
searchTarget: weight
folder: diary
summary:
    template: "Minimum: {{min()}}kg\nMaximum: {{max()}}kg\nMedian: {{median()}}kg\nAverage: {{average()}}kg"
```

```
searchType: tag
searchTarget: weight
folder: diary
line:
    title: Weight Log
    yAxisLabel: Weight
    yAxisUnit: kg
    showPoint: false
    lineColor: "#b16286"
```

Por favor, verifique também os alvos de pesquisa em arquivos de marcação em pasta 'diário'.