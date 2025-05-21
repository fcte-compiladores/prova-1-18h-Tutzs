De modo abstrato, o compilador é um programa que converte código de uma
linguagem para outra. Como se fosse uma função do tipo `compilador(str) -> str`.
No caso de compiladores que emitem código de máquina ou bytecode, seria mais
preciso dizer `compilador(str) -> bytes`, mas a idéia básica é a mesma.

De forma geral o processo é dividido em etapas como abaixo

```python
def compilador(x1: str) -> str | bytes:
    x2 = lex(x1)        # análise léxica
    x3 = parse(x2)      # análise sintática
    x4 = analysis(x3)   # análise semântica
    x5 = optimize(x4)   # otimização
    x6 = codegen(x5)    # geração de código
    return x6
```

Defina brevemente o que cada uma dessas etapas realizam e marque quais seriam os
tipos de entrada e saída de cada uma dessas funções. Explique de forma clara o
que eles representam. Você pode usar exemplos de linguagens e/ou compiladores
conhecidos para ilustrar sua resposta. Salve sua resposta nesse arquivo.

# lex(str) -> list[Token]
A análise léxica pega o código-fonte e transforma em uma lista de tokens, que são tipo as palavras-chave, operadores e outras partes importantes do código.
 
# parse(list[Token]) -> AST
A análise sintática pega a lista de tokens e monta uma AST, que mostra a estrutura do programa de acordo com as regras da linguagem.

# analysis(aST) -> AST
A análise semântica serve pra checar se o programa faz sentido de verdade e, às vezes, adiciona informações extras na AST.

# optimize(AST) -> AST
A otimização pega a AST e faz algumas mudanças pra deixar o código mais eficiente, mas sem mudar o que o programa realmente faz.

# codegen(AST) -> str | byte
A geração de código pega a AST e transforma em um código de saída, que pode ser, por exemplo, código de máquina.
