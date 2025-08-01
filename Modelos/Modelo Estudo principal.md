---
Etiqueta: ✔️
Categoria: 
Tipo: Anotação
Subtipo: Cronograma
Edital: 
Ano: "{{date:YYYY}}"
tags:
  - Concursos/edital
Gênero: ""
Título: "{{name}}"
Data: "{{date:YYYY/MM/DD}}"
---
#Concursos/Estudos/{{date:YYYY-MM-DD}}  

- - -
[[DV Estudos|Meus estudos 📖]] 
_ _ _
# Aulas do dia
_ _ _

> [!QUOTE] O que você estudou hoje?
> # Acompanhamento de Aulas
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
> # Reta Final CNU
> - [ ] [[Concursos/Editais/CNU/Revisão CNU estratégia|Revisão do estratégia]]
> - [ ] [[Concursos/Editais/CNU/Revisão Gran CNU|Revisão do gran]]
> - [ ] [[Concursos/Editais/CNU/Revisão IMP CNU|Revisão IMP]]
> - [ ] [[Biblioteca/PDF/BLOCO 07 - CNU - DICAS.pdf|Ebook Bloco 7]]
> - [ ] [](Biblioteca/PDF/BLOCO%2007%20-%20CNU%20-%20DICAS.pdf)xo-tematico-5-comunicacao-gestao-documental-transparencia-e-protecao-de-dados.pdf| Ebook Eixo 5]]
> - [ ] [[Memorex+CNU+(Bloco+07)+-+Rodada+01.pdf|Memorex I]]
> - [ ] [[Memorex+CNU+(Bloco+07)+-+Rodada+02.pdf|Memorex II]]
> - [ ] [[Memorex+CNU+(Bloco+07)+-+Rodada+03.pdf|Memorex 3]]
> - [ ] [[Memorex+CNU+(Bloco+07)+-+Rodada+04.pdf|Memorex 4]]
> - [ ] [[Memorex+CNU+(Bloco+07)+-+Rodada+05.pdf|Memorex 5]]
> - [ ] [[Memorex+CNU+(Bloco+07)+-+Rodada+06.pdf|Memorex 6]]

> 

# Leitura do dia
- - -

>[!QUOTE] Quais capítulos leu hoje?
> - [ ] Leitura 1
> - [ ] Leitura 2
> - [ ] Leitura 3
> - [ ] Leitura 4
> - [ ] Leitura 5


# Produtividade
<font color="#7f7f7f">(substituir today pela data da nota)</font>
- - -
```dataview
table file.ctime as Data, Tipo, Categoria, Etiqueta
from "Concursos"
where date(file.cday) = date(2024-05-17) and date(file.mday) = date(2024-05-17)
sort file.cday desc
```


_ _ _ 
# Anotações das aulas

_ _ _







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
