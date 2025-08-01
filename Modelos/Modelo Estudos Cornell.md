---
Etiqueta: ✔️
Categoria:
  - Estudos
Tipo: Anotação
Subtipo:
  - ""
Área: 
Tópico: "{{name}}"
Subtópico: 
Ano: "{{date:YYYY}}"
tags:
  - Concursos
  - Concursos/estudos
Gênero:
  - ""
Título: "{{name}}"
Data: "{{date:YYYY/MM/DD}}"
---
#Concursos/estudos/{{date:YYYY-MM-DD}} 
#  {{Name}}

--- start-multi-column: ID_85wv
```column-settings
Number of Columns: 2
Largest Column: standart
```

> [!NOTE] # Tópicos
> 

Digite Aqui

--- column-break ---

> [!NOTE] ## Anotações

Digite aqui

--- end-multi-column

> [!QUOTE] # Resumo 
> Digite Aqui


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





