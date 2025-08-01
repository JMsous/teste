---
Etiqueta: ✔️
Categoria: Modelo
Tipo: Anotação
Subtipo: Sumário
Título: "{{name}}"
Ano: "{{date:YYYY}}"
tags:
  - jms
Gênero: ""
Data: "{{date:YYYY/MM/DD}}"
---
#Biblioteca/Sumário/{{name}}

_ _ _
# Complete com as informações e voilá!!
_ _ _

```dataview
list
from
where 
sort 
```


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