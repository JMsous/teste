---
Etiqueta: 📅
Categoria:
  - Agenda
Gênero:
  - ""
Tipo: Planejamento
Subtipo:
  - Diário
Leitura: 
Água: 
Ler: 
Devocional: 
Treino: false
Vibrações: 
Cíngulo: false
Francês: false
Agradecer: 
Gratidão: 
Data: "{{date:YYYY-MM-DD}}"
Mês: "{{date:MMMM}}"
Ano: "{{date:YYYY}}"
Capa_y: 0.364
Capa: "https://i.pinimg.com/originals/8b/4d/52/8b4d52b8c282637f902367965f366d5c.jpg"
tags:
  - Agenda/Notadiária
  - Agenda
---
>📍Hoje é `= dateformat(date(now), "DD")`  #Agenda/Notadiária/{{date:YYYY}}/{{date:MMMM}}/{{date:YYYY-MM-DD}}    
_ _ _
# ☕Bom dia, Jerusa!  

🏋️‍♀️ `INPUT[toggle:Treino]` 🦋 `INPUT[toggle:Cíngulo]` 📝 `INPUT[toggle:Devocional]` 🎧 `INPUT[toggle:Vibrações]` 🗼 `INPUT[toggle:Francês]` 😇 `INPUT[toggle:Agradecer]` 💧 `INPUT[suggester(option(😃), option(🙂), option(😐), option(🙁), option(😭)):Água]` 📖 `INPUT[suggester(option(😃), option(🙂), option(😐), option(🙁), option(😭)):Ler]` 

 ![](https://i.imgur.com/Burw3UE.png) 
 - - -
> [!QUOTE]  Para refletir antes de iniciar o dia
> 
 Nunca foi sorte... sempre foi Deus!!
 Nem tudo precisa ser com esforço algumas coisas podem flui com facilidade!
- - -
# Tarefas 
``` tasks
not done 
due {{date:YYYY-MM-DD}}
```
```tasks
not done
due before date(today)
```
# Anotações do dia
- - -

> [!QUOTE] Como foi o seu dia?
>
>?
# Diário de Gratidão
- - -

> [!QUOTE] O que você tem a agradecer hoje?
> `INPUT[textArea:Gratidão]`

# Acompanhamento
<font color="#7f7f7f">(Não se perca! a arte de ir até o fim)</font>
```dataview
list Subtipo + " em progresso " + Status
from "Biblioteca"
where contains(Status, "🟠")
Sort Subtipo desc
```

# Produtividade 
<font color="#7f7f7f">(substituir dia pela data da nota)</font>
```dataview
list Subtipo + Categoria + Etiqueta
from ""
where date(file.cday) = date({{date:YYYY-MM-DD}})
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
