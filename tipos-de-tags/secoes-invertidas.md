# Seções invertidas

Uma seção invertida começa com um sinal de `^` e termina com uma `/`. Ou seja, `{{^person}}` inicia uma seção invertida "pessoa" enquanto `{{/person}}` termina.

Embora as seções possam ser usadas para renderizar texto uma ou mais vezes com base no valor da chave, as seções invertidas podem renderizar texto uma vez com base no valor inverso da chave. Ou seja, eles serão renderizados se a chave não existir, for falsa ou for uma lista vazia.

```text
Exemplo:

{{#person}}
  <b>{{name}}</b>
{{/person}}
{{^person}}
  Sem pessoas :(
{{/person}}
Hash:

{
  "person": []
}

Saída:

Sem pessoas :(
```

