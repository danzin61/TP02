# TP02
 #include <stdio.h>

// funçao para verificar se um numero e primo
int nPrimo(int num) {
    if (num <= 1) {
        return 0; // 0 e 1 nao sao primos
    }
    for (int i = 2; i * i <= num; i++) {
        if (num % i == 0) {
            return 0; // nao e primo
        }
    }
    return 1; // e primo
}

int main() {
    int num;
    
    printf("Digite um número inteiro maior que 2: ");
    scanf("%d", &num);

    if (num <= 2) {
        printf("O número fornecido não é maior que 2.\n");
        return 1;
    }

    int primo1, primo2;
    
    // encontre a decomposiçao em numeros primos
    for (primo1 = 2; primo1 <= num / 2; primo1++) {
        if (nPrimo(primo1) && nPrimo(num - primo1)) {
            primo2 = num - primo1;
            break; // para a busca apos encontrar a primeira decomposiçao valida
        }
    }

    printf("%d + %d = %d\n", primo1, primo2, num);

    return 0;
}
