---
cssclasses:
  - cards
status:
  - Done
target: 
Capa: "https://i.imgur.com/GWPtMMG.jpeg"
banner_y: 0.34619
banner_x: 0.50867
banner_icon: 
banner_lock: true
---
# <center> Olá Jerusa </center>

> [!multi-column]
>
>
>> [!infobox|right|]
>> #### Meus hábitos
>![External Image](https://i0.wp.com/i.pinimg.com/originals/99/c6/ca/99c6cadb02d2174dfcbebe7f46bba09f.gif)
>>
>> ```dataview
table Francês as 🗼, Ler as 📖, Agradecer as 😇, Cíngulo as 🦋, Vibrações as 🎧, Treino as 🏋️‍♀️, Água as 💧, Ler as 🧐
from "Agenda/Diário/2024"
where contains(Mês-Ano, "Junho-2024")
sort file.ctime desc
Limit 8

>
>> [!infobox|left]
>> #### Agenda
>![External Image](https://data.whicdn.com/images/268732126/original.gif)
>>
>> Dia Mês Semana
>> 📆 `$= '[['+ moment().format("YYYY-MM-DD") +'|Hoje]]'`  - - - - - 📆 `$= '[['+ moment().format("YYYY-MM") +'|Este mês]]'` - - - - -  📆 `$= '[['+ moment().format("YYYY") +'|Este Ano]]'`
>> 
>>  
>>  
>> 
>>  <wbr> 
>
>> [!infobox|left]
>> #### OTHERS
>![External Image](https://i.gifer.com/ZMZJ.gif)
>>
>> | |
>> |---|


>- **Meu Obsidian** 
> ![External Image|center|440](https://raw.githubusercontent.com/D3Ext/aesthetic-wallpapers/main/images/van.png)
> **[[00. Obsidian\|Obsidian]] — #obsidian**  <br> 
> **[[Agenda\|Agenda]] — #Agenda**   
><br>**[[DB Biblioteca\|Biblioteca]] — #Biblioteca**  <br>
>  <br>**[[Tarefas\|Tarefas]] — #tarefas** <br>
>  
>- **Personal**
> ![External Image|center|440](https://raw.githubusercontent.com/D3Ext/aesthetic-wallpapers/main/images/pink-mecha.png)
>**[[40. Projects\|Biblioteca]] — #projects**  <br> **[[Diário\|Diário]] — #Agenda/Notadiária** 
>
>- **Outros**
> ![External Image|center|440](https://raw.githubusercontent.com/D3Ext/aesthetic-wallpapers/main/images/wallhaven-28rjj6.png)
>**[[Saúde\|Saúde]] — #saude**  <br> **[[Trabalho\|Trabalho]] — #Trabalho/Enani**  
>



>[!multi-column|right|2]
>
>> [!danger] Meu mês
>> # Relatório de Hábitos
Treino🏋️‍♀️ -  Estudo📖 - Cíngulo🦋 - Afirmações🎧 - Francês🗼- Gratidão😇
- - -
```tracker
searchType: frontmatter
searchTarget: Treino, Estudo, Cíngulo, Vibrações, Francês, Agradecer
folder: Agenda/Diário/2024
datasetName: Treino, Estudo, Cíngulo, Afirmações, Francês, Gratidão
startDate: 2024-06-01
endDate: 2024-06-30
month:
	mode: annotation
	annotation: 🏋️‍♀️, 📖, 🦋, 🎧, 🗼, 😇 
	color: red
``` 

- - -

>
>> [!important]+ Importantes
>> ![[Countdown]]

---

## 🗓️ Produtividade do Mês
- - -
```dataview 
 calendar file.ctime
 where contains(Mês-Ano, "06-2024")
 ```