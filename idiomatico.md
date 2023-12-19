# Idioma da Linguagem (Idiomatic)

A característica "Idioma da Linguagem" em um projeto de software representa a conformidade do código às convenções e padrões estabelecidos pela linguagem de programação utilizada. Seguir práticas idiomáticas não apenas promove a legibilidade do código, tornando-o mais claro e compreensível, mas também contribui para a coesão e consistência no desenvolvimento. Ao alinhar o código com as normas da linguagem, os desenvolvedores facilitam a colaboração, tornando o código mais acessível e compreensível para outros membros da equipe. A adesão a padrões idiomáticos não apenas aprimora a qualidade do código, mas também minimiza a propensão a maus cheiros, resultando em um código mais eficiente e sustentável.

## Tópicos

1. Descrição e Efeitos no Código
2. Relação com Maus-Cheiros de Código
3. Operações de Refatoração
4. Referências Bibliográficas

## Descrição e Efeitos no Código

A característica idiomatic diz respeito à adesão às convenções e padrões da linguagem de programação utilizada. Códigos idiomáticos seguem as práticas comuns da linguagem, tornando-se mais legíveis e compreensíveis para os desenvolvedores familiares com a linguagem específica.

Efeitos no código:

- **Legibilidade Aprimorada:** Códigos idiomáticos são mais fáceis de entender, pois seguem as convenções aceitas pela comunidade da linguagem.
- **Consistência:** A adesão a padrões idiomáticos promove consistência no estilo de código, facilitando a colaboração entre membros da equipe.

## Relação com Maus-Cheiros de Código

- Não Adesão às Convenções: Códigos que não seguem as práticas idiomáticas podem ser difíceis de entender para outros desenvolvedores e podem introduzir confusão.

## Operações de Refatoração

- **Ajuste de Estilo:** Modificar o código para seguir as convenções idiomáticas da linguagem, garantindo uniformidade e compreensibilidade.

### (Antes) Não idiomático

```
def somar_numeros(lista):
    resultado = 0
    for i in range(len(lista)):
        resultado += lista[i]
    return resultado
```


### (Depois) Idiomático

```
def somar_numeros(lista):
    return sum(lista)

```


## Referências Bibliográficas

FOWLER, Martin. Refactoring: improving the design of existing code. Boston: Addison-Wesley Longman Publishing Co., Inc., 1999.


