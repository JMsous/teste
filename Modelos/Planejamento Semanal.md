---
Etiqueta: 📅
Categoria:
  - Agenda
Gênero:
  - ""
Tipo: Planejamento
Subtipo:
  - Semanal
Metas: []
Anotação: 
Título: "{{name}}"
Data: "{{date:YYYY/MM/DD}}"
Mês: "{{date:MMMM}}"
Ano: "{{date:YYYY}}"
Nível_limpeza: 
Nível_hábitos: 
Nível_estudos: 
Nível_nutrição: 
Capa: https://s1.static.brasilescola.uol.com.br/be/conteudo/images/ao-longo-um-ano-as-estacoes-ano-dividem-se-em-quatro-inverno-primavera-verao-outono-5c058fe7a7f13.jpg
tags:
  - "#Agenda"
  - "#Agenda/Planejamento/Semanal"
---
#Agenda/Planejamento/Semanal/{{date:YYYY}}/{{date:YYYY-WW}}  
<!-- Criado em {{date:YYYY/MM/DD}} --> 
# Olá, Jerusa! Esta é o sua Semana 😊
- - -
🏋️‍♀️Tirar medidas `INPUT[toggle:Medidas]` 💰 Pagar as contas `INPUT[toggle:Orçamento]` 🎯Avaliar metas`INPUT[toggle:Avaliar_Metas]`  

> [!QUOTE] Vá e Vença!
> 
### Cardápio Semanal

- [ ] Segunda  `INPUT[text:Cardápio_segunda]`
- [ ] Terça        `INPUT[text:Cardápio_terça]` 
- [ ] Quarta     `INPUT[text:Cardápio_quarta]`
- [ ] Quinta     `INPUT[text:Cardápio_quinta]` 
- [ ] Sexta       `INPUT[text:Cardápio_sexta]`
- [ ] Sábado    `INPUT[text:Cardápio_sabádo]`
- [ ] Domingo `INPUT[text:Cardápio_domingo]`
### Termômetro
<!--escala de ok 3 <🔴 6 <🟠 6>🟢-->

Hábitos 🪴 `INPUT[number:Nível_hábitos]`
Nutrição 🍽️`INPUT[number:Nível_nutrição]`
Estudos 🖊️ `INPUT[number:Nível_estudos]`
Limpeza🧹 `INPUT[number:Nível_limpeza]`
Diversão 💖`INPUT[number:Nível_limpeza]`

### Metas Semanais
- - -
> [!QUOTE] Qual seu maior objetivo para este mês?
> ```meta-bind
INPUT[multiSelect(option(Fachina geral), option(Concluir 14 lições Duolingo), option(Concluir 1 curso/filme/série), option(Ler 1 livro), option(fluir no amor), option(Treinar 6 dias) ):Metas]
### Compromissos Semanais
- - -
> [!ckeck] Tarefas desta semana
> ```meta-bind
INPUT[multiSelect(option(Lavar o cabelo), option(Esfoliar a pele), option(Sair com o love) ):Tarefas_semanais]  
#### Pré-Agendadas
```tasks
not done
due after today
due before in 1 week
```
#### Atrasadas
```tasks
not done
due before date(today)
```
### Anotações

> [!QUOTE] Tem algo que gostaria de compartilhar?
> `INPUT[textArea:Anotação]`

### Progresso concluído
<font color="#7f7f7f">(Não se perca! a arte de ir até o fim)</font>

```dataview
table without id ("![capaimg|45](" + Capa +")") as Capa, file.link as Título, Subtipo
from ""
where Ano = "{{date:YYYY}}"
where Mês = "{{date:MMMM}}"
where contains(Status, "🟢")
Sort file.ctime desc 
limit 7
```

### Calendário de Hábitos

```dataview teste
table choice(Francês, "✅", "⛔") AS "🗼", choice(Cíngulo, "✅", "⛔") AS "🦋", choice(Treino, "✅", "⛔") AS "🏋️‍♀️", choice(Agradecer, "✅", "⛔") AS "😇", choice(Vibrações, "✅", "⛔") AS "🎧"
from "Agenda/Diário"
where contains(file.name, "{{date:YYYY-MM}}")
sort file.ctime desc
limit 7
```

### Notas de estudos 
- - -
```dataview
table Edital, Status, file.cdate as Data
from "Estudos" or "Biblioteca/Cursos"
where Ano = "{{date:YYYY}}"
where Mês = "{{date:MMMM}}"
sort file.ctime desc
limit 7
```

### Produtividade 
<font color="#7f7f7f">(substituir dia pela data da nota)</font>
- - -
```dataview
list Subtipo + Categoria + Etiqueta
from ""
where Ano = "{{date:YYYY}}"
where Mês = "{{date:MMMM}}"
sort file.ctime desc
limit 7
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
