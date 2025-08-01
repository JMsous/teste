---
Etiqueta: ✔️
Categoria:
  - Leitura
Tipo: Anotação
Subtipo:
  - ""
Classificação: ✰✰✰✰✰
Início: 
Conclusão: 
Status: 
Ano: "{{date:YYYY}}"
tags:
  - Biblioteca/livros
Gênero:
  - ""
Título: "{{name}}"
Data: "{{date:YYYY/MM/DD}}"
---
l
# Anotações
- - -
> [!QUOTE] # 🧐 O que você achou do livro?
> 
> Digite aqui 


# Resumo
- - -
> [!Note]+ Sobre o que é este livro?  
> {excerpt}  

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