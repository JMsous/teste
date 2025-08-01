---
Etiqueta: ✔️
Categoria:
  - Meta
Tipo: Anotação
Subtipo:
  - ""
Metas:
  - "{{name}}"
Status: 
Término: 
Ano: "{{date:YYYY}}"
tags:
  - JMS/Meta
Gênero:
  - ""
Título: "{{name}}"
Data: "{{date:YYYY/MM/DD}}"
---
#JMS/Meta/{{name}} 
- - -
# Como vou alcança esta meta?
- - -
- [ ] 

# Próxima meta
- - -
[exemplo](caminho)

- [ ]
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