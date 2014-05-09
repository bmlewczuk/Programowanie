```c
#include<stdio.h>
#include<string.h>
#define MAX 128

main(){
	int i, f, wynik=0;
	char haslo[MAX];
	char porow[MAX] = "a";
	for(i=1;i<=10;i++){
		printf("%i wybrany czasownik to: x\n", i);
		for (f=1;f<=3;f++){
			printf("podaj %d forme czasownika\n", f);
			gets(haslo);
			if (stricmp(haslo, porow) == 0){
				printf("bardzo dobrze!\n\n");
				wynik+=1;	
			} 
			else printf("niestety, pomylka\n\n");
		}
	}
	printf("zdobyles %d na 30 punktow", wynik);
}
```
