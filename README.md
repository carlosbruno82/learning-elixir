# Apprentice challenge

## language: Elixir

## Source: https://elixirschool.com/pt/lessons/basics/basics/#primeiros-passos

### Versão instalada.
```
$ elixir -v
```

### Modo Interativo
```
$ iex
```

### Tipos Básicos
**Inteiros**
```
iex> 255
255
```

*O suporte para números binários, octais e hexadecimais também estão inclusos:*
```
iex> 0b0110
6
iex> 0o644
420
iex> 0x1F
31
```

**Pontos Flutuantes**
*Em Elixir, os números de ponto flutuante requerem um decimal depois de pelo menos um dígito; estes possuem uma precisão de 64 bits e suportam e para números exponenciais:*
```
iex> 3.14
 3.14
iex> .14
** (SyntaxError) iex:2: syntax error before: '.'
iex> 1.0e-10
1.0e-10
```

**Booleanos**
*Elixir suporta "true" e "false" como booleanos; todo valor é verdadeiro com exceção de "false" e "nil"*
```
iex> true
true
iex> false
false
```

**Átomos**
*Um átomo é uma constante cujo o nome é seu valor. Se está familiarizado com Ruby, estes são equivalentes aos símbolos:*
```
iex> :foo
:foo
iex> :foo == :bar
false
```
*Booleanos "true" e "false" também são os átomos ":true" e ":false", respectivamente.*
```
iex> is_atom(true)
true
iex> is_boolean(:true)
true
iex> :true === true
true
```
*Nomes de módulos em Elixir também são átomos. "MyApp.MyModule" é um átomo válido, mesmo se tal módulo ainda não tenha sido declarado.*
```
iex> is_atom(MyApp.MyModule)
true
```
*Átomos também são usados para referenciar módulos de bibliotecas Erlang, incluindo as bibliotecas integradas.*
```
iex> :crypto.strong_rand_bytes 3
<<23, 104, 108>>
```

**Strings**
*As strings em Elixir são codificadas em UTF-8 e são representadas com aspas duplas:*
```
iex> "Hello"
"Hello"
iex> "dziękuję"
"dziękuję"
```
*As strings suportam quebras de linha e caracteres de escape:*
```
iex> "foo
...> bar"
"foo\nbar"
iex> "foo\nbar"
"foo\nbar"
```

### Operações Básicas
**Aritmética**
*Elixir suporta os operadores básicos "+", "-", "*", e "/" como era de se esperar. É importante ressaltar que "/" sempre retornará um número ponto flutuante:*
```
iex> 2 + 2
4
iex> 2 - 1
1
iex> 2 * 5
10
iex> 10 / 5
2.0
```
*Se você necessita de uma divisão inteira ou o resto da divisão, Elixir vem com duas funções úteis para isto:*
```
iex> div(10, 5)
2
iex> rem(10, 3)
1
```

**Booleanos**
*Elixir provê os operadores booleanos "||", "&&", e "!". Estes suportam qualquer tipo:*
```
iex> -20 || true
-20
iex> false || 42
42

iex> 42 && true
true
iex> 42 && nil
nil

iex> !42
false
iex> !false
true
```
*Há três operadores adicionais cujo o primeiro argumento tem que ser um booleano ("true" e "false"):*
```
iex> true and 42
42
iex> false or true
true
iex> not false
true
iex> 42 and true
** (ArgumentError) argument error: 42
iex> not 42
** (ArgumentError) argument error
```
*Nota: O "and" e "or" do Elixir são mapeados para "andalso" e "orelse" do Erlang.*

**Comparação**
*Elixir vem com todos os operadores de comparação que estamos acostumados a usar: "==", "!=", "===", "!==", "<=", ">=", "<" e ">".*
```
iex> 1 > 2
false
iex> 1 != 2
true
iex> 2 == 2
true
iex> 2 <= 3
true
```
*Para comparação de inteiros e pontos flutuantes usa-se "===":*
```
iex> 2 == 2.0
true
iex> 2 === 2.0
false
```
*Uma característica importante do Elixir é que qualquer tipo pode ser comparado; isto é particularmente útil em ordenação. Não precisamos memorizar a ordem de classificação, mas é importante estar ciente de que:*
```
number < atom < reference < function < port < pid < tuple < map < list < bitstring
```
*Isso pode levar a algumas comparações interessantes e válidas, que você pode não encontrar em outras linguagens:*
```
iex> :hello > 999
true
iex> {:hello, :world} > [1, 2, 3]
false
```

**Interpolação de Strings**
*Se você já usou Ruby, a interpolação de strings em Elixir parecerá muito familiar:*
```
iex> name = "Sean"
iex> "Hello #{name}"
"Hello Sean"
```

**Concatenação de Strings**
*A concatenação de strings usa o operador "<>":*
```
iex> name = "Sean"
iex> "Hello " <> name
"Hello Sean"
```


<div style="text-align: right">

~~Carlos Bruno~~ 🛰️

</div>


