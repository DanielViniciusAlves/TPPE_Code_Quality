# Codificação Elegante

A codificação elegante refere-se à prática de escrever código de forma clara, concisa e eficiente, facilitando a leitura, manutenção e compreensão do código-fonte. Códigos elegantes são geralmente bem estruturados, utilizam boas práticas de programação e seguem convenções que tornam o código mais legível. 

## Exemplo 1: Manipulação de Strings
```
#include <stdio.h>
#include <string.h>

// Função para inverter uma string
void inverterString(char *str) {
    int inicio = 0;
    int fim = strlen(str) - 1;

    while (inicio < fim) {
        // Troca os caracteres no início e no fim
        char temp = str[inicio];
        str[inicio] = str[fim];
        str[fim] = temp;

        // Move os índices para o meio da string
        inicio++;
        fim--;
    }
}

int main(void) {
    char minhaString[] = "Codificacao Elegante";

    // Chama a função para inverter a string
    inverterString(minhaString);

    // Imprime a string invertida
    printf("String Invertida: %s\n", minhaString);

    return EXIT_SUCCESS;
}

```

## Exemplo 2: Estrutura e Modularidade
```
#include <stdio.h>
#include<stdlib.h>

// Definição da estrutura para representar um ponto no plano cartesiano
typedef struct {
    float x;
    float y;
} Ponto;

// Função para calcular a distância entre dois pontos
float calcularDistancia(Ponto p1, Ponto p2) {
    float distancia = sqrt(pow(p2.x - p1.x, 2) + pow(p2.y - p1.y, 2));
    return distancia;
}

int main(void) {
    // Criação de dois pontos
    Ponto ponto1 = {1.0, 2.0};
    Ponto ponto2 = {4.0, 6.0};

    // Chama a função para calcular a distância entre os pontos
    float distancia = calcularDistancia(ponto1, ponto2);

    // Imprime a distância calculada
    printf("Distancia entre os pontos: %.2f\n", distancia);

    return EXIT_SUCCESS;
}
```