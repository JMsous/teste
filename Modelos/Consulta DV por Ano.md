---
Etiqueta: 
Categoria: 
Tipo: Anotação
Subtipo:
  - Consulta Dataview
Título: Consulta por ano
Ano: 
Link: 
tags: 
Gênero: 
Data: ""
---
#MinhasNotas/ConsultaDV
# Relatório de Leituras 

```dataview
list without id length(rows) + " Livros com Status " + key
from "Biblioteca"
where contains(Subtipo, "Livros")
group by Status
```
#### livros lidos este Ano
- - -
``` dataview
table  Without ID file.link as Título, Autor, Classificação, Statu
from "Biblioteca/Livros"
where contains(Ano, "2024")
where contains(Status, "🟢")
Sort file.name asc
```

# Meus  Hábitos

```dataview teste
table choice(Francês, "✅", "⛔") AS "🗼", choice(Cíngulo, "✅", "⛔") AS "🦋", choice(Treino, "✅", "⛔") AS "🏋️‍♀️", choice(Agradecer, "✅", "⛔") AS "😇", choice(Vibrações, "✅", "⛔") AS "🎧", Água as "💧", Ler as 📖
from "Agenda/Diário"
where contains(file.name, "2024")
sort file.ctime desc
```
# Relatórios mensais
- - -
### medidas

```dataview
table Peso, Cintura, Quadril, Abdomên as Pança
from "Agenda/Mensal"
where contains(Ano,"2024")
sort files.name desc 
```
### Finanças

```dataview
table Santander as STD, Mercado_Pago as MPG, Rico, Santander + Rico + Mercado_Pago as "Total"
from "Agenda/Mensal"
where contains(Ano,"2024")
sort files.name desc 
```
# Produtividade do ano
- - -
## Calendário de Produção 
- - -
 ```dataview 
calendar file.ctime
where contains(Ano, "2024")
```
## Notas Produzidas este ano
- - -
```dataview
list WITHOUT ID length(rows) + " notas de " + key 
where contains(Ano, "2024")
group By Subtipo
Sort file.name asc 
```