---
description: >-
  O quê são sistemas de controle de versão centralizados e distribuídos e quais
  são as suas diferenças
---

# 2.4 Sistemas Centralizados

## Por que entender sistemas centralizados

O Git, sistema de controle de versão que vamos estudar neste livro, é um sistema **distribuído**. Mas, antes de irmos direto para esse modelo mais moderno, é importante entender como os sistemas centralizados funcionavam e por que eles acabaram motivando a criação de algo novo.

Mesmo que você nunca venha a usar um sistema centralizado na prática, entender esse modelo ajuda bastante a compreender melhor o Git. Muitas decisões do Git fazem mais sentido quando conhecemos os problemas que ele veio resolver.

Em algum momento, você provavelmente vai se perguntar: “Mas por que o Git faz isso desse jeito?”. Com esse contexto, o que parece estranho no começo passa a fazer sentido, e você percebe que existe uma lógica por trás das escolhas.

Não se preocupe em aprender detalhes técnicos dos sistemas centralizados. O foco deste livro é o modelo distribuído, e é nele que vamos mergulhar de verdade nos próximos capítulos.

## Como funciona um sistema centralizado

O objetivo aqui é entender, de forma geral, como funciona um Sistema de Controle de Versão Centralizado. A ideia não é entrar em muitos detalhes técnicos, mas compreender a lógica desse modelo.

Imagine um grupo de pessoas trabalhando juntas em um projeto. Um projeto, nesse contexto, é simplesmente um conjunto de arquivos relacionados entre si. Esses arquivos podem representar muitas coisas diferentes: um site, com páginas, imagens e textos; um aplicativo, com arquivos de código; um livro, com capítulos separados; ou até um trabalho acadêmico, com textos, tabelas e referências.

Independentemente do tipo, a situação é sempre parecida: várias pessoas mexendo em arquivos que fazem parte de um mesmo conjunto.

Para organizar esse trabalho coletivo, o grupo decide adotar um Sistema de Controle de Versão Centralizado.

### Onde o projeto fica

A primeira pergunta que surge naturalmente é: onde o projeto vai ficar guardado?

Em todo Sistema de Controle de Versão, em geral, existe uma **pasta especial chamada repositório**. Ela faz mais do que apenas armazenar arquivos.

Além de guardar a versão atual de cada arquivo, o repositório **registra o histórico das mudanças ao longo do tempo**. Cada alteração fica registrada com informações como o que mudou, quando mudou e quem fez a mudança. Assim, é possível acompanhar a evolução do projeto como uma linha do tempo.

O repositório passa a ser a **referência oficial do projeto**. Na prática, isso significa que o projeto “mora” ali. É naquele lugar que está a versão principal, usada por todas as pessoas como base de trabalho.

A partir desse momento, o grupo passa a usar o repositório como o local oficial para armazenar e versionar os arquivos do projeto.

### O papel do servidor

Agora que o grupo já sabe que o projeto ficará em um repositório, surge outra pergunta: em qual computador esse repositório vai ficar?

Para que a colaboração funcione bem, esse repositório precisa ficar em um computador específico, dedicado a essa tarefa. Esse computador é chamado de **servidor**.

O servidor não é o computador pessoal de ninguém do grupo. Se fosse, o andamento do trabalho dependeria da rotina dessa pessoa: do horário em que liga o computador, da qualidade da internet ou até do simples fato de desligar a máquina no fim do dia. O servidor existe justamente para evitar esse tipo de dependência.

Ele fica ligado e acessível o tempo todo, funcionando como o ponto central do projeto.

As pessoas se conectam a esse servidor pela rede. A partir de seus próprios computadores, elas conseguem acessar esse lugar central usando a internet ou uma rede interna. Ao longo do livro, vamos chamar esses computadores pessoais de **máquinas locais**.

Cada pessoa começa copiando os arquivos do projeto para sua máquina local. Assim, pode trabalhar com mais conforto, sem depender da conexão o tempo inteiro.

### Enviando alterações

Depois de fazer suas alterações, como ajustar um texto, modificar um arquivo, criar algo novo ou remover o que não é mais necessário, a pessoa envia de volta para o servidor apenas os arquivos que mudaram.

O servidor recebe essas alterações e, quando necessário, realiza a mesclagem.\
Mesclar significa juntar mudanças feitas por pessoas diferentes, combinando o que já existia no projeto com o que acabou de ser enviado. Quando as alterações não se sobrepõem, essa junção acontece de forma automática. Em seguida, o servidor atualiza os arquivos do projeto e registra tudo no histórico, incluindo quem realizou cada mudança.

Esse processo acontece em um ciclo contínuo: as pessoas copiam a versão mais recente dos arquivos do servidor para a máquina local, fazem suas mudanças localmente e enviam de volta o que foi alterado. À medida que o projeto evolui, esse ciclo se repete várias vezes, com diferentes pessoas contribuindo.

### Conflitos

Quando duas ou mais pessoas mexem no mesmo arquivo, surgem situações chamadas de **conflitos**.

Existem diferentes formas de lidar com isso, e equipes diferentes fazem escolhas diferentes. Algumas preferem usar um sistema de bloqueio (_lock_), em que o arquivo fica temporariamente bloqueado enquanto alguém o edita, impedindo que outras pessoas mexam nele ao mesmo tempo.

Outras equipes preferem deixar todo mundo editar livremente e resolver os problemas depois. Nesse caso, quando as mudanças chegam ao servidor, elas são comparadas e reunidas. Se duas pessoas alterarem exatamente a mesma parte de um arquivo, alguém precisa revisar e ajustar o conteúdo para que tudo faça sentido novamente.

***

Em resumo, essa é a dinâmica geral dos sistemas de controle de versão centralizados: um servidor guarda o repositório, registra o histórico e organiza o ciclo de copiar arquivos, modificar localmente e enviar alterações de volta para o ponto central. Sistemas como o Subversion (SVN) e o Microsoft Team Foundation Version Control (TFVC) seguem exatamente esse modelo.

Na próxima seção, vamos acompanhar um exemplo concreto desse fluxo, passo a passo, para ver como tudo isso acontece na prática.
