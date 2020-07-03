# Seções

As seções renderizam blocos de texto uma ou mais vezes, dependendo do valor da chave no contexto atual.

Uma seção começa com uma  `#` e termina com uma `/`. Ou seja, `{{#person}}` inicia uma seção "pessoa" enquanto `{{/person}}`  termina.

O comportamento da seção é determinado pelo valor da chave.

**Valores falsos ou listas vazias**

Se a chave **person** existir e tiver um valor falso ou uma lista vazia, o HTML entre o início e final da tag não será exibido.

```text
Exemplo:

Visualizando.

{{#person}}
  Não visualizando!
{{/person}}

Hash:

{
  "person": false
}

Saída:

Visualizando.
```

**Listas não vazias**

Se a chave **person** existir e tiver um valor não falso, o HTML entre o início e final da tag será renderizado e exibido uma ou mais vezes.

Quando o valor é uma lista não vazia, o texto no bloco será exibido uma vez para cada item da lista. O contexto do bloco será definido como o item atual para cada iteração. Dessa forma, podemos percorrer coleções.

```text
Exemplo:

{{#person}}
  <b>{{name}}</b>
{{/person}}
Hash:

{
  "person": [
    { "name": "resque" },
    { "name": "hub" },
    { "name": "rip" }
  ]
}
Saída:

<b>resque</b>
<b>hub</b>
<b>rip</b>
```

**Valores Não Falsos**

Quando o valor não for falso e também não for uma lista, poderá usado como contexto para uma única renderização do bloco.

```text
Exemplo:

{{#person?}}
  Oi {{name}}!
{{/person?}}
Hash:

{
  "person?": { "name": "Jon" }
}
Saída:

Oi Jon!
```

