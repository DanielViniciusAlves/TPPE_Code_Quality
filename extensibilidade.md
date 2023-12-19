# Extensibilidade
O conceito de extensibilidade refere-se à capacidade do código-fonte de ser facilmente estendido e adaptado para incluir novas funcionalidades ou realizar modificações sem alterar drasticamente a estrutura existente. Códigos extensíveis são flexíveis e permitem a adição de novos recursos de forma modular.

## Exemplo 1: Manipulação de Listas Genéricas

```
#include <stdio.h>
#include <stdlib.h>

// Definição de estrutura para um nó genérico
typedef struct Node {
    void *data;
    struct Node *next;
} Node;

// Função para criar um novo nó
Node *criarNo(void *data) {
    Node *novoNo = (Node *)malloc(sizeof(Node));
    if (novoNo != NULL) {
        novoNo->data = data;
        novoNo->next = NULL;
    }
    return novoNo;
}

// Função para imprimir uma lista genérica
void imprimirLista(Node *head, void (*imprimir)(void *)) {
    Node *atual = head;
    while (atual != NULL) {
        imprimir(atual->data);
        atual = atual->next;
    }
}

// Função para imprimir um inteiro
void imprimirInteiro(void *data) {
    printf("%d ", *((int *)data));
}

int main() {
    // Criar lista genérica de inteiros
    Node *lista = criarNo((void *)malloc(sizeof(int)));
    *((int *)lista->data) = 10;

    lista->next = criarNo((void *)malloc(sizeof(int)));
    *((int *)lista->next->data) = 20;

    // Imprimir lista de inteiros
    imprimirLista(lista, imprimirInteiro);

    return 0;
}
```

## Exemplo 2: Sistema de Plugins Simples

```
#include <stdio.h>

// Interface para um plugin
typedef struct {
    void (*executar)(void);
} Plugin;

// Implementação de um plugin específico
void meuPlugin() {
    printf("Executando meu plugin!\n");
}

int main() {
    // Criação e execução de um plugin
    Plugin plugin = {meuPlugin};
    plugin.executar();

    return 0;
}
```

Neste exemplo, a definição de uma interface simples para plugins permite a adição fácil de novos recursos ao sistema sem modificar o código principal.
Esses exemplos ilustram como a extensibilidade em C pode ser alcançada, permitindo que o código seja adaptado para incluir novas funcionalidades de maneira modular e eficiente.