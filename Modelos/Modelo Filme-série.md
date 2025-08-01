<%---%>
Etiqueta:  🎬
Categoria: 
Gênero:  "{{genres}}" 
Tipo: Anotação
Subtipo: Séries
Título: "{{title}}" 
Capa: "{{backdrop_path}}"
Idioma_original: "{{original_language}}" 
Popularidade: "{{popularity}}" 
Diretor: "{{director}}" 
Atores: "{{main_actors}}" 
Produtora: "{{production_companies}}" 
País_origem: "{{production_countries}}" 
Temporadas: 
Trailer: "{{youtube_url}}" 
Classificação: ✰✰✰✰✰
Status: 
Início: 
Conclusão: 
Mês: "{{date:MMMM}}"
Ano: "{{date:YYYY}}"
Lançamento: "{{release_date}}" 
Data: "{{date:YYYY/MM/DD}}"
tags: Biblioteca/Filmes
<%---%>

 tags: #Biblioteca/filmes/{{title}}

#  📺  `= this.file.name`

| Capa                          | Ficha                                                                                                                                                                                                                                                                             |
| ----------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ![Capa\|100]({{poster_path}}) | <font color="#548dd4">Título:</font> {{title}}<br><font color="#548dd4">Pontuação:</font> {{vote_average}}<br><font color="#548dd4">Quantidade de Votos:</font> {{vote_count}}<br><font color="#548dd4">Temporadas:</font><br><font color="#548dd4">Plataforma:</font><br>[Página Oficial]({{homepage}})  <br> |

# Anotações
- - -
> [!QUOTE] ### 🧐 O que você achou?
> 
> Digite aqui 


# Resumo
- - -
> [!Note]+ ### A História é sobre o que?  
> {{overview}}

# Trailer
![Trailer]({{youtube_url}})

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