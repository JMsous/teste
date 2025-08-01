---
Etiqueta: ✔️
Categoria: 
Tipo: Anotação
Subtipo: Cursos
Curso: 
Status: 
Classificação: ✰✰✰✰✰
Ano: "{{date:YYYY}}"
tags:
  - Biblioteca/cursos
  - Biblioteca
Gênero:
  - ""
Título: "{{name}}"
Data: "{{date:YYYY/MM/DD}}"
Capa: https://www.shutterstock.com/image-photo/young-woman-learning-language-during-600nw-2200684015.jpg
---
#Biblioteca/cursos/{{name}} 
# {{name}}
- - -
# Detalhes 

xxxx

* [ ] Inscrição 
* [ ] Cronograma
# Resumo 
xxxxx

# Pontos principais - 
xxxx

# Aplicação 
xxxx

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