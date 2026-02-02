---
description: >-
  O quê são sistemas de controle de versão centralizados e distribuídos e quais
  são as suas diferenças
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

# 2.5 Sistemas Distribuídos

Os Sistemas de Controle de Versão Distribuídos surgem como uma evolução do modelo centralizado. A principal mudança está na forma como o projeto é compartilhado e mantido.

A ideia aqui, assim como antes, não é entrar em detalhes técnicos, mas entender a lógica geral do modelo distribuído e como ele organiza o trabalho em equipe. Ao decorrer do livro, vamos aprender especificamente sobre o Git e aí assim entraremos em mais detalhes do seu funcionamento.

## Como funciona um sistema distribuído

Imagine o mesmo cenário de antes: um grupo de pessoas trabalhando juntas em um projeto, que é composto por vários arquivos relacionados entre si. A diferença agora está em **como** esse projeto é compartilhado entre as pessoas.

Em vez de existir apenas um único lugar que guarda o projeto completo, como no modelo centralizado, nos sistemas distribuídos cada pessoa possui uma cópia **completa** do projeto em seu próprio computador. Essa cópia não contém apenas os arquivos atuais, mas também todo o histórico de mudanças do projeto.&#x20;

### Onde o projeto fica

Assim como no modelo centralizado, também existe o conceito de **repositório.** A diferença é que agora existem dois tipos importantes:

* **Repositório local**: é o repositório que fica no computador de cada pessoa.
* **Repositório remoto**: é o repositório que fica em um servidor e é usado para compartilhar o projeto entre a equipe.

Quando uma pessoa começa a participar do projeto, ela faz uma cópia completa do repositório remoto para sua máquina. A partir desse momento, ela passa a ter um **repositório local completo**, com todos os arquivos e todo o histórico do projeto.

### O papel do repositório remoto

O repositório remoto continua existindo e ainda é muito importante. Ele funciona como um **ponto de encontro** para a equipe. É nele que as pessoas publicam suas mudanças e de onde recebem as mudanças feitas por outras pessoas.

A grande diferença em relação ao modelo centralizado é que o repositório remoto **não é mais o único lugar onde o projeto existe**. Ele deixa de ser o “dono” do histórico e passa a ser um ponto de sincronização entre vários repositórios completos.

### Trabalhando localmente

No dia a dia, a maior parte do trabalho acontece no repositório local. A pessoa pode editar arquivos, criar novos, remover o que não é mais necessário, registrar versões e consultar o histórico, tudo isso sem precisar estar conectada ao servidor. As mudanças ficam registradas localmente, no seu próprio repositório.

Isso também muda a forma como conflitos e mesclagens acontecem. Como cada pessoa tem seu próprio histórico local, é possível registrar várias versões intermediárias, testar ideias, desfazer mudanças e reorganizar o trabalho antes mesmo de compartilhar qualquer coisa com o resto da equipe.

### Compartilhando alterações

Quando a pessoa decide compartilhar seu trabalho com o restante da equipe, ela envia suas mudanças para o repositório remoto. Da mesma forma, quando quer receber as mudanças feitas por outras pessoas, ela atualiza seu repositório local a partir do remoto.

Nesse processo, pode ocorrer a **mesclagem**, que é quando o sistema junta alterações vindas de repositórios diferentes. Na maioria dos casos, essa junção é feita automaticamente. Quando duas pessoas modificam exatamente a mesma parte de um arquivo, surgem os chamados **conflitos**, que precisam ser resolvidos manualmente.

A diferença importante em relação ao modelo centralizado é que, no sistema distribuído, esses conflitos tendem a ser resolvidos localmente, no próprio computador da pessoa, antes de enviar as mudanças para o repositório remoto.

Além disso, o uso de bloqueio de arquivos (lock) deixa de ser essencial. Como cada pessoa trabalha em sua própria cópia completa, o modelo distribuído favorece que todos editem livremente e que os ajustes sejam feitos depois, por meio de mesclagens, em vez de impedir edições antecipadamente.

Assim, o fluxo geral passa a ser:

* cada pessoa trabalha e registra mudanças localmente;
* em momentos específicos, sincroniza com o repositório remoto;
* o repositório remoto serve para integrar o trabalho da equipe.

***

Em resumo, nos Sistemas de Controle de Versão Distribuídos, o projeto não vive mais em um único lugar. Ele passa a existir em **múltiplas cópias completas**, uma em cada computador. Cada pessoa trabalha de forma independente em seu repositório local, enquanto o repositório remoto serve como ponto de compartilhamento e integração.

Na próxima seção, vamos acompanhar um exemplo prático de fluxo para ver tudo isso funcionando na prática.
