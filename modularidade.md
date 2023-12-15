# Modularidade

A coesão e o acoplamento são aspectos cruciais em um projeto de software eficaz. A coesão, refere-se à medida em que as funcionalidades relacionadas são agrupadas logicamente em um módulo. Em um código coeso, as partes internas do módulo trabalham de maneira integrada, formando uma unidade funcional clara. A coesão contribui para a compreensão e manutenção do código, uma vez que cada módulo desempenha um papel bem definido, facilitando ajustes e modificações específicas. Por outro lado, o acoplamento, mede a interdependência entre os módulos. Um baixo acoplamento, como na busca pela simplicidade, implica que os módulos são independentes, reduzindo a influência de um sobre o outro. Isso resulta em código mais modular, fácil de testar e modificar, evitando o risco de efeitos colaterais indesejados. Dessa forma, ao otimizar a coesão e minimizar o acoplamento, um projeto de software promove uma estrutura clara e compreensível, facilitando a colaboração entre os membros da equipe e fortalecendo a base para um desenvolvimento eficiente (adaptado de FOWLER, 1999).

## Tópicos

1. Descrição e Efeitos no Código
2. Relação com Maus-Cheiros de Código
3. Operações de Refatoração
4. Referências Bibliográficas
5. Materiais de Apoio

## Descrição e Efeitos no Código

A modularidade é uma das características fundamentais em um sólido design de software. Refere-se à capacidade do código de ser dividido em módulos independentes e interconectados, cada um desempenhando uma função específica. Uma arquitetura modular promove a coesão, onde os componentes de um módulo estão fortemente relacionados entre si, compartilhando uma finalidade comum. Ao mesmo tempo, a modularidade visa manter um baixo acoplamento entre os diferentes módulos, minimizando as dependências entre eles. Um código modular é mais fácil de entender, pois permite que os desenvolvedores foquem em partes específicas do sistema sem se perderem em complexidades desnecessárias. A coesão resultante de uma abordagem modular contribui para a manutenibilidade do código, enquanto o baixo acoplamento facilita a adaptação e a expansão do sistema sem causar impactos indesejados

## Relação com Maus-Cheiros de Código

A modularidade no design de software desempenha um papel crucial na abordagem de maus cheiros de código, como o Código Duplicado, Método Longo e Classe Inchada. Ao adotar uma abordagem modular, é possível reduzir significativamente o Código Duplicado, já que módulos reutilizáveis podem ser criados para conter funcionalidades comuns, evitando repetições desnecessárias. A quebra de funcionalidades em módulos também aborda o problema do Método Longo, pois promove a implementação de métodos mais curtos e específicos, facilitando a leitura, manutenção e compreensão do código. No caso da Classe Inchada, a modularidade permite distribuir responsabilidades entre diferentes módulos, evitando que uma única classe cresça excessivamente. Isso não apenas melhora a organização e clareza da estrutura do código, mas também reduz o acoplamento, já que cada módulo pode se concentrar em uma responsabilidade específica, resultando em classes mais coesas e fáceis de entender.

## Operações de Refatoração

A modularidade no design de software é essencial para criar sistemas mais compreensíveis e de fácil manutenção. No contexto da "Classe Inchada", a refatoração se torna uma ferramenta valiosa para promover a modularidade. A técnica de refatoração "Extract Class" é particularmente relevante nesse cenário. Ela permite abordar o problema de uma classe que se tornou grande e complexa, dividindo suas responsabilidades em classes menores e mais coesas. Ao identificar grupos lógicos de responsabilidades, essa técnica contribui diretamente para a criação de módulos independentes, facilitando a compreensão e a manutenção do código. A modularidade resultante não apenas melhora a organização interna do código, mas também reduz o acoplamento, uma vez que as classes mais enxutas são menos propensas a depender excessivamente umas das outras.

### Exemplo de Classe inchada

```
public class Cachorro {
    private String nome;
    private int idade;
    private String cor;
    private String raca;
    private boolean estaComFome;

    public void exibirInformacoes() {
        System.out.println("Nome: " + nome);
        System.out.println("Idade: " + idade);
        System.out.println("Cor: " + cor);
        System.out.println("Raça: " + raca);
        System.out.println("Está com fome? " + estaComFome);
    }

    public void latir() {
        if (estaComFome) {
            System.out.println(nome + " está latindo por comida!");
        } else {
            System.out.println(nome + " está latindo!");
        }
    }

    public void alimentar() {
        estaComFome = false;
        System.out.println(nome + " foi alimentado!");
    }

    public void envelhecer() {
        idade++;
        System.out.println(nome + " envelheceu um ano!");
    }
}
```

### Exemplo de Código modularizado

```
public class Cachorro {
    private String nome;
    private int idade;
    private String cor;
    private String raca;
    private boolean estaComFome;
    private Latido latido;

    public void exibirInformacoes() {
        System.out.println("Nome: " + nome);
        System.out.println("Idade: " + idade);
        System.out.println("Cor: " + cor);
        System.out.println("Raça: " + raca);
        System.out.println("Está com fome? " + estaComFome);
    }

    public void latir() {
        latido.latir(nome, estaComFome);
    }

    public void alimentar() {
        estaComFome = false;
        System.out.println(nome + " foi alimentado!");
    }

    public void envelhecer() {
        idade++;
        System.out.println(nome + " envelheceu um ano!");
    }
}

public class Latido {
    public void latir(String nomeCachorro, boolean comFome) {
        if (comFome) {
            System.out.println(nomeCachorro + " está latindo por comida!");
        } else {
            System.out.println(nomeCachorro + " está latindo!");
        }
    }
}
```



## Referências Bibliográficas

FOWLER, Martin. Refactoring: improving the design of existing code. Boston: Addison-Wesley Longman Publishing Co., Inc., 1999.

## Materiais de Apoio

1. [Extract Class](https://refactoring.guru/pt-br/extract-class)

2. [Refactoring - Martin Fowler](https://martinfowler.com/books/refactoring.html)
