---
Etiqueta: ✔️
Categoria:
  - Agenda
Tipo: Planejamento
Subtipo: Anual
Data: "{{date:YYYY/MM/DD}}"
Ano: "{{date:YYYY}}"
tags:
  - Agenda/Planejamento/planejamentoanual
  - Agenda
Gênero:
  - ""
Capa: https://cdn4.vectorstock.com/i/1000x1000/43/33/feliz-ano-novo-happy-new-year-in-brazilian-vector-27834333.jpg
Capa_y: 0.292
---
#Agenda/Planejamento/planejamentoanual/{{date:YYYY-mm}} 

> [!QUOTE] Vá e Vença!
> 
 >Nunca foi sorte... sempre foi Deus!!
 pare de controlar! deixa fluir! confia em Deus!
 
_ _ _

# Objetivo Principal

> [!QUOTE] Qual seu maior objetivo para este ano
> 
 >Escreva aqui
# Metas

> [!QUOTE] Quais suas metas e indicadores para este ano?
> Escreva aqui
# Balanço anual

> [!QUOTE] O que aconteceu durante este ano 
> 
 >Escreva aqui
 
# Calendário de Hábitos

```dataview teste
table choice(Francês, "✅", "⛔") AS "🗼", choice(Cíngulo, "✅", "⛔") AS "🦋", choice(Treino, "✅", "⛔") AS "🏋️‍♀️", choice(Agradecer, "✅", "⛔") AS "😇", choice(Vibrações, "✅", "⛔") AS "🎧"
from "Agenda/Diário"
where contains(file.name, "{{date:YYYY}}")
sort file.ctime desc
```
# Relatório de Hábitos
- - -
### 🦋 Cíngulo
```dataview
list without id length(rows) + " Dias de Cíngulo com Status " + choice(Cíngulo, "✅", "⛔")
from "Agenda/Diário"
where contains(file.name, "{{date:YYYY}}")
group by Cíngulo
```
- - -
### 🗼Francês
```dataview
list without id length(rows) + " Dias de Francês com Status " + choice(Francês, "✅", "⛔")
from "Agenda/Diário"
where contains(file.name, "{{date:YYYY}}")
group by Francês
```
- - -
### 🎧Afirmações Positivas
```dataview
list without id length(rows) + " Dias de afirmações com Status " + choice(Vibrações, "✅", "⛔")
from "Agenda/Diário"
where contains(file.name, "{{date:YYYY}}")
group by Vibrações
```
- - -
### 😇Gratidão
```dataview
list without id length(rows) + " Dias de Agradecer com Status " + choice(Agradecer, "✅", "⛔")
from "Agenda/Diário"
where contains(file.name, "{{date:YYYY}}")
group by Agradecer
```
- - -
### 🏋️‍♀️Treino
```dataview
list without id length(rows) + " Dias de Treino com Status " + choice(Treino, "✅", "⛔")
from "Agenda/Diário"
where contains(file.name, "{{date:YYYY}}")
group by Treino
```

# Tarefas realizadas este ano 

> [!ckeck] Tarefas deste Ano
>```tasks
due this year by 2024


# Informações da Nota `= this.file.name`

>[!note]    
>📍Hoje é `= dateformat(date(now), "DD")`  
>Nota criada em: `= this.file.ctime`  
>Modificada em: `= this.file.mtime`
>Existe Desde: `= date(now) - this.file.ctime`
>

- - -
🔗 Mencionado em:
```dataview
list without id this.file.inlinks
GROUP BY this.filename
```
- - -
🔗Mencionou:
```dataview
list without id this.file.outlinks
group by this.filename
````
- - -
