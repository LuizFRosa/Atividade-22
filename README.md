# Atividade-22

#include <stdio.h>
#include <stdlib.h>

// Função que realiza a busca binária
int buscaBinaria(int vetor[], int tamanho, int alvo) {
        int esquerda = 0;
        int direita = tamanho - 1;

        while (esquerda <= direita) {
        int meio = esquerda + (direita - esquerda) / 2;

        // Verifica se o alvo está no meio
        if (vetor[meio] == alvo) {
            return meio; // Elemento encontrado
        }

        // Se o alvo for maior, ignora a metade esquerda
        if (vetor[meio] < alvo) {
            esquerda = meio + 1;
        }
        // Se o alvo for menor, ignora a metade direita
        else {
            direita = meio - 1;
        }
    }

    // Se o elemento não for encontrado
    return -1;
}

int main() {
	
    // Vetor ordenado
    int vetor[] = {2, 4, 6, 8, 10, 12, 14, 16, 18, 20};
    int tamanho = sizeof(vetor) / sizeof(vetor[0]);
    int alvo;
    int resultado;
    char continuar;

    do {
        // Solicita ao usuário o valor a ser buscado
        printf("Digite o valor que deseja buscar: ");
        scanf("%d", &alvo);

        // Chama a função de busca binária
        resultado = buscaBinaria(vetor, tamanho, alvo);

        // Exibe o resultado
        if (resultado != -1) {
            printf("Elemento encontrado na posicao: %d\n", resultado);
        } else {
            printf("Elemento nao encontrado.\n");
        }

        // Pergunta ao usuário se deseja procurar outro número
        printf("Deseja buscar outro valor? (s/n): ");
        scanf(" %c", &continuar); // Note o espaço antes de %c para consumir qualquer caractere de nova linha residual

        } while (continuar == 's' || continuar == 'S');

        printf("Programa encerrado.\n");

        return 0;
       }
