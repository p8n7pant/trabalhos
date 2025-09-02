#include<stdio.h>
#include<stdlib.h>
struct Jogo {
    int quantidade_cartoes;
    int cartoes[4][12];
    int quantidade_numeros_do_cartao[4];
    int maximo_cartoes;
    int minimo_numeros_por_cartao;
    int maximo_numeros_por_cartao;
};

int main() {
    struct Jogo jogador[8];  // até 8 jogadores
    int i, j, k;
    int jogadores;

    // Lê número de jogadores e valida
    do {
        printf("Numero de jogadores (1 a 8): ");
        scanf("%d", &jogadores);

        if (jogadores < 1)
            printf("Numero de jogadores insuficiente! Tente novamente.\n");
        else if (jogadores > 8)
            printf("Numero de jogadores excedido! Tente novamente.\n");

    } while (jogadores < 1 || jogadores > 8);

    printf("Numero de jogadores = %d\n", jogadores);
    for(i=0;i< jogadores;i++){
    	jogador[i].maximo_cartoes=4;
    	jogador[i].minimo_numeros_por_cartao=6;
    	jogador[i].maximo_numeros_por_cartao=12;
    	jogador[i].quantidade_cartoes=0;
	
	for(j=0;j<4;j++){
		jogador[i].quantidade_numeros_do_cartao[j]=0;
		for(k=0;k<12;k++){
			jogador[i].cartoes[j][k]=0;
		}
	}
	do{
		printf("\n jogador %d ecolha um numero de (1-4)?",i+1);
		scanf("%d", &jogador[i].quantidade_cartoes);
		if(jogador[i].quantidade_cartoes<1){
			printf("\n numero menor que 1, Tente novamente!");
		}
		if(jogador[i].quantidade_cartoes>jogador[i].maximo_cartoes){
			printf("\n passou do limite de cartas, tente novamente");
		}
	}while (jogador[i].quantidade_cartoes<1 || jogador[i].quantidade_cartoes>jogador[i].maximo_cartoes);
	 printf("Jogador %d tem essas cartas %d.\n", i + 1, jogador[i].quantidade_cartoes);
}
return 0;
}
