---
layout:
  width: default
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
  metadata:
    visible: true
---

# 4.4 Configurações do Git

Nesta seção, vamos entender como o Git pode ser configurado e quais são os tipos de configurações disponíveis. Você verá como essas configurações influenciam o comportamento do Git e como elas se organizam em diferentes escopos.

## O que são as configurações do Git

As configurações do Git são ajustes que definem como a ferramenta deve se comportar no seu computador e nos seus projetos. Elas controlam preferências básicas, como identificação da pessoa usuária, idioma, formato de saída dos comandos e outras opções de comportamento.

Você pode pensar nas configurações do Git como as preferências de um jogo ou aplicativo. Antes de começar a usar, você ajusta algumas opções para que tudo funcione da forma esperada. No Git, essas configurações ajudam a adaptar a ferramenta ao seu ambiente e ao seu jeito de trabalhar.

<figure><img src="../../.gitbook/assets/0433.png" alt=""><figcaption></figcaption></figure>

Essas configurações não alteram os arquivos do projeto. Em vez disso, elas influenciam como o Git executa comandos, exibe informações e organiza o trabalho internamente.

As configurações do Git são armazenadas em arquivos próprios e podem ter diferentes níveis de alcance, chamados de escopos. Dependendo do escopo, uma configuração pode valer para todo o computador, para uma pessoa usuária específica ou apenas para um projeto.

Nos próximo tópico, vamos entender o que são esses escopos e como eles funcionam na prática.

## Onde o Git salva as configurações

Quando você configura o Git, essas informações não ficam apenas no terminal. O Git salva todas as configurações em **arquivos de texto** no seu computador.

Esses arquivos funcionam como listas de preferências. Sempre que o Git é executado, ele lê esses arquivos para saber como deve se comportar.

Cada escopo de configuração possui seu próprio arquivo, em um local diferente. Isso é o que permite que algumas configurações valham para todo o computador, outras só para uma pessoa usuária e outras apenas para um projeto específico.

## Escopos de configuração

Configurar o Git é como ajustar as preferências de um jogo antes de começar a jogar. Algumas configurações valem para todos os jogos, outras só para você como pessoa jogadora, e outras apenas para um jogo específico.

No Git, essas configurações são organizadas em escopos. Um escopo define onde uma configuração se aplica e quem ela afeta. Em outras palavras, ele responde à pergunta: para quem e para onde essa configuração vale?

O Git possui três escopos principais: system, global e local. Cada um deles representa um nível diferente de alcance da configuração.

### Escopo de sistema (&#x73;_&#x79;stem_)

O escopo de sistema pode ser comparado às configurações do console ou do computador onde os jogos rodam. Em um jogo, seriam opções como a resolução da tela ou o idioma do console.

No Git, o escopo System define configurações que se aplicam a todas as pessoas usuárias e a todos os repositórios do computador.

Escopo: computador inteiro\
Arquivo de configuração:

* Linux e macOS: `/etc/gitconfig`
* Windows: `C:\Program Files\Git\etc\gitconfig`

Esse tipo de configuração normalmente é definido por quem administra o sistema e não costuma ser alterado com frequência.

### Escopo global (&#x67;_&#x6C;obal_)

O escopo global representa as preferências da pessoa jogadora. Em um jogo, seriam configurações como o nome da pessoa jogadora ou os controles personalizados.

No Git, o escopo Global define configurações que se aplicam a todos os repositórios de uma mesma pessoa usuária, independentemente do projeto.

Escopo: pessoa usuária\
Arquivo de configuração:

* Linux e macOS: `~/.gitconfig`
* Windows: `C:\Users\SEU_USUARIO\.gitconfig`

Esse é o escopo mais comum para configurações pessoais, pois normalmente elas não mudam de um projeto para outro.

### Escopo local (&#x6C;_&#x6F;cal_)

O escopo local é equivalente às configurações salvas de um jogo específico. Em um jogo, seria algo como a dificuldade definida para uma partida em andamento.

No Git, o escopo Local define configurações que se aplicam somente ao repositório atual, sem impactar outros projetos.

Escopo: repositório\
Arquivo de configuração:

* Linux e macOS: `<pasta-do-projeto>/.git/config`
* Windows: `<pasta-do-projeto>\.git\config`

Esse escopo é usado quando um projeto precisa de configurações diferentes das demais.

### Ordem de prioridade dos escopos

Para entender como o Git decide qual configuração usar, é importante observar a ordem de prioridade entre os escopos.

A imagem ilustra como os escopos de configuração do Git se organizam do mais amplo para o mais específico. No topo está o escopo **system**, que afeta todo o computador. Em seguida vem o escopo **global**, que se aplica apenas à pessoa usuária. Por fim, o escopo **local**, que vale somente para um repositório específico.

A seta indica que, à medida que avançamos nessa direção, as configurações se tornam mais específicas e passam a ter maior prioridade.

<figure><img src="../../.gitbook/assets/0434.png" alt=""><figcaption></figcaption></figure>

Quando uma mesma configuração existe em mais de um escopo, o Git segue essa ordem de prioridade: primeiro o **local**, depois o **global** e, por fim, o **system**. Isso significa que configurações locais sobrescrevem as globais, e configurações globais sobrescrevem as de sistema. O Git sempre utiliza a configuração mais específica disponível.

***

Na próxima seção, vamos aprender a usar o comando <mark style="color:purple;">git</mark> <mark style="color:orange;">config</mark> na prática. Veremos como criar, alterar e consultar configurações do Git, aplicando os escopos que vimos aqui para personalizar o comportamento da ferramenta de forma segura e controlada.
