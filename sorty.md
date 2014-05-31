```c
#include<stdio.h>
#include<stdlib.h>
#include<time.h>
#define MAX 16

void wyswietl(int dane[], int rozmiar){
	int k;
	for (k=0;k<rozmiar;k++){
        printf ("%d ", dane[k]);
    }
}

int wypelnij(int dane[], int rozmiar){
	int k;	
	srand(time(NULL));
	for (k=0;k<rozmiar;k++){
    	dane[k]=(rand()%17)+7;
    }
}


int main(){
    int dane[MAX], rozmiar;
    rozmiar=MAX;
    wypelnij(dane, rozmiar);
    wyswietl(dane, rozmiar);
}

```
