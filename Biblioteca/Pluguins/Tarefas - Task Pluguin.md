---
Etiqueta: ✔️
Categoria:
  - obsidian pluguins
Tipo: Anotação
Subtipo: Artigo
Pluguin: Task
Função: Criar e gerenciar tarefas
Link: https://publish.obsidian.md/tasks
Ano: "2024"
tags:
  - Biblioteca
Gênero:
  - Produtividade
Capa: "https://images.spiceworks.com/wp-content/uploads/2022/12/26124808/Mobile-Apps.jpg"
---
#Biblioteca/Pluguins

# Tutorial

## Melhor tutorial de tarefas que achei

# [Como gerenciar suas tarefas com o obsidian - delchibruce](https://delchibruce.com/como-gerenciar-suas-tarefas-com-o-obsidia.html)
Já fiz minhas listas de tarefas em papel. No final estavam sempre bagunçadas! Abandonei o papel e fui procurar programas que fizessem essa tarefa melhor. Existem centenas de programas e aplicativos para gestão de projetos, objetivos e tarefas por aí e muitos são excelentes, alguns são gratuitos e outros servem em qualquer sistema operacional. Testei vários e usei alguns por algum tempo, mas sempre voltava a indagar **como estou usando mais um aplicativo ao invés de centralizar tudo possível em um só lugar**.

Como sabem, sou apaixonado pelo [zerttlekasten](https://delchibruce.com/o-metodo-zettelkasten.html) e pelo [obsidian](https://delchibruce.com/aprender-a-usar-o-obsidian-e-seja-mestre-do-zettelkasten.html) e como eu o utilizo para anotar, escrever e organizar, achei que seria interessante tentar gerenciar minhas tarefas com ele também.

Dentre as funções básicas do obsidian estão a criação de tarefas, utilizando a marcação `- [ ]` antes de um item, criando um item clicável, como diversas outras ferramentas de gestão de tarefas, mas é possível expandir as funções básicas com o uso de plugins que facilitam o fluxo, a organização e a visualização das informações.

Então, este post mostra o que eu fiz para **as minhas tarefas**, seguindo uma lógica que faz sentido para mim, mas pode ser que funcione para você também.

Vamos começar com os pré-requisitos:

Plugins necessários
----------

Para começar é necessário instalar e habilitar quatro plugins da comunidade, os chamados “não-oficiais”. São eles:

* **Dataview**, da comunidade, é um dos melhores plugins do obsidian, serve para visualização de dados;
* **Quickadd**, também da comunidade, facilita muito com atividades repetitivas;
* **Reminder**, para criar notificações e alarmes sobre as tarefas; e
* **Tasks**, para gerenciar as tarefas em si.

Esses são os plugins para criar o sistema que eu uso, mas é possível criar fluxos diferentes, utilizando outros, caso você ache melhor. Para começar, é necessário instalar e habilitar plugins da comunidade, os chamados “não-oficiais”. Para tanto, acesse a área de configurações, clicando na engrenagem do lado esquerdo, assim:

<img alt="acessar a área de configurações" src="https://delchibruce.com/media/posts/61/Pasted-image-20220817105321-3.png" height="282" width="216" />

Depois, desative o modo seguro, para permitir a instalação de plugins da comunidade. Atente que todos os plugins são verificados e possuem código aberto, mas há sempre algum risco na instalação desses itens.

<img alt="desligar o modo de segurança" src="https://delchibruce.com/media/posts/61/Pasted-image-20220817105523-2.png" height="277" width="1005" />

Clique no botão de “procurar” para acessar os plugins comunitários disponíveis:

<img alt="buscar plugins não oficiais" src="https://delchibruce.com/media/posts/61/Pasted-image-20220817105542.png" height="256" width="1022" />

E pesquise pelos quatro plugins comunitários que usaremos aqui: o dataview, o quickadd, o reminder e o tasks:

<img alt="buscando o plugin dataview" src="https://delchibruce.com/media/posts/61/Pasted-image-20220817105632-3.png" height="283" width="1005" />

Instale-os e depois habilite-os, na própria tela de plugins não oficiais.

<img alt="botão de habilitar o plugin" src="https://delchibruce.com/media/posts/61/Pasted-image-20220817105657.png" height="382" width="993" />

Repita esse passo para todos os plugins não oficiais que decidiu instalar.

Configurando os plugins
----------

Beleza! Com os plugins instalados e habilitados iremos configurá-los para passarmos para o uso propriamente dito do sistema de gerenciamento de tarefas.

Comece acessando a área de configurações do plugin `tasks` para alterar algumas das configurações padrão. Altere o `Global task filter` para `#tarefas`. Essa configuração permite que o obsidian diferencie tarefas de outras listas que você criou em seu cofre, ficando mais fácil organizá-las quando necessário. O padrão é `#task` e você pode mantê-lo, caso deseje, lembrando de fazer as alterações necessárias mais embaixo. Eu gosto de `#tarefas`, mas poderia ser `#todo`, `#dever`, `#afazeres`, ou qualquer outro nome que deseje. Em seguida, marque o `Remove global filter from description`, para ficar mais bonitinho.

Ficou assim:

<img alt="tela de configurações do plugin tasks" src="https://delchibruce.com/media/posts/61/Pasted-image-20220906105024-2.png" height="853" width="990" />

Depois, vamos configurar o `quickadd`, acessando a área de configuração de plugins não-oficiais e clicando no nome deste plugin.

Nosso objetivo aqui é criar uma ação rápida que faça as perguntas sobre os dados da tarefa, para que ela seja criada rapidamente e com todas as informações necessárias para ser útil. Nesse sentido, crie uma ação acessando a área de configurações do quickadd, escolhendo um novo nome e selecionando `capture`, depois clique em `add choice`.

<img alt="como adicionar ação ao quickadd" src="https://delchibruce.com/media/posts/61/Pasted-image-20220914143741-4.png" height="326" width="816" />

Isto criará uma nova ação rápida, chamada de `nova tarefa`. Clique na engrenagem dessa ação e faça duas alterações em suas configurações: a primeira é ligar o `task`, que permitirá que o item criado seja uma tarefa e o segundo é o `capture format`, que criará o modal de coleta de informações para acionar a ação `nova tarefa`. O `capture format` pode ser distinto, mas aqui está o meu, que cria uma tarefa com data de conclusão. Verifique se o `capture to active file` está ligado.

`#tarefas {{VALUE:nome da tarefa}} 📅 {{VDATE:data de vencimento,YYYY-MM-DD}}`

<img alt="editando nova tarefa do quickadd" src="https://delchibruce.com/media/posts/61/Pasted-image-20220914144737-2.png" height="540" width="651" />

Agora é só ligar o raiozinho, para que esta ação esteja disponível na paleta de comandos.

<img alt="adicionando ação à paleta de comando" src="https://delchibruce.com/media/posts/61/Pasted-image-20220914144527.png" height="108" width="792" />

Ao pressionar `ctrl+p` para chamar a paleta de comandos e escrever `nova tarefa` irá aparecer o modal para criação rápida. Olha como aparecerá na paleta:

<img alt="paleta de comando" src="https://delchibruce.com/media/posts/61/Screenshot_20220915_150245.png" height="256" width="566" />

E, ao clicar neste comando rápido, aparecerá o modal de inserção de tarefa, primeiro com a data de vencimento e, em seguida, a descrição da tarefa em si:

<img alt="modal de inserção de tarefa" src="https://delchibruce.com/media/posts/61/Screenshot_20220915_150415.png" height="181" width="675" />

Atente para o fato que a tarefa será criada na anotação que estiver aberta e em foco no momento da chamada do comando.

Por fim, vamos configurar o Reminder, o plugin que nos avisa quando chega a vez das tarefas agendadas. Você não precisa ser avisado do vencimento da tarefa? Então passe adiante!

Eu gosto de deixar as notificações para às 9:00, já que antes disso tenho minha rotina já estabelecida. Faça a marcação do `use system notification` se quiser usar as notificações do seu sistema operacional. Com o linux funciona muito bem e não vi nenhuma reclamação de não funcionar com o windows ou com o mac.

<img alt="configuração do plugin notification" src="https://delchibruce.com/media/posts/61/Pasted-image-20220914114506.png" height="293" width="803" />

O mais importante, no entanto, é fazer a alteração do formato para ser a mesma do plugin `tasks` que estamos usando:

<img alt="escolher o formato das datas no plugin notification" src="https://delchibruce.com/media/posts/61/Pasted-image-20220914114717.png" height="85" width="777" />

E, em seguida, faça as configurações específicas desse plugin:

<img alt="configurações específicas das tarefas no plugin notification" src="https://delchibruce.com/media/posts/61/Pasted-image-20220914141359.png" height="334" width="798" />

A única coisa que não curti das notificações é que os wikilinks não são clicáveis quando a opção de notificações do sistema estiver ligada. Nada de mais, mas você pode preferir usar as notificações do obsidian ao invés das do sistema operacional caso isso seja importante para você.

As tarefas em si
----------

Agora, com os plugins configurados, vamos criar uma tarefa em uma anotação. Digamos que você está estudando e identifique as próximas fases de seu estudo, como ler um novo capítulo, resolver questões de provas anteriores ou revisar o material estudado no ciclo anterior. Abra a paleta de comando usando `ctrl+p` e escolha a ação `Tasks: create or edit tasks` para chamar a caixinha de tarefas. Assim:

<img alt="paleta de comando chamando criação de tarefas" src="https://delchibruce.com/media/posts/61/Pasted-image-20220908110436.png" height="210" width="719" />

Ou chame o modal de criação rápida, que acabamos de criar ali em cima.

E, em seguida, selecionando esta opção:

<img alt="modal de criação de tarefas" src="https://delchibruce.com/media/posts/61/Pasted-image-20220908110512.png" height="642" width="575" />

É nessa tela que você criará suas tarefas, estabelecendo suas informações básicas. São elas:

* **Description**, ou descrição: a tarefa em si, como `ler o capítulo 32 do livro X` e por aí vai;
* **Priority**, ou prioridade: estabelecer a prioridade da tarefa, que pode ser Alta, Média ou baixa. As tarefas sem prioridades definidas serão posicionadas entre as médias e as baixas;
* **Recurrence**, ou recorrência: para tarefas que ocorrem de tempos em tempos, como `revisar material da aula passada` ou `pagar a conta de luz`;
* **Due**, ou vencimento: a data que a tarefa deve ser concluída ou entregue;
* **Scheduled** ou agendada: a data em que você quer fazer a tarefa. Deve ser anterior à data de vencimento;
* **Start** ou início: quando vai começar a trabalhar nessa tarefa. Geralmente significa que você precisa esperar algo acontecer para poder se dedicar a esta tarefa.

Vamos criar uma tarefa usando esta tela?

<img alt="modal de criação de tarefas" src="https://delchibruce.com/media/posts/61/Pasted-image-20220908112309.png" height="637" width="566" />

É possível, também, criar tarefas sem o uso da paleta de comando e da tela do plugin de tarefas, usando texto simples. Comece com o marcador de tarefa `- [ ]`, seguido pela tag que estabelecemos no `Global task filter`, ou `#tarefas`, descreva a tarefa e ao final aparecerá uma pequena ajuda para estabelecer as datas da tarefa. Olhe só:

<img alt="tarefas criadas usando somente texto" src="https://delchibruce.com/media/posts/61/Pasted-image-20220908112705.png" height="218" width="548" />

Criei mais algumas tarefas aqui, usando somente texto, sem o uso dos modais de criação de tarefas:

<img alt="muitas tarefas criadas" src="https://delchibruce.com/media/posts/61/Screenshot_20220915_145826.png" height="201" width="749" />

Atente para o fato de que terminei as duas primeiras tarefas e a primeira delas, a `[blog] escolher o tema do próximo post` é uma tarefa recorrente e voltou a ser criada com a data da próxima recorrência.

Os campos com datas aceitam o uso de linguagem natural, em inglês, o que significa que você pode escrever tm ou tomorrow para colocar a data de amanhã . Olhe a linguagem natural que pode ser utilizada:

|abreviação|por extenso|      significado      |
|----------|-----------|-----------------------|
|    td    |   today   |         hoje          |
|    tm    | tomorrow  |        amanhã         |
|    yd    | yesterday |         ontem         |
|    tw    | this week |      esta semana      |
|    nw    | next week |    próxima semana     |
|    we    |  weekend  |final de semana: sábado|

Enquanto os ícones também tem funções importantes aqui. Vamos ver o que significam:

|ícone|                                 significado                                 |
|-----|-----------------------------------------------------------------------------|
|  ⏫  |                               prioridade alta                               |
|  🔼  |                              prioridade média                               |
|  🔽  |                              prioridade baixa                               |
|  📅  |                        data de vencimento da tarefa                         |
|  🛫  |                          data de início da tarefa                           |
|  ⏳  |                        data do agendamento da tarefa                        |
|  ✅  |                     tarefa finalizada na data a seguir                      |
|  🔁  |recorrência: serve para estabelecer tarefas que acontecem de tempos em tempos|

É possível criar essas tarefas em qualquer anotação feita no obsidian, simplesmente começando com `- [ ]` e usando as opções de datas e prioridades. Além disso, é possível chamar a paleta de comando, usando `crtl+p` e procurar por `tasks`, ou ainda estabelecendo um atalho para essa função. Para estabelecer um atalho é só abrir a área de configurações e selecionar o `tasks` na aba de atalhos. Eu coloquei `crtl + alt + shift + t` para criar uma nova tarefa, mas isso é porque adoro atalhos do teclado. Você pode usar atalhos ou não.

<img alt="atalho para criação de tarefas" src="https://delchibruce.com/media/posts/61/Pasted-image-20220914101222.png" height="312" width="1032" />

A notificação de tarefas, quando ligadas, aparecerão assim:

<img alt="notificações do sistema operacional" src="https://delchibruce.com/media/posts/61/Screenshot_20220914_1420452.png" height="664" width="562" />

Na versão móvel do aplicativo a notificação de tarefas ficou assim:

<img alt="notificações na versão mobile" src="https://delchibruce.com/media/posts/61/Screenshot_20220916-0624462.png" height="812" width="1080" />

Uma vez que tudo está configurado, vamos ao sistema de gestão de tarefas em si.

Gestão de tarefas
----------

Eu crio tarefas em quase todas as anotações. Tarefas que precisam ser realizadas e tarefas que podem ser realizadas caso eu deseje caminhar com algum projeto específico.

>
>
> uma lista de tarefas é simplesmente uma coleção de coisas que devem ser feitas durante um dado período de tempo. É importante manter a lista atualizada e priorizada!
>
>

Como meu cofre foi crescendo, ficou bem difícil acompanhar as tarefas criadas, o que me fez usar outros aplicativos para manter o controle daquilo que precisava ser feito. Mas eu uso o obsidian todos os dias e como ele é bem ajustável aos fluxos particulares, pensei que deveria tentar manter as tarefas aqui dentro.

Para tanto, criei uma anotação chamada `tarefas` que fica alfinetada na minha tela e que tem sempre minhas tarefas organizadas. E esta anotação está sempre aberta, para que eu veja as próximas tarefas e possa interagir com cada uma delas.

Mas, antes de mostrar minha aba de tarefas, pense no que eu já disse lá em cima: tenho dois tipos de tarefas, sendo as que possuem data para conclusão e as que posso fazer a qualquer momento caso deseje ir por aquele caminho. Vamos chamá-las de tarefas `importantes` e tarefas `comuns`. Somente as tarefas que são importantes, e que possuem datas de início ou conclusão, são adicionadas usando o plugin de tarefas do obsidian. As demais são criadas apenas com um `- [ ]`, sem datas ou prioridades e, principalmente, sem o `#tarefas` que marca os itens criados pelo `Tasks`.

Por que disso? Porque nem todas as tarefas precisam ser feitas em momentos específicos ou não fazem parte de projetos e podem ser feitas a qualquer momento ou ainda, estão como lembretes para virarem projetos em algum momento. As tarefas marcadas com o `#tarefas`, ao ser concluída, ganha a data de conclusão, com o ícone do tick verdinho (✅), como essas abaixo:

<img alt="tarefas concluídas" src="https://delchibruce.com/media/posts/61/Pasted-image-20220914105028.png" height="54" width="688" />

As tarefas comuns não terão isso, certo? Ficarão assim:

<img alt="tarefa comum concluída" src="https://delchibruce.com/media/posts/61/Screenshot_20220915_152104.png" height="57" width="262" />

E o objetivo das `tarefas comuns` é me ajudar a criar melhores `tarefas importantes` no futuro. Servem para não esquecer de algo que pode ser muito importante caso algum projeto vá para frente. Ou são, simplesmente, parte da minha rotina.

A lista de tarefas
----------

Agora, finalmente, vamos criar a lista de tarefas. Primeiro, crie uma anotação chamada `Tarefas` e use o alfinete para que ela fique travada na tela. Dependendo do tema que você usa no obsidian é possível deixá-la fixada na barra direita da tela. Para fixá-la é só abrir a nota e usar o menu e escolher o alfinete:

<img alt="anotação com lista de tarefas" src="https://delchibruce.com/media/posts/61/Pasted-image-20220914110933.png" height="311" width="907" />

Depois é só arrumar o tamanho desejado do painel. Olhe a minha lista:

<img alt="lista de tarefas no obsidian" src="https://delchibruce.com/media/posts/61/Screenshot_20220916_155549.png" height="1057" width="900" />

Essa anotação precisa ter o seguinte código:

```
## Tarefas
### Para hoje
```tasks
not done
due today
```
### Para amanhã
```tasks
not done
due tomorrow
```
### Para esta semana
```tasks
not done
due after today
due before in 1 week
```

### Atrasadas
```tasks
not done
due before date(today)
```
### Sem data definida
```tasks
not done
no due date
limit 15
```

## Outras tarefas


```dataviewjs
dv.taskList(dv.pages('"Agenda/Tarefas/2024"').file.tasks
.where(t => !t.completed && !t.text.includes("@frank") &&
!t.text.includes("Mês: julho")
))
```
[[Tarefas Concluídas]]

Atente que o último fragmento dessa anotação possui um código do plugin `dataview` que serve para capturar todas as tarefas que não foram criadas utilizando o plugin `tasks` e, por isso, não possuem o `#tarefas` como marcador. Listará todas as demais tarefas disponíveis em seu cofre. Todas as milhares, caso você seja como eu!

Ao todo, depois de concluído, sua lista ficará assim:

<img alt="lista de tarefas" src="https://delchibruce.com/media/posts/61/Pasted-image-20220914111148.png" height="797" width="686" />

É possível incluir uma seção com as tarefas concluídas também. Eu prefiro ter as concluídas em uma outra lista, que chamo de `tarefas arquivadas`, com o seguinte código:

```
### Tarefas concluídas
```tasks
done
```



Que ficará assim:

<img alt="lista de tarefas concluídas" src="https://delchibruce.com/media/posts/61/Pasted-image-20220914111614.png" height="169" width="647" />

E é só isso! O obsidian é um aplicativo sinistramente útil, tem todas as minhas anotações, artigos, referências, livros e agora, tarefas. Um sistema super simples que me serve bem. Talvez sirva para você!

Se quiser baixar um cofre exemplo desse sistema é só pegar lá no [github](https://github.com/delchibruce/obsidian-tarefas).

E lembre-se de uma coisa: quando nós obtemos sucesso, mesmo o pequeno sucesso de marcar uma tarefa como concluída, nosso cérebro libera pequenas quantidades de dopamina.

>
>
> A dopamina é um neurotransmissor envolvido nas emoções, nos processos cognitivos, no devido funcionamento cardíaco, no aprendizado e no controle dos movimentos. Quando é liberada provoca a sensação de prazer e aumenta a motivação.
>
>

Quem não precisa de motivação?

Bom planejamento, boas tarefas e dopamine-se!

##  Criar ou editar Tarefa' Modal

### Introdução

![Criar ou Editar Modal](https://publish-01.obsidian.md/access/40e62a316a834ff6f495ebf1d122cae6/images/modal.png)

  
O `Tasks: Create or edit` o comando ajuda você a adicionar ou editar uma tarefa.

### Abrindo o Modal 'Criar ou editar Tarefa'

Use o comando 'Tarefas: Criar ou editar tarefa' para iniciar o modal.

- Se o cursor estiver em uma tarefa existente, o modal modificará as propriedades dessa tarefa.
- Se o cursor estiver em uma linha em branco, o modal criará uma nova tarefa nessa linha.

### Atalhos de teclado

Lançado

Introduzido nas Tarefas 1.17.0.

Todos os campos do formulário têm "chaves de acesso", ou seja, atalhos de teclado. As teclas de acesso são exibidas como as letras sublinhadas nos rótulos.

- No Windows, pressione o `Alt`chave e a letra sublinhada ao mesmo tempo.
- No Mac, pressione `Ctrl`- a chave e o `Option`chave e a letra sublinhada ao mesmo tempo.

Ver [Conflito de teclas de atalho e atalhos de teclado](https://publish.obsidian.md/tasks/Editing/Create+or+edit+Task#Hotkey%20and%20keyboard%20shortcut%20conflict) abaixo para obter informações importantes relacionadas aos atalhos de teclado e a tecla de atalho usada para abrir este modal.

### Desligar atalhos de teclado

Lançado

Introduzido nas Tarefas 1.17.0.

Se as teclas de acesso (atalhos de teclado) para qualquer campo entrarem em conflito com os atalhos de teclado do sistema ou interferirem na funcionalidade de tecnologia assistiva que é importante para você, você pode, você pode querer desativá-los nas configurações do plugin Tasks:

![Criar ou Editar Modal](https://publish-01.obsidian.md/access/40e62a316a834ff6f495ebf1d122cae6/images/settings-provide-access-keys-in-dialogs.png)

Esta configuração tem efeito imediato e não requer o reinício do Obsidian.

### Inserindo valores

#### Descrição

Este é o texto que descreve a sua tarefa.

Se você tem um [filtro global](https://publish.obsidian.md/tasks/Getting+Started/Global+Filter) ativada, a caixa de diálogo cuida de adicioná-la automaticamente.

A caixa de descrição pode ser ampliada arrastando seu canto. O texto de várias linhas pode ser colado ou arrastado e solto, e as Tarefas removerão os caracteres de fim de linha automaticamente.

Lançado

O campo Descrição tornou-se redimensionável em Tasks 2.0.0.

#### Prioridade

Ver [prioridade](https://publish.obsidian.md/tasks/Getting+Started/Priority).

#### Recorrência

Aqui você pode fazer a tarefa se repetir, de modo que quando ele é marcado como feito, uma nova tarefa é criada, com datas mais recentes.

Dica

Uma tarefa com uma regra de recorrência também é necessária para ter pelo menos uma das datas de Vencimento, Agendamento ou Início.  
Ver [As tarefas recorrentes devem ter pelo menos uma data](https://publish.obsidian.md/tasks/Getting+Started/Recurring+Tasks#Recurring%20tasks%20must%20have%20at%20least%20one%20date).

Ver [tarefas recorrentes (repetição)](https://publish.obsidian.md/tasks/Getting+Started/Recurring+Tasks).

#### Datas

Aqui você pode opcionalmente dar a tarefa [devido](https://publish.obsidian.md/tasks/Getting+Started/Dates#Due%20date), [agendado](https://publish.obsidian.md/tasks/Getting+Started/Dates#Scheduled%20date) e [começar](https://publish.obsidian.md/tasks/Getting+Started/Dates#Start%20date) datas.

Você também pode adicionar ou editar [criado](https://publish.obsidian.md/tasks/Getting+Started/Dates#Created%20date), [feito](https://publish.obsidian.md/tasks/Getting+Started/Dates#Done%20date) e [cancelado](https://publish.obsidian.md/tasks/Getting+Started/Dates#Cancelled%20date) datas.

Há muita flexibilidade aqui. Por exemplo:

- Você pode digitar datas exatas, como `2022-11-28`.
- Você também pode inserir partes de datas, como `6 oct`.
- Você pode inserir datas relativas, como `today` ou `tomorrow` ou `Saturday`.

Observe que as datas relativas serão sempre interpretadas como sendo no futuro, porque geralmente é isso que você quer. Você pode alterar esse comportamento desmarcando "Apenas datas futuras" se quiser inserir uma tarefa atrasada ou experimentar a maneira como as datas relativas no passado seriam interpretadas nas consultas.

Informação

Se ativou a data de criação ‘Set em cada task’ adicionado nas definições de Tarefas (e reiniciou o Obsidian), quando cria uma nova Tarefa através deste modal, a data de hoje será adicionada automaticamente.

Lançado

- `Only future dates`foi introduzido no Tasks 1.15.0.
- Edição de [criado](https://publish.obsidian.md/tasks/Getting+Started/Dates#Created%20date), [feito](https://publish.obsidian.md/tasks/Getting+Started/Dates#Done%20date) e [cancelado](https://publish.obsidian.md/tasks/Getting+Started/Dates#Cancelled%20date) as datas foram introduzidas no Tasks 5.5.0.

#### Abreviaturas de data

Lançado

Introduzido nas Tarefas 1.8.0.

O modal também tem algumas abreviaturas próprias, para acelerar a inserção de valores comuns nos campos de data.

Digite a abreviatura e, em seguida, um caractere de espaço, e toda a palavra será inserida para você.

Abreviaturas suportadas:

| Abreviatura | Texto Expandido |
| ----------- | --------------- |
| `td`        | `today`         |
| `tm`        | `tomorrow`      |
| `yd`        | `yesterday`     |
| `tw`        | `this week`     |
| `nw`        | `next week`     |
| `weekend`   | `sat`           |
| `we`        | `sat`           |

#### Dependências

Lançado

Introduzido nas Tarefas 6.1.0.

Dica

Esta seção descreve a mecânica de adicionar e editar dependências entre suas tarefas.

Para uma explicação da própria instalação de dependências, consulte [Dependências de Tarefas](https://publish.obsidian.md/tasks/Getting+Started/Task+Dependencies).

Use a área "Dependências" do modal para especificar relações entre tarefas, para definir a ordem em que você deseja trabalhar em um conjunto de tarefas.

Exemplo

É assim que as dependências podem parecer para uma tarefa 'Tenha uma parte':

![Uma tarefa que requer que duas tarefas sejam feitas primeiro e, quando concluídas, permitirá que uma outra tarefa seja iniciada.](https://publish-01.obsidian.md/access/40e62a316a834ff6f495ebf1d122cae6/images/task-dependencies-party.png)

Uma tarefa que requer duas tarefas, 'Convidar os convidados' e 'Fazer a comida' a ser feito em primeiro lugar, e, quando feito, permitirá uma outra tarefa, 'Condicionar após a festa', para ser iniciado.

#### Antes disso

Use the "Before this" region to find and link to any tasks that **must be finished before the task being edited can be started**.

This is marked **1** and **2** in the image above.

#### After this

Use the "After this" region to find and link to any tasks that **can only be started after the task being edited is finished**.

This is areas **3** and **4** in the image above.

#### Searching for tasks

Understanding the search query:

- In either "Before this" or "After this", start typing any text from the description of a required task.
- Currently only task descriptions are searched, and not file paths.
- You can type bits of words, in any order, and capitalisation does not matter.
- For example, you could quickly find `Invite the guests` with `inv gu`, or `gu inv`.

Understanding the matches:

- As you type, Tasks will show you up to 20 closest matching tasks.
- Other tasks in the same file as the task being edited are listed first.
- Then matching tasks elsewhere in the vault are shown, followed by their path.
- If any text is too long to fit, it is truncated with `...` and you can hover over the name to see the full text.

This is what the above process looks like:

![Procurar uma tarefa, para configurar uma dependência](https://publish-01.obsidian.md/access/40e62a316a834ff6f495ebf1d122cae6/images/task-dependencies-search.png)

Searching for a task, to set up a dependency

#### Saving dependencies

When you click Apply after editing dependencies:

- `id` fields are added to any tasks that are now depended upon,
- `dependsOn` fields are adjusted to add or remove dependencies.

This is currently the only operation in Tasks that can edit multiple files in the vault in one step.

### Status

Released

Introduced in Tasks 1.23.0.

Use the Status dropdown to change the Status Symbol for the task.

![Tarefa editar modal mostra novos status imediatamente](https://publish-01.obsidian.md/access/40e62a316a834ff6f495ebf1d122cae6/images/modal-showing-new-statuses.png)

For more information, including adding your own customised statuses, see [Statuses](https://publish.obsidian.md/tasks/Getting+Started/Statuses).

#### Automatic setting of dates upon status change

Released

Introduced in Tasks 6.1.0.

When you change the Status Symbol for a Task, the [Date-tracking settings](https://publish.obsidian.md/tasks/Getting+Started/Dates#Date-tracking%20settings) are used to determine whether to update any date fields:

- **If** the status is changed **to** a [DONE status type](https://publish.obsidian.md/tasks/Getting+Started/Statuses/Status+Types#DONE) **from** any other status type,
    - **and** the "Set done date on every completed task" option is enabled,
    - **then** the **Done date** is changed to today's date.
- **If** the status is changed **to** a [CANCELLED status type](https://publish.obsidian.md/tasks/Getting+Started/Statuses/Status+Types#CANCELLED) **from** any other status type,
    - **and** the "Set cancelled date on every completed task" option is enabled,
    - **then** the **Cancelled date** is changed to today's date.

#### Overriding dates on status change

When Tasks has automatically set a Created, Done or Cancelled date to today, you are free to edit the value.

For example, perhaps you actually completed a task yesterday and forget to mark it as complete. Now you can complete it in the modal, and set the Done date to yesterday, before clicking Apply.

#### Rewriting history: completing recurring tasks in the modal

Tip

When marking `when done` recurring tasks as Done in the Edit Task modal, the date of the _next_ occurrence is now calculated from the value in the Done date field.

The Done date value defaults to the current date, but can then be edited before clicking Apply.

This might be useful if you realise that you had forgotten to mark a recurring task as Done on the actual day that you completed it, and so you would like the new instance to be created based on the day you really completed the task, rather than today when you are marking it as done.

(Today's date is still used for an Created day on a new recurrence, though.)

## Display values

These values cannot currently be edited in this modal.

### Completed

A read-only checkbox, showing whether the task is completed.

## Finishing off

To close the modal and save your edits, do one of:

- click `Apply`,
- press `Return` or `Enter`.

To close the modal and cancel your edits, do one of:

- click `Cancel`,
- click or tap outside the modal,
- click the close button at the corner of the modal (if one exists on your operating system),
- hit the `Esc` key.

## Known limitations

### Need to scroll on phone screens

On phone screens the 'Create or edit Task' Modal may be too tall to fit on the screen. It does support scrolling, and on Android, the scrollbar is visible.

Unfortunately iPhones don't display the scrollbar until you actually start scrolling. Tap on the screen and drag down, and you will see a scrollbar appear temporarily. More importantly, the scrolling does then work fine.

We are tracking the iPhone scrollbar issue in [issue #1238](https://github.com/obsidian-tasks-group/obsidian-tasks/issues/1238).

### Hotkey and keyboard shortcut conflict

If the [custom hotkey](https://help.obsidian.md/Customization/Custom+hotkeys) for the 'Create or edit Task' Modal is the same as one of the keyboard shortcuts [Keyboard shortcuts](https://publish.obsidian.md/tasks/Editing/Create+or+edit+Task#Keyboard%20shortcuts) used in this modal, then when the modal opens, **the keyboard shortcut is unexpectedly also triggered**.

For example, making `Alt + O` (Linux and Windows) or `Ctrl + Opt + O` (Mac) will mean that when the modal opens, the `Lowest` priority is selected, instead of `Normal`.

We are tracking this in [issue #2503](https://github.com/obsidian-tasks-group/obsidian-tasks/issues/2503).

## Use this modal in scripts and other plugins

The [Tasks API Interface](https://publish.obsidian.md/tasks/Advanced/Tasks+Api) allows this modal to be used outside of the Tasks plugin, for example in QuickAdd scripts, and by other plugins.

LINKS TO THIS PAGE

[About Editing](https://publish.obsidian.md/tasks/Editing/About+Editing)

[About Task Formats](https://publish.obsidian.md/tasks/Reference/Task+Formats/About+Task+Formats)

[Auto-Suggest](https://publish.obsidian.md/tasks/Editing/Auto-Suggest)

[Dataview Format](https://publish.obsidian.md/tasks/Reference/Task+Formats/Dataview+Format)

[Dates](https://publish.obsidian.md/tasks/Getting+Started/Dates)

[Encontre tarefas com dados inválidos](https://publish.obsidian.md/tasks/How+To/Find+tasks+with+invalid+data)

[Começando](https://publish.obsidian.md/tasks/Getting+Started/Getting+Started)

[Como estilizar botões](https://publish.obsidian.md/tasks/How+To/How+to+style+buttons)

[Introdução](https://publish.obsidian.md/tasks/Introduction)

[Limitações Conhecidas](https://publish.obsidian.md/tasks/Support+and+Help/Known+Limitations)

[Prioridade](https://publish.obsidian.md/tasks/Getting+Started/Priority)

[QuickAdd](https://publish.obsidian.md/tasks/Other+Plugins/QuickAdd)

[Tarefas Recorrentes](https://publish.obsidian.md/tasks/Getting+Started/Recurring+Tasks)

[Configurar status personalizados](https://publish.obsidian.md/tasks/How+To/Set+up+custom+statuses)

[Configurações](https://publish.obsidian.md/tasks/Getting+Started/Settings)

[Estátuas](https://publish.obsidian.md/tasks/Getting+Started/Statuses)

[Tags](https://publish.obsidian.md/tasks/Getting+Started/Tags)

[Dependências de Tarefas](https://publish.obsidian.md/tasks/Getting+Started/Task+Dependencies)

[Tarefas Api](https://publish.obsidian.md/tasks/Advanced/Tasks+Api)

[Alternando e Editando Estátuas](https://publish.obsidian.md/tasks/Editing/Toggling+and+Editing+Statuses)

[Usar o Nome do arquivo como Data Padrão](https://publish.obsidian.md/tasks/Getting+Started/Use+Filename+as+Default+Date)


# Pesquisas

#   
Sobre Consultas

[#index-páginas](https://publish.obsidian.md/#index-pages)

## A Consulta Mais Simples

Você pode listar tarefas de todo o seu cofre consultando-as usando um `tasks` bloco de código. Você pode editar as tarefas dos resultados da consulta clicando no pequeno ícone de lápis ao lado delas. Por padrão, as tarefas são classificadas por status, data de vencimento e caminho. Você pode alterar a classificação (consulte as opções de consulta abaixo).

A maneira mais simples de consultar tarefas é esta:

````
```tasks
```
````

Nos modos Visualização ao Vivo e Leitura, isso será listado _tudo_ tarefas do seu cofre, independentemente de suas propriedades, como status.

Provavelmente não é isso que você quer. Portanto, Tarefas permite definir opções de consulta para filtrar as tarefas que você deseja mostrar.

Por exemplo, você pode mostrar apenas as tarefas (de qualquer lugar no cofre) que são devidas hoje:

````
## Due today
```tasks
due today
not done
```
````

You can create as many task queries as you like, and you can also wrap them into [callouts](https://help.obsidian.md/Editing+and+formatting/Callouts) if you want to style them differently:

```
> [!check] Due today
> ```tasks
> due today
> not done
> ```
```

In the following sections we will explain all the various options that are available for querying tasks.

## Tasks Query options

### Searching tasks - Basics

- [Filters](https://publish.obsidian.md/tasks/Queries/Filters)
- [Explaining Queries](https://publish.obsidian.md/tasks/Queries/Explaining+Queries)
- [Comments](https://publish.obsidian.md/tasks/Queries/Comments)
- [Examples](https://publish.obsidian.md/tasks/Queries/Examples)

### Searching tasks - Advanced

- [Global Query](https://publish.obsidian.md/tasks/Queries/Global+Query)
- [Combining Filters](https://publish.obsidian.md/tasks/Queries/Combining+Filters)
- [Regular Expressions](https://publish.obsidian.md/tasks/Queries/Regular+Expressions)
- [Line Continuations](https://publish.obsidian.md/tasks/Queries/Line+Continuations)

### Viewing the results

- [Backlinks](https://publish.obsidian.md/tasks/Queries/Backlinks)

### Controlling the display

- [Limiting](https://publish.obsidian.md/tasks/Queries/Limiting)
- [Sorting](https://publish.obsidian.md/tasks/Queries/Sorting)
- [Grouping](https://publish.obsidian.md/tasks/Queries/Grouping)
- [Layout](https://publish.obsidian.md/tasks/Queries/Layout)

## Query Tips

### Capitals in Query Instructions - Case Insensitivity

Released

The ability to use capital letters in query instructions was introduced in Tasks 5.2.0.

Almost all Tasks query instructions are now case-INsensitive: they can now be typed with capital letters. This is especially helpful when typing them on mobile phones, and for emphasising important words.

For example, the following instructions are identical:

- `due before tomorrow`
- `Due before tomorrow`
- `due BEFORE Tomorrow`

The only exceptions to this flexibility are:

- When [Combining Filters](https://publish.obsidian.md/tasks/Queries/Combining+Filters), the boolean operators such as `AND`, `OR` and `NOT` must still be capitalised.
- In [Regular Expressions](https://publish.obsidian.md/tasks/Queries/Regular+Expressions), the search pattern and flags are still case-sensitive.
- The code in expressions in [Custom Filters](https://publish.obsidian.md/tasks/Scripting/Custom+Filters), [Custom Sorting](https://publish.obsidian.md/tasks/Scripting/Custom+Sorting) and [Custom Grouping](https://publish.obsidian.md/tasks/Scripting/Custom+Grouping) remain case-sensitive.

### Why is my query not working?

If a query gives unexpected results, see [Explaining Queries](https://publish.obsidian.md/tasks/Queries/Explaining+Queries) and add the `explain` instruction.

## Limitations of Queries

### Tasks are not indented in query results

Warning

The result list will list tasks unindented. See [#60](https://github.com/obsidian-tasks-group/obsidian-tasks/discussions/60) for a discussion around the topic. Do not hesitate to contribute 😊

### Footnotes are not displayed in query results

Warning

The result list will not contain any footnotes of the original task. The footnotes will _not_ be carried over to documents with ```tasks blocks. We are tracking this in [issue #2571](https://github.com/obsidian-tasks-group/obsidian-tasks/issues/2571).

See also [Getting Started > Tasks with Footnotes](https://publish.obsidian.md/tasks/Getting+Started/Getting+Started#Tasks%20with%20Footnotes).

LINKS TO THIS PAGE

[Examples](https://publish.obsidian.md/tasks/Queries/Examples)

[Getting Started](https://publish.obsidian.md/tasks/Getting+Started/Getting+Started)

[Introduction](https://publish.obsidian.md/tasks/Introduction)

[Known Limitations](https://publish.obsidian.md/tasks/Support+and+Help/Known+Limitations)