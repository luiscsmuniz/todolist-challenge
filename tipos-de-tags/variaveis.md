# Variáveis

O tipo de tag mais básico é a variável. Uma `{{name}}` tag  em um modelo básico tentará encontrar a chave de nome no contexto atual. Se não houver uma chave de nome, os contextos pai serão verificados recursivamente. Se o contexto superior for alcançado e a chave de nome ainda não for encontrada, nada será renderizado.

Todas as variáveis que contém tags HTML são removidas por padrão. Se você deseja retornar HTML, use o chaves triplas: `{{{name}}}`.

Exemplo:

```markup
Template:

* {{name}}
* {{age}}
* {{company}}
* {{{company}}}

Hash:

  {
    "name": "Chris",
    "company": "<b>GitHub</b>"
  }
  
Saída:

* Chris
*
* &lt;b&gt;GitHub&lt;/b&gt;
* <b>GitHub</b>
```

