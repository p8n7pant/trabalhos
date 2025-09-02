






#include<stdio.h>
#include<stdlib.h>
#include<time.h>
void numeros_sorteio(){
    int aleatorio,i;
    for(i=1;i<=6;i++){
        aleatorio=rand() %60 +1;
         printf("\n %d\n ",aleatorio);
    }
     printf("\n");
}
int main(){
    srand(time(NULL));
 numeros_sorteio();
    return 0;
}
