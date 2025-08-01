---
Etiqueta: 💭
Categoria:
  - Lazer
Tipo:
  - Viagem
Subtipo:
  - Passeio rápido
Destino: "{{name}}"
Hospedagem: 
Meio de transporte: 
Data_partida: 
Data_chegada: 
Ano: "{{date:YYYY}}"
tags:
  - JMS/Viagens
  - Agenda
Gênero:
  - ""
Título: "{{name}}"
Data: "{{date:YYYY/MM/DD}}"
---
#JMS/Viagens/{{name}} 
# Roteiro da viagem
- - -
> [!NOTE] Quais locais você vai visitar e em qual dia?
> 
- [ ] x
- [ ] 
- [ ] 

# Anotações

> [!Quote] O que não pode esquecer de levar?
> - [ ] 
> - [ ] 
> - [ ] 
> - [ ] 
> - [ ] 
> - [ ] 

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