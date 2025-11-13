# -Batalha-Naval
Desafio Jogo de Batalha Naval

Módulo 1 ( Novato ) -----------------------------------------------------

#include <stdio.h>

#define TAM 10

int main() {
    int tabuleiro[TAM] = {0};  // 0 = água, 1 = navio
    int posicaoNavio = 4;

   // Posiciona o navio
    tabuleiro[posicaoNavio] = 1;

   printf("=== BATALHA NAVAL (NOVATO) ===\n");
    for (int i = 0; i < TAM; i++) {
        if (tabuleiro[i] == 1)
            printf("N "); // N = navio
        else
            printf("~ "); // ~ = água
    }
    printf("\n");

  return 0;
}

Modulo 2 ( Aventureiro ) -----------------------------------------------------

#include <stdio.h>

#define TAM 8

int main() {
    int tabuleiro[TAM][TAM] = {0};

   // Navio horizontal
    for (int j = 2; j < 5; j++)
        tabuleiro[1][j] = 1;

  // Navio vertical
    for (int i = 3; i < 6; i++)
        tabuleiro[i][4] = 1;

  // Navio diagonal
    for (int i = 0; i < 3; i++)
        tabuleiro[i + 5][i + 2] = 1;

  printf("=== BATALHA NAVAL (AVENTUREIRO) ===\n");
    for (int i = 0; i < TAM; i++) {
        for (int j = 0; j < TAM; j++) {
            if (tabuleiro[i][j] == 1)
                printf("N ");
            else
                printf("~ ");
        }
        printf("\n");
    }

  return 0;
}

Modulo 3 ( Mestre ) -----------------------------------------------------

#include <stdio.h>

#define TAM 9

void exibirTabuleiro(int tabuleiro[TAM][TAM]) {
    for (int i = 0; i < TAM; i++) {
        for (int j = 0; j < TAM; j++) {
            if (tabuleiro[i][j] == 1)
                printf("N ");
            else if (tabuleiro[i][j] == 2)
                printf("* "); // área de efeito
            else
                printf("~ ");
        }
        printf("\n");
    }
}

int main() {
    int tabuleiro[TAM][TAM] = {0};

  // Coloca alguns navios
    tabuleiro[4][4] = 1;
    tabuleiro[2][6] = 1;

  // Coordenadas do centro da habilidade
    int x = 4, y = 4;

  // Habilidade em forma de cruz
    for (int i = 0; i < TAM; i++) {
        for (int j = 0; j < TAM; j++) {
            if (i == x || j == y)  // mesma linha ou coluna
                tabuleiro[i][j] = 2;
        }
    }

  printf("=== BATALHA NAVAL (MESTRE) ===\n");
    exibirTabuleiro(tabuleiro);

  return 0;
}
