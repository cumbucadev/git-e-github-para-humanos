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

# 4.4 Configurações do Git local

Nesta seção, vamos entender o que são as configurações do Git e como elas ajudam a definir o comportamento da ferramenta. Você verá como essas configurações são organizadas, como são nomeadas e onde ficam armazenadas, preparando o terreno para os próximos tópicos.

## O que são as configurações do Git

As configurações do Git são ajustes que definem como a ferramenta deve se comportar no seu computador e nos seus projetos. Elas controlam preferências básicas, como identificação da pessoa usuária, idioma, formato de saída dos comandos e outras opções de comportamento.

Você pode pensar nas configurações do Git como as preferências de um jogo ou aplicativo. Antes de começar a usar, você ajusta algumas opções para que tudo funcione da forma esperada. No Git, essas configurações ajudam a adaptar a ferramenta ao seu ambiente e ao seu jeito de trabalhar.

<figure><img src="../../.gitbook/assets/0433.png" alt=""><figcaption></figcaption></figure>

Essas configurações não alteram os arquivos do projeto. Em vez disso, elas influenciam como o Git executa comandos, exibe informações e organiza o trabalho internamente.

As configurações do Git são armazenadas em arquivos próprios e podem ter diferentes níveis de alcance, chamados de escopos. Dependendo do escopo, uma configuração pode valer para todo o computador, para uma pessoa usuária específica ou apenas para um projeto.

Mais adiante, veremos o que cada escopo significa, onde esses arquivos ficam e como o Git decide qual valor utilizar quando a mesma configuração aparece em mais de um lugar.

## Formato das configurações

As configurações do Git seguem um padrão formado por duas partes separadas por um ponto. Esse formato existe para organizar melhor as informações e deixar claro a que tipo de dado cada configuração se refere.

A primeira parte indica a categoria da configuração. A segunda parte indica a configuração específica que será armazenada dentro dessa categoria. De forma geral, esse padrão pode ser representado assim:

> categoria.configuração

Para exemplificar esse formato, vamos utilizar duas configurações ao longo desta seção: `user.name` e `user.email`.

Ao utilizar Git, cada pessoa precisa informar alguns dados básicos para conseguir colaborar em projetos. Antes mesmo de aprender os comandos, é importante entender como essas informações são organizadas dentro do Git. No caso das informações de identificação, a categoria utilizada é `user`.

Assim, a configuração `user.name` representa o nome da pessoa que está utilizando o Git, enquanto a configuração `user.email` representa o endereço de email associado a essa pessoa. Em ambos os casos, o prefixo `user` deixa claro que essas informações estão relacionadas à identidade de quem trabalha no projeto.

Essas configurações precisam ser definidas por todas as pessoas que utilizam Git. Dessa forma, ao trabalhar em equipe, o Git consegue manter um histórico organizado, no qual é possível identificar quem realizou cada modificação ao longo do projeto.

## Armazenamento das configurações

Quando você utiliza o Git, as informações de configuração não ficam apenas na memória do computador nem existem só enquanto você está usando o terminal. O Git salva essas informações em arquivos de texto no seu computador.

Esses arquivos funcionam como listas de preferências. Sempre que o Git é executado, ele lê esses arquivos para entender quais valores deve utilizar e como deve se comportar.

Cada escopo de configuração possui seu próprio arquivo, armazenado em um local diferente. É isso que permite que algumas configurações valham para todo o computador, outras apenas para a pessoa usuária e outras somente para um projeto específico.

Independentemente do escopo, o formato das configurações dentro desses arquivos é sempre o mesmo. As informações são organizadas por categoria e seguem o padrão:

```
[categoria]
    configuração = valor
```

Por exemplo, quando as informações de identificação estão definidas, um arquivo de configuração pode conter algo como:

```
[user]
    name = Aprendiz Cumbuca Dev
    email = aprendiz.cumbucadev@gmail.com
```

Nesse exemplo, `user` é a categoria da configuração. Dentro dessa categoria, aparecem as configurações `name` e `email`, cada uma associada a um valor.

Sempre que o Git precisa dessas informações, ele lê esses arquivos de configuração automaticamente, sem que seja necessário informar tudo novamente.&#x20;

***

A seguir, vamos entender os diferentes escopos de configuração. Você vai entender o que cada um deles representa, quando usar cada escopo e como o Git escolhe qual configuração aplicar em cada situação.

{% hint style="warning" %}
#### Configurações locais do Git não são configurações do GitHub

Se você já teve contato com GitHub ou com outros sistemas de hospedagem de repositórios, é importante não confundir as configurações apresentadas nesta seção com configurações de autenticação ou acesso remoto.

Tudo o que será visto aqui diz respeito **apenas ao Git instalado localmente** no computador. Essas configurações não têm relação com GitHub, SSH, chaves, tokens ou qualquer outro mecanismo de acesso a plataformas externas.

Esses temas serão abordados separadamente mais adiante.
{% endhint %}
