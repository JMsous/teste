---
Etiqueta: ✔️
Categoria:
  - Estudos
Tipo:
  - Anotação
Subtipo: Cursos
Curso: "{{name}}"
Status: 
Início: 
Conclusão: 
Ano: "{{date:YYYY}}"
tags:
  - Concursos
Gênero: 
Data: "{{date:YYYY/MM/DD}}"
---
#Concursos/edital/{{title}}  <!-- Criado em {{date:YYYY/MM/DD}} --> 
# {{title}}
- - -
[[DV Estudos|Meus estudos 📖]] 
_ _ _
# Aulas do dia
_ _ _

> [!QUOTE] O que você estudou hoje?
> 
> - [ ] aula 1
> - [ ] aula 2
> - [ ] aula 3
> - [ ] aula 4
> - [ ] aula 5
> - [ ] aula 6
> - [ ] aula 7
> - [ ] aula 8
> - [ ] aula 9
> - [ ] aula 10

# Leitura do dia
- - -

>[!QUOTE] Quais capítulos leu hoje?
> - [ ] Leitura 1
> - [ ] Leitura 2
> - [ ] Leitura 3
> - [ ] Leitura 4
> - [ ] Leitura 5

_ _ _ 
# Anotações das aulas

_ _ _

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