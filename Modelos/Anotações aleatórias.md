---
Etiqueta: 💭
Categoria: 
Gênero: 
Tipo: Anotação
Subtipo: 
Título: "{{name}}"
Data: "{{date:YYYY/MM/DD}}"
Mês: "{{date:MMMM}}"
Ano: "{{date:YYYY}}"
Capa: https://i.imgur.com/NJKm7Za.jpeg
Capa_y: 0.21144
Link: 
tags:
  - MinhasNotas
---
#MinhasNotas/{{date:YYYY-MM}}{{name}} #{{date:YYYY-MM}}
# `= this.file.name`

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
