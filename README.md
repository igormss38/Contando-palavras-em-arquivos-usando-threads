#include <stdio.h>
#define total (30)

char *ler (char *);

int main(void)
{
    FILE *arq;
    char arquivo[total];
    char totalPalavra;
    int i; 
    int total_palavras = 0;

    do
    {
        if (scanf("%29[^\n]", arquivo) == 0){
            return 0;
        }

        scanf("%*[^\n]"); scanf("%*c");
        arq = fopen(arquivo, "r");

        if (arq == NULL){
            printf("Erro %s \n", arquivo);
        }

    } while (arq == NULL);
    
    while ((totalPalavra = fgetc(arq)) != EOF) {
        if(totalPalavra == ' ' || totalPalavra == '\t' || totalPalavra == '\0' || totalPalavra == '\n') {
        if (i) 
        {
        i = 0;
        total_palavras++;
        }
        } else 
        {
        i = 1;
        }
    }

    printf("palavras do arquivo %s : %d\n",arquivo, total_palavras);
    fclose(arq);
    return 0;
}
