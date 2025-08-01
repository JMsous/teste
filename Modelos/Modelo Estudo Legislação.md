---
Etiqueta: ✔️
Categoria:
  - Concursos
Tipo:
  - Anotação
Subtipo: Legislação
Área: 
Legislação: "{{name}}"
Aplicação: 
Ano: "{{date:YYYY}}"
Link: 
tags:
  - Concursos
  - Concursos/Legislação
Gênero:
  - ""
Data: "{{date:YYYY/MM/DD}}"
---

#Concursos/Legislação/{{name}} 

# {{name}}

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