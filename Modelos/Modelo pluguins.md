---
Etiqueta: 📑
Categoria:
  - obsidian pluguins
Tipo: Anotação
Subtipo: Artigo
Pluguin: "{{name}}"
Função: 
Link: 
Ano: "{{date:YYYY}}"
tags:
  - Biblioteca
Gênero:
  - ""
Data: "{{date:YYYY/MM/DD}}"
Capa: https://images.spiceworks.com/wp-content/uploads/2022/12/26124808/Mobile-Apps.jpg
---
#Biblioteca/Pluguins/{{name}}
- - -
# {{Name}}


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