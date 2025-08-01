---
Etiqueta: 📅
Categoria:
  - Agenda
Tipo:
  - Anotação
Subtipo: Tarefa
Título: "{{name}}"
Local: 
Prioridade:
  - ⚫⚪🟤
Status: 
Conclusão: 
Data: "{{date:YYYY/MM/DD}}"
Ano: "{{date:YYYY}}"
tags:
  - Agenda
  - Agenda/Tarefas
Gênero:
  - ""
---
#Agenda/Tarefas/{{name}} 
# {{name}}
> [!QUOTE] **Compromissos**
> Digite seu aqui
> 

# Informações da Nota `= this.file.name`

>[!note]    
>📍Hoje é `= dateformat(date(now), "DD")`  
>Nota criada em: `= this.file.ctime`  
>Modificada em: `= this.file.mtime`
>Existe Desde: `= date(now) - this.file.ctime`

- - -
🔗 Mencionado em:
```dataview
list without id this.file.inlinks
group by this.filename
```
- - -
🔗Mencionou:
```dataview
list without id this.file.outlinks
group by this.filename 
````
- - -