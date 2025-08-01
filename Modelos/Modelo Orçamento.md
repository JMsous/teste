---
Etiqueta: ✔️
Categoria: Finanças
Tipo: Orçamento
Subtipo: Despesas
Santander: 
Rico: 
Mercado Pago: 
Aluguel: 
Outras contas: 
A pagar: 
Ano: "{{date:YYYY}}"
tags:
  - Planejamento/orçamento2024
Gênero: ""
Título: "{{name}}"
Data: "{{date:YYYY/MM/DD}}"
---
  #Planejamento/orçamento2024 

# Controle
- - -

- [ ] Aluguel
- [ ] Rico
- [ ] Mercado Livre
- [ ] Santander
- [ ] Outras contas

# Relatório de despesas Mensais





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