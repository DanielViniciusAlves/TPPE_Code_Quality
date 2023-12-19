# Boas Interfaces

A criação de boas interfaces é fundamental para o desenvolvimento de software robusto e de fácil manutenção. Interfaces bem projetadas definem contratos claros entre diferentes partes do sistema, proporcionando uma abstração eficaz e permitindo a comunicação sem ambiguidades. Boas interfaces devem ser intuitivas, documentadas e capazes de resistir a mudanças no interior das implementações.

## Tópicos

1. Efeitos no Código
2. Relação com Maus-Cheiros de Código
3. Operações de Refatoração
4. Referências Bibliográficas
5. Materiais de Apoio

## Efeitos no Código

- **Clareza e Legibilidade:** Boas interfaces tornam o código mais claro e legível, facilitando o entendimento das interações entre diferentes componentes.
- **Facilidade de Uso:** Uma interface bem projetada simplifica o uso do código, tornando-o intuitivo para os desenvolvedores que a utilizam.
- **Manutenibilidade:** Interfaces bem definidas isolam a implementação subjacente, permitindo alterações internas sem impactar o código que as utiliza.

## Relação com Maus-Cheiros de Código

- **Interfaces Confusas ou Inconsistentes:** Interfaces mal projetadas podem levar a confusões e dificuldades na compreensão do código que as utiliza.

## Operações de Refatoração

- **Extrair Interface:** Isolar uma parte do código como uma interface, promovendo a modularidade e a abstração.
- **Renomear Métodos:** Ajustar nomes de métodos em interfaces para refletir com precisão sua funcionalidade, melhorando a clareza.

### Exemplo de Interface Bem Definida:

```
public interface NotificationService {
    void enviarNotificacao(String mensagem, String destinatario);
    void configurarCanal(String canal);
    void configurarTempoExpiracao(int segundos);
}

```

Neste exemplo, a interface NotificationService é bem definida. Ela possui métodos claramente nomeados e coesos, relacionados ao propósito de enviar notificações. Os métodos são intuitivos, fornecendo funcionalidades específicas sem serem excessivamente genéricos.

### Exemplo Interface Mal Definida:

```
public interface NotifService {
    void sendMsg(String msg, String recipient);
    void configure(String channel, int timeout);
    Object doSomething(Object input);
}

```

Aqui, a interface NotifService é mal definida. Os nomes de métodos são vagos e não transmitem claramente o propósito ou a funcionalidade. A presença do método doSomething sem uma descrição clara adiciona ambiguidade à interface. A falta de coesão dificulta a compreensão do propósito geral do serviço.

## Referências Bibliográficas

FOWLER, Martin. Refactoring: improving the design of existing code. Boston: Addison-Wesley Longman Publishing Co., Inc., 1999.

## Materiais de Apoio

1. Designing Interfaces: Patterns for Effective Interaction Design" por Jenifer Tidwell.

2. Clean Code: A Handbook of Agile Software Craftsmanship" por Robert C. Martin.

