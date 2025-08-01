<%---%>
Categoria: "{{categories}}"
Etiqueta: 📕
Tipo: Anotação
Subtipo: Livros
Páginas:  "{{totalPage}}"
Autor:  "{{author}}"
Título:  "{{title}}"
Subtítulo: "{{subtitle}}"
Editora: "{{publisher}}"
Status: 🔴
Classificação:  ✰✰✰✰✰
Capa: "{{coverUrl}}"
Link: "{{URL}}"
Data: "{{date:YYYY/MM/DD}}"
Ano: "{{date:YYYY}}"
Mês: "{{date:MMMM}}"
tags: biblioteca/livros
Gênero: Leitura
isbn: "{{isbn13}}"
Publicação: "{{publishDate}}"
Capa_local: "{{localCoverImage}}"
<%---%>
#Biblioteca/livros/{{title}} #{{date:YYYY-MM}}
# `= this.file.name`
- - -

| Capa                        | Ficha                                                                                                                                                                                      |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| ![Capa\|100](coverSmallUrl) | <font color="#548dd4">Título:</font> {{title}}<br><font color="#548dd4">Autor:</font> {{author}}<br><font color="#548dd4">Páginas:</font> {{totalPage}}<br><font color="#548dd4">Editora:</font>  {{publisher}}<br><br> |

# Anotações
---
> [!QUOTE] ### 🧐 O que você achou?
>
> Digite aqui


# Resumo
---
> [!Note]+ ### A História é sobre o que?
> {{description}}


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
