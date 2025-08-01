---
Etiqueta: 📅
Categoria:
  - Agenda
Gênero:
  - ""
Tipo: Planejamento
Subtipo: Mensal
Renda: 
Santander: 
Rico: 
Mercado_Pago: 
Aluguel: 
Peso: 
Quadril: 
Cintura: 
Abdomên: 
Orçamento: 
Medida: 
Avaliar_Metas: 
Ano: "{{date:YYYY}}"
tags:
  - Agenda/Planejamento/planejamentomensal2024
  - Agenda
Metas: 
Anotações: 
Gratidão: "   "
Título: "{{name}}"
Data: "{{date:YYYY/MM/DD}}"
Capa: https://s1.static.brasilescola.uol.com.br/be/conteudo/images/ao-longo-um-ano-as-estacoes-ano-dividem-se-em-quatro-inverno-primavera-verao-outono-5c058fe7a7f13.jpg
Mês: "{{date:MMMM}}"
---
#Agenda/Planejamento/planejamentomensal/{{date:YYYY}}/{{date:YYYY-MM}}  
<!-- Criado em {{date:YYYY/MM/DD}} --> 
# Olá, Jerusa! Este é o seu mês 😊
- - -
🏋️‍♀️Tirar medidas `INPUT[toggle:Medidas]` 💰 Pagar as contas `INPUT[toggle:Orçamento]` 🎯Avaliar metas`INPUT[toggle:Avaliar_Metas]`  

> [!QUOTE] Vá e Vença!
> 
 >Nunca foi sorte... sempre foi Deus!!
 pare de controlar! deixa fluir! confia em Deus!
_ _ _

### Minhas Medidas

Peso     `INPUT[number:Peso]`
Peito    `INPUT[number:Peito]` 
Cintura `INPUT[number:Cintura]` 
Barriga `INPUT[number:Abdomên]` 
Quadril `INPUT[number:Quadril]` 

### Pagamentos

- [ ] Renda        `INPUT[number:Renda]`
- [ ] Santander  `INPUT[number:Santander]`
- [ ] Rico           `INPUT[number:Rico]` 
- [ ] Mpg          `INPUT[number:Mercado_pago]`
- [ ] Água/Luz  `INPUT[number:Água_luz]`
- [ ] Aluguel     `INPUT[number:Aluguel]`
# Metas
- - -

> [!QUOTE] Qual seu maior objetivo para este mês?
> ```meta-bind
INPUT[multiSelect(option(Estudo CNU/CNJ), option(Conseguir fonte de renda), option(Aprender françês), option(Cuidar saúde emocional), option(Ler mínimo 1 livro), option(Cuidar do relacionamento), option(Treino academia) ):Metas]
### Termômetro
<!--escala de ok 3 <🔴 6 <🟠 6>🟢-->

Hábitos 🪴 `INPUT[number:Nível_hábitos]`
Nutrição 🍽️`INPUT[number:Nível_nutrição]`
Estudos 🖊️ `INPUT[number:Nível_estudos]`
Limpeza🧹 `INPUT[number:Nível_limpeza]`
Diversão 💖`INPUT[number:Nível_limpeza]`
# Anotações

> [!QUOTE] Tem algo que gostaria de compartilhar?
> `INPUT[textArea:Gratidão]`

# Livros Lidos

```dataview
table Autor, Classificação, Status
from "Biblioteca/Livros"
where Ano = "{{date:YYYY}}"
where Mês = "{{date:MMMM}}"
where contains(Status, "🟢")
Sort file.ctime desc 
```

# Calendário de Hábitos

```dataview teste
table choice(Francês, "✅", "⛔") AS "🗼", choice(Cíngulo, "✅", "⛔") AS "🦋", choice(Treino, "✅", "⛔") AS "🏋️‍♀️", choice(Agradecer, "✅", "⛔") AS "😇", choice(Vibrações, "✅", "⛔") AS "🎧"
from "Agenda/Diário"
where contains(file.name, "{{date:YYYY-MM}}")
sort file.ctime desc
```
# Relatório de Hábitos
- - -
### 🦋 Cíngulo
```dataview
list without id length(rows) + " Dias de Cíngulo com Status " + choice(Cíngulo, "✅", "⛔")
from "Agenda/Diário"
where contains(file.name, "{{date:YYYY-MM}}")
group by Cíngulo
```
- - -
### 🗼Francês
```dataview
list without id length(rows) + " Dias de Francês com Status " + choice(Francês, "✅", "⛔")
from "Agenda/Diário"
where contains(file.name, "{{date:YYYY-MM}}")
group by Francês
```
- - -
### 🎧Afirmações Positivas
```dataview
list without id length(rows) + " Dias de afirmações com Status " + choice(Vibrações, "✅", "⛔")
from "Agenda/Diário"
where contains(file.name, "{{date:YYYY-MM}}")
group by Vibrações
```
- - -
### 😇Gratidão
```dataview
list without id length(rows) + " Dias de Agradecer com Status " + choice(Agradecer, "✅", "⛔")
from "Agenda/Diário"
where contains(file.name, "{{date:YYYY-MM}}")
group by Agradecer
```
- - -
### 🏋️‍♀️Treino
```dataview
list without id length(rows) + " Dias de Treino com Status " + choice(Treino, "✅", "⛔")
from "Agenda/Diário"
where contains(file.name, "{{date:YYYY-MM}}")
group by Treino
```
# Progresso concluídos
<font color="#7f7f7f">(Não se perca! a arte de ir até o fim)</font>
- - -
 ```dataview
list Subtipo + " em progresso " + Status
from ""
where Ano = "{{date:YYYY}}"
where Mês = "{{date:MMMM}}"
where contains(Status, "🟢")
Sort Subtipo desc
```
# Notas de estudos 
- - -
```dataview
table Edital, Status, file.cdate as Data
from "Estudos or Cursos"
where Ano = "{{date:YYYY}}"
where Mês = "{{date:MMMM}}"
sort file.ctime desc
```

# Produtividade 
<font color="#7f7f7f">(substituir dia pela data da nota)</font>
- - -
```dataview
list Subtipo + Categoria + Etiqueta
from ""
where Ano = "{{date:YYYY}}"
where Mês = "{{date:MMMM}}"
sort file.ctime desc
```

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
