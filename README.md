# Descrição

o Template pode ser usado para HTML, arquivos de configuração, geração de relatórios, código fonte - qualquer coisa. Ele funciona expandindo tags em um modelo usando valores fornecidos em um hash ou objeto.

Chamamos isso de "menos lógica" porque não há instruções if, cláusulas else ou loops. Em vez disso, existem apenas tags. Algumas tags são substituídas por um valor, outras nada e outras uma série de valores.

### Exemplo

Um exemplo básico:

```markup
<p>
    Olá, {{name}}
    Você acabou de ganhar {{value}} reais!
    {{#in_ca}}
    Bem, {{taxed_value}} reais, depois dos impostos.
    {{/ in_ca}}
</p>
```

Dado o seguinte hash:

```markup
{
    "nome": "Chris",
    "valor": 10000,
    "taxed_value": 10000 - (10000 * 0,4),
    "in_ca": true
}
```

Produzirá o seguinte:

> Olá Chris Você acabou de ganhar 10000 reais! Bem, 6000,0 reais, depois dos impostos.



